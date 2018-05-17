## 一、数据结构（Data Structure）

+ **数据（Data）** 是描述客观事物的符号，是计算机中可以操作的对象，是能被计算机识别，并输入给计算机处理的符号集合。

+ **数据元素（Data Element）** 是组成数据的、有一定意义的基本单位，在计算机中通常作为整体处理。也被称为 **记录（Record）**。

+ **数据项（Data Item）** 指一个数据元素可以由若干个数据项组成。

+ **数据对象(Data Object)** 是性质相同的数据元素的集合，是数据的子集。

+ **数据结构（Data Structure）** 是指相互之间存在一种或多种特定关系的数据元素的集合。

+ **逻辑结构（Logical Structure）** 是指数据对象中数据元素之间的相互关系。
  1. 集合结构（Collection）： 集合结构中的数据元素除了同属一个集合外，它们之间没有其他的关系。
  2. 线性结构（Linear）： 线性结构中的数据元素之间是 **一对一** 的关系。
  3. 树形结构（Tree）： 树形结构中的数据元素之间存在一种 **一对多** 的层次关系。
  4. 图形结构（Graphical）： 图形结构的数据元素是 **多对多** 的关系。

+ **物理结构（Physical Structure）** 是指数据的逻辑结构在计算机中的储存形式。
  1. 顺序储存结构（Sequential Storage）： 是把数据元素存放在地址连续的存储单元里，其数据间的逻辑关系和物理关系是一致的。
  2. 链式储存结构（Chained Storage）： 是把数据元素存放在任意的存储单元里，这组存储单元可以是连续的，也可以是不连续的。

## 二、算法（Algorithm）

+ **算法（Algorithm）** 是解决特定问题求解步骤的描述，在计算机中表现为指令的有限序列，并且每条指令表示一个或多个操作。

+ 算法的5个特性
  1. 输入
  2. 输出
  3. 有穷性
  4. 确定性
  5. 可行性

+ 算法设计的要求
  1. 正确性
  2. 可读性
  3. 健壮性
  4. 时间效率高和储存量低

+ 算法时间复杂度（Time Complexity） T(n)=O(f(n))
  1. 常数阶 O(1)
  2. 线性阶 O(n)
  3. 对数阶 O(logn)
  4. 平方阶 O(n^2)
  5. O(1) < O(logn) < O(n) < O(nlogn) < O(n^2) < O(n^3) < O(2^n) < O(n!) < O(n^n)

+ 算法空间复杂度（Space Complexity） S(n)=O(f(n))

  &emsp;&emsp;算法的空间复杂度通过计算算法所需的存储空间实现，算法空间复杂度的计算公式记作: S(n)= O(f(n))，其中，n 为问题的规模， f(n) 为语句关于 n 所占存储空间的函数。

## 三、线性表（Linear List）

+ **线性表：** 

  &emsp;&emsp;零个或多个数据元素的有限序列。在较复杂的线性表中，一个数据元素可以由若干个数据项组成。（如：班级同学点名册）

+ 线性表的操作：

  1. InitList(L) // 初始化操作，建立一个空的线性表 L 
  2. DestroyList(L) // 线性表存在了，消耗一个线性表
  3. ClearList（L） // 将线性表清空
  4. ListEmpty（L） // 若线性表为空，返回 true；否则返回 false
  5. ListLength（L） // 返回线性表的长度
  6. GetElem（L, i, e） // 将线性表 L 中的第 i 个位置上的元素值返回给 e    
  7. PriorElem（L, cur_e, pre_e） // 如果 cur_e 是线性表中的元素，而且不是第一个，那么返回该元素前一个元素的值
  8. NextElem（L, cur_e, next_e） // 如果 cur_e 是线性表中的元素，而且不是最后一个，就返回它下一个元素的值
  9. Listinsert(L, i, e) // 如果线性表 L 存在了，而且 i 符合条件，则在 i 位置插入一个元素
  10. ListDelete（L, i） // 删除 i 位置上的元素
  11. ListDelete_data(L, e, order) // 删除指定的元素 e，order 决定是删除一个，还是全部
  12. Connect_two_List(L_a, L_b, L_c) // 连接两个线性表，除去重复的内容    
  13. print(L) // 打印线性表 L

+ **单链表：** 

    &emsp;&emsp;链表的定义是递归的，它或者为“空”（通常用 NULL 或 “^” 表示），或者指向另一个节点 Node 的引用，这个节点含有下一个节点或链表的引用。与顺序存储相比，允许存储空间不连续，插入删除时不需要移动大量的元素，只需修改指针即可，但查找某个元素，只能从头遍历整个链表。

  - 结点由存放数据元素的数据域和存放后继结点地址的指针域组成。
  - 链表中第一个结点的存储位置叫做头指针；在单链表的第一个节点前附设一个结点，称为头结点。
  - 无论链表是否为空，头指针均不为空。
  - 头结点不一定是链表的必须元素。

