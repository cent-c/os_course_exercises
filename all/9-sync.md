# 同步

##单选题

---

操作系统中，两个或多个并发进程各自占有某种资源而又都等待别的进程释放它们所占有的资源的现象叫做什么（）
- [ ] 饥饿
- [x] 死锁
- [ ] 死机
- [ ] 死循环

>	解释：饥饿状态的进程不会进入等待状态，死锁是指两个或多个进程各自占有某种资源而又等待别的进程释放其所占有的资源。

临界资源是什么类型的共享资源（）
- [ ] 临界资源不是共享资源
- [ ] 用户共享资源
- [x] 互斥共享资源
- [ ] 同时共享资源

>	解释：临界资源是指能够被多个进程共享，但是同一时间只能由一个进程访问的资源，因此是互斥的。

要想进程互斥地进入各自的同类资源的临界区，需要（）
- [ ] 在进程间互斥使用共享资源
- [ ] 在进程间非互斥使用临界资源
- [x] 在进程间互斥地使用临界资源
- [ ] 在进程间不使用临界资源

>	解释：临界资源位于临界区，共享资源不一定位于临界区，因此无法保证进程进入临界区；非互斥使用临界资源和不使用临界资源均无法保证进程互斥地进入临界区，因为不存在临界资源的互斥使用的话个进程之间不存在互斥关系。

一个进程由阻塞队列进入就绪队列，可能发生了哪种情况（）
- [x] 一个进程释放一种资源
- [ ] 系统新创建了一个进程
- [ ] 一个进程从就绪队列进入阻塞队列
- [ ] 一个在阻塞队列中的进程被系统取消了

>	解释：一个进程释放了一种资源后，可能该资源正是位于阻塞队列中的一个进程所必需的资源，因此该进程便可以从阻塞队列进入就绪队列；其余三种情况均不会使某个进程从阻塞队列进入就绪队列。

设两个进程共用一个临界区的互斥信号量mutex，当一个进程进入了临界区，另一个进程等待时，mutex应该等于多少（）
- [x] -1
- [ ] 0
- [ ] 1
- [ ] 2

>	解释：两个进程共用一个临界区的互斥信号量mutex，那么mutex的取值范围应该是1到-1，1表示没有进程进入临界区并且也没有进程等待，0表示有一个进程进入临界区，-1表示有一个进程进入临界区并且另一个进程等待。

共享变量是指（）访问的变量
- [ ] 只能被系统进程
- [ ] 只能被多个进程互斥
- [ ] 只能被用户进程
- [x] 可被多个进程

>	解释：共享变量可以被多个进程访问，并且不需要互斥访问，可以访问的进程既可以是系统进程，也可以是用户进程。

临界区是指并发进程中访问共享变量的（）段
- [ ] 管理信息
- [ ] 信息存储
- [ ] 数据
- [x] 程序

>	解释：临界区是指进程中的一段需要访问共享资源并且当另一个进程处于相应代码区域时便不会被执行的代码区域。

假定在一个处理机上执行以下五个作业，其中采用HRN（最高响应比优先）算法时第三个被选择的作业号是（）

		 作业号     到达时间     运行时间
		    A         0            4
		    B         1            3
		    C         2            5
		    D         3            2
		    E         4            4

- [ ] A
- [ ] B
- [ ] C
- [x] D
- [ ] E

>	解释：A到达时没有其他进程到达，所以先处理A，当A处理完时其余所有进程都到达，此时计算各自的响应比：B=(3+3)/3=2, C=(2+5)/5=1.4, D=(1+2)/2=1.5, E=4/4=1。所以第二个被选择的是B，B完成后再次计算响应比：C=(5+5)/5=2, D=(4+2)/2=3, E=(3+4)/4=1.75，所以第三个被选择的是D。

下面关于Bakery算法的描述错误的是（）
- [ ] 进入临界区前，每个进程都会得到一个数字
- [ ] 得到数字最小的进程可以进入临界区
- [x] 如果P2和P4两个进程得到的数字相同，那么P4先进入临界区
- [ ] 数字是按照从小到大生成的\

