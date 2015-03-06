---
layout: blog
title:  "IDL使用IDL_IDLbridge进行多线程运算"
subtitle: "Using IDL_IDLbridge for multi-processes purpose"
categories: Techs
tags: IDL
---
当使用IDL（version>=6.3） 时，可以利用IDL_IDLbridge进行多线程（并行）处理。主要针对大量互不影响的函数运算。在有多个核的服务器上尤为有效。
整体思路为: 创建类名为IDL_IDLBridge的对象,该对象作为一个新的idl子进程,通过execute属性将使用的程序在这个进程里编译过后,并运行该程序.通过该对象status属性,检测已完成上一次任务的进程,并分配新的任务,直至所有任务都被执行过.通过setvar和getvar属性在母进程和子进程之间传递参数.
下面是示例程序写法，以及适当说明：

<!--more-->

```
;20131124 RUIXIONG ZHANG multi-processes controller
;本示例目的在于使用指定线程数，以指定参数，执行特定函数。
 
 
 ;给定使用的线程数量，如果过大，则会出问题。
 threads=8;the number of the processes used
 ;给定所使用的函数地址，进行编译之用
 Function_position='/ozone_nox_voc.pro'
 ;给定所使用的函数，进行引用
 Function_name='ozone_nox_voc'
 ;创建一个对象数组，用以代表线程
 p=objarr(threads)
 ;用以记录每个线程正在进行的任务
 p_task=fltarr(threads);thread's last task position
 ;任务池的大小
 task_num=50*50;tasks number
 ;任务池里下一个任务的编号
 new_task=0;next task tracer
 ;输出结果
 output=fltarr(50,50)
 output(*,*)=!values.f_nan
 ;parameteres initialization
 ;任务池里各个任务所代表的参数
 parameter=fltarr(2,50,50)
 FOR i=0,49 do parameter(0,*,i)=indgen(50)*0.1+0.1
 FOR i=0,49 do parameter(1,*,i)=indgen(50)*0.1+0.1
 ;initialization, assign the first jobs to the threads
 FOR j=0,threads-1 do begin
 ;将p(j)创建为IDL_IDLBridge类的对象，也就是赋予其一个子idl进程
   p(j)=OBJ_NEW('IDL_IDLBridge')
   temp=array_sub(50,50,new_task);get the position of a new task
   voc_str=string(parameter(0,temp[0],temp[1]))
   nox_str=string(parameter(1,temp[0],temp[1]))
   ;记录赋予该进程的任务
   p_task(j)=new_task;this is my task!
   new_task++
   ;设定子进程里的参数（这个是函数所在位置）
   p(j)->Setvar,"function",Function_position
   ;在子进程里编译该函数
   p(j)->Execute,".compile function"
   ;将函数结果赋给子进程里的maxium变量，/nowait代表此命令后母进程直接执行下一条命令。
   p(j)->Execute,"maxium="+Function_name+"("+voc_str+","+nox_str+")",/nowait
 ENDFOR
 signal=intarr(threads); threads' status managernew_task=0
 print,'Successfully initialized and waiting for signal'
 t0=systime(1)
 While (1 gt 0) do begin
   ;查看每个子进程的状况，1为忙，0为闲  
   for i=0,threads-1 do signal(i)=p(i)->Status()
   ;如果所有子进程都空闲，且任务池没有任务，则跳出while循环
   if (new_task eq task_num)and(total(signal)eq 0) then break;all tasks are done
   pos=where(signal eq 0,pos_count);idle threads
   ;对空闲子进程赋予新的任务
   FOR i=0,pos_count-1 do begin
     thread_idle=pos(i)
     temp=array_sub(50,50,p_task(thread_idle));my last task position
     output(temp[0],temp[1])=p(thread_idle)->Getvar('maxium')
     print,'Thread '+string(thread_idle,format='(i)')+' finishes task:'+string(temp[0],format='(i)')+' '+string(temp[1],format='(i)')
     print,'Result: '+string(output(temp[0],temp[1]))
     ;如果最后一个任务已经被他子进程执行，则不作为
     if (new_task eq task_num) then continue;no tasks left
     temp=array_sub(50,50,new_task)
     p_task(thread_idle)=new_task;my new task num!
     voc_str=string(parameter(0,temp[0],temp[1]))
     nox_str=string(parameter(1,temp[0],temp[1]))
     new_task++
     p(j)->Execute,"maxium="+Function_name+"("+voc_str+","+nox_str+")",/nowait
     dt=systime(1)-t0
     print,'Moves to task:'+string(temp[0],format='(i)')+' '+string(temp[1],format='(i)')
     print,'Elapse time: '+string(dt/60,format='(i)')+' min'
     print,'Assigned/Unassigned task: '+string(new_task,format='(i)')+'/'+string(task_num,format='(i)')
     print,'*******************************************************************'
     print,''
   ENDFOR
 ENDwhile
 
 print,'Computation is completed!'
 save,output,filename='/temp.sav'
 print,'All saved! Work done!'
 ```
 
 
 





本文引用地址：http://blog.sciencenet.cn/blog-733034-744790.html  此文来自科学网张睿雄博客 