+ 单链表的操作：

  1. 头插法

  &emsp;&emsp;始终让新结点都插在第一的位置，如图：

  ![头插法](https://github.com/MaugerWu/DataStructure_Algorithm/blob/master/images/1.png)

  ```java
  public void headInsert(T item) {
      Node old = first;
      first = new Node();
      first.item = item;
      first.next = old;
      count++;
  }
  ```

  2. 尾插法

  &emsp;&emsp;把每次新结点都插在终端结点的后面，如图：

  ![尾插法](https://github.com/MaugerWu/DataStructure_Algorithm/blob/master/images/2.png)

  ```java
  public void tailInsert(T item) {
      Node old = last;
      last = new Node();
      last.item = item;
      last.next = null;
      if (isEmpty()) {
          first = last;
      } else {
          old.next = last;
      }
      count++;
  }
  ```

  &emsp;&emsp;节点的插入和删除，要点是先断后连，关键就是不要断链了，以插入为例（把s插入 p 和 q 之间），先断意思是先把 p->q 断了，变成 s->q，后连，最后再把 p 和 s连接起来。

  3. 插入节点

  &emsp;&emsp;待插入节点为s，一般采用后插法，即先找到插入位置节点的前驱节点，然后插入，时间复杂度O(n)。如图：

  ![插入结点](https://github.com/MaugerWu/DataStructure_Algorithm/blob/master/images/3.png)

  ```java
  p=getNodeByIndex(i-1);
  s.next = p.next;
  p.next = s;
  ```

  &emsp;&emsp;还有一种方法是，直接插入到位置的后面（前插法），然后交换两个节点的值，插入的节点到了指定位置，时间复杂度 O(1)：

  ```java
  s.next = p.next;
  p.next = s;
  temp = p.item;    // 交换内容
  p.item = s.item;
  s.item = temp;
  ```

  4. 删除节点

  &emsp;&emsp;待删除节点为 q，也是先找到前驱节点，修改指针域即可，时间复杂度 O(n)。如图：

  ![删除结点](https://github.com/MaugerWu/DataStructure_Algorithm/blob/master/images/4.png)

  ```java
  P = getNodeByIndex(i-1);
  q = p.next;
  p.next = q.next;
  q = null;
  ```

  &emsp;&emsp;删除节点也能直接删除其后继节点，然后将后继节点的内容赋给自己即可，时间复杂度为 O(1)：

  ```java
  q = p.next;
  p.item = p.next.item;
  p.next = q.next;
  q = null;
  ```

+ 线性表与单列表的区别：

  |存储类别|顺序存储结构|单链表（链式存储结构）|
  |:--:|:--|:--|
  |存储分配方式|用一段地址连续的存储单元依次存储线性表的数据元素|采用链式存储结构，用一组任意的存储单元存放线性表的元素|
  |时间性能|查找O（1）、插入和删除O（n）|查找O（n）、插入和删除O（1）|
  |空间性能|需要预分配存储空间，分大了浪费，小了容易发生上溢|不需要分配存储空间，只要有就可以分配，元素个数不受限制|

+ **静态链表：**

  &emsp;&emsp;用数组描述的链表叫做静态链表。这种链表在初始时必须分配足够的空间，也就是空间大小是静态的，在进行插入和删除时则不需要移动元素，修改指针域即可，所以仍然具有链表的主要优点（快速插入和删除）。

+ **静态单链表的结构：**

  ```java
  #define MAXSIZE 1000;

  typedef struct {
    ElemType data; // 数据域
    int cur; // 游标
  }component,SLinkList[MAXSIZE];
  ```

+ **静态链表优缺点：**

  |优点|缺点|
  |:--:|:--:|
  |在插入和删除操作时，只需要修改游标，不需要移动元素，从而改进了在顺序存储结构中的插入和删除操作需要移动大量元素的缺点|没有解决连续存储分配带来的表长难以确定的问题；失去了顺序存储结构随机存取的特性。|

+ **循环链表：**

  &emsp;&emsp;循环链表（Circular Linked List）是指将单链表中终端结点的指针端由空指针改为指向头结点，使整个单链表头尾相接形成一个环。

  &emsp;&emsp;循环链表和单链表的主要差异就在于循环的判断条件上，原来是判断 p->next 是否为空，现在则是 p->next 等于头结点，则循环结束。

+ **双向链表：**

  &emsp;&emsp;双向链表（Double Linked List）是在单链表的每个结点中，再设置一个指向其前驱结点的指针域。所以在双向链表中的结点都有两个指针域，一个指向直接后继，另一个直接指向直接前驱。

## 四、栈与队列（Stack And Queue）

+ **栈：**

  &emsp;&emsp;栈（stack）是限定仅在表尾进行插入和删除操作的线性表。将允许插入和删除的一端称为 **栈顶（top）**，另一端称为 **栈底（bottom）**，不含任何数据元素的栈称为 **空栈**。栈又称为后进先出（Last In First Out）的线性表，简称 **LIFO** 结构。

+ **栈的操作：**

  1. 栈的插入操作：叫做进栈 / 压栈 / 入栈（push）。
  
  2. 栈的删除操作：叫做出栈（pop）。

+ **栈的顺序存储结构：**

&emsp;&emsp;既然栈是线性表的特例（简称：顺序栈），以数组下标为 0 的一端作为栈底，因为首元素都存在栈底，变化最小。

+ **栈的链式存储结构：**

&emsp;&emsp;栈的链式存储结构（简称：链栈），将栈顶放在单链表的头部，通常对于链栈来说，是不需要头结点的。

+ **栈的应用：**

&emsp;&emsp;递归：斐波拉契数列的实现（Fibonacci）。

&emsp;&emsp;后缀（逆波兰 Reverse Polish Notation）表示法 — 四则运算表达式求值。比如**中缀表达式：** `9 + （3 - 1） * 3 + 10 / 2`，**后缀表达式为：** `9 3 1 - 3 * + 10 2 / +`。

+ **递归：**

&emsp;&emsp;把一个直接调用自己或通过一系列的调用语句间接地调用自己的函数，称为递归函数。