>	解释：Bakery算法描述：（1）进入临界区之前，进程接收一个数字；（2）得到的数字最小的进入临界区；（3）如果进程Pi和Pj收到相同的数字，那么如果i<j，Pi先进入临界区，否则Pj先进入临界区；（4）编号方案总是按照枚举的增加顺序生成数字

Peterson算法是解决Pi和Pj之间互斥的经典的（）的解决方法
- [ ] 基于中断禁用
- [x] 基于软件
- [ ] 基于硬件
- [ ] 基于原子操作

>	解释：Peterson算法是满足进程Pi和Pj之间互斥的经典的基于软件的解决方法（1981年）。

如果有5个进程共享同一程序段，每次允许3个进程进入该程序段，若用PV操作作为同步机制则信号量S为-1时表示什么（）
- [ ] 有四个进程进入了该程序段
- [ ] 有一个进程在等待
- [x] 有三个进程进入了程序段，有一个进程在等待
- [ ] 有一个进程进入了该程序段，其余四个进程在等待

>	解释：S初始为3，当有一个进程进入程序段或等待时，S减一. S为-1，意味着有四次减1的操作，也即3个进程获准进入，1个在等待。

---

##多选题

---

产生死锁的必要条件（1345）
- [x] 互斥
- [ ] 可抢占
- [x] 不可抢占
- [x] 占有且申请
- [x] 循环等待

>	解释：产生死锁的四个必要条件：（1）互斥--一个资源每次只能给一个进程使用（2）不可抢占--资源申请者不能强行的从资源占有者手中夺取资源，资源只能由占有者自愿释放（3）占有且申请--一个进程在申请新的资源的同时保持对原有资源的占有（只有这样才是动态申请，动态分配）（4）循环等待--存在一个进程等待队列
    {P1 , P2 , … , Pn},
    其中P1等待P2占有的资源，P2等待P3占有的资源，…，Pn等待P1占有的资源，形成一个进程等待环路。

锁的实现方法有哪几种（124）
- [x] 禁用中断
- [x] 软件方法
- [ ] 添加硬件设备
- [x] 原子操作指令

>	解释：实现锁机制的三种方法：禁用中断（仅限于单处理器），软件方法（复杂）和原子操作指令（单处理器或多处理器均可）。锁机制是高等级的编程抽象，因此无法使用硬件设备实现。

---

##判断题

---

产生死锁的根本原因是供使用的资源数少于需求资源的进程数。
- [x] 对
- [ ] 错

>	解释：死锁是指两个或多个进程各自占有某种资源而又等待别的进程释放其所占有的资源，因此根本原因就是提供的资源少于需求的资源。

一旦出现死锁, 所有进程都不能运行。
- [ ] 对
- [x] 错

>	解释：出现死锁后，处于死锁状态的进程无法继续运行，但是其他无关的进程可以继续运行。

所有进程都挂起时, 系统陷入死锁。
- [ ] 对
- [x] 错

>	解释：死锁是指两个或多个进程各自占有某种资源而又等待别的进程释放其所占有的资源。所有进程都挂起并不代表其无法被完成。

参与死锁的所有进程都占有资源。
- [ ] 对
- [x] 错

>	解释：应该是参与死锁的所有进程都等待资源。不占有资源的进程也可能进入死锁。

有m个进程的操作系统出现死锁时, 死锁进程的个数为1<k≤m。
- [x] 对
- [ ] 错

>	解释：死锁并不会将所有的进程都牵扯进去，但出现死锁时一定会有进程参与。

进程间的互斥是一种特殊的同步关系。
- [x] 对
- [ ] 错

>	解释：基本概念，互斥是实现同步的一种方式，因此也代表一种同步关系。

所有进程都进入等待状态时，系统陷入死锁。
- [ ] 对
- [x] 错

>	解释：产生死锁的四个必要条件：（1）互斥--一个资源每次只能给一个进程使用（2）不可抢占--资源申请者不能强行的从资源占有者手中夺取资源，资源只能由占有者自愿释放（3）占有且申请--一个进程在申请新的资源的同时保持对原有资源的占有（只有这样才是动态申请，动态分配）（4）循环等待--存在一个进程等待队列
    {P1 , P2 , … , Pn},
    其中P1等待P2占有的资源，P2等待P3占有的资源，…，Pn等待P1占有的资源，形成一个进程等待环路。

