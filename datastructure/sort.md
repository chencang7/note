# 排序（sort）

## 1、插入排序

- 排序思想：把待排序的元素按其值的大小逐个插入到一个已经排好序的序列中，直到所有的元素插入完为止。

- 优化：二分插入排序

## 2、希尔排序（不会）

- 排序思想：将待排序的数组元素 按下标的一定增量分组 ，分成多个子序列，然后对各个子序列进行直接插入排序算法排序；然后依次缩减增量再进行排序，直到增量为1时，进行最后一次直接插入排序，排序结束。
- 希尔排序的执行时间依赖于增量序列h，好的增量序列的共同特征：
    - 最后一个增量必须为1；
    - 应该尽量避免序列中的值(尤其是相邻的值)互为倍数的情况。
- 希尔排序比插入排序要快的多，并且数组越大，优势越大。
- 是对直接插入排序的一个优化，也称**缩小增量排序**。

## 3、选择排序

- 排序思想：每一次从待排序的数据元素中找出最小（或最大）的一个元素，将它和待排序的元素中第一个位置的元素进行交换，直到全部待排序的数据元素排完程为止。

## 4、堆排序

- 排序思想：利用堆的有序性（根节点最大）来进行排序，每次从堆中取出根节点，并保持堆有序。
- 堆排序是一种选择排序

## 5、冒泡排序

- 排序思想：依次比较相邻的两个元素，若它们的顺序错误则交换，每次循环都将最大（或最小）元素放在序列一端。
- 冒泡排序与选择排序的区别：
    1. 冒泡排序法是两两依次比较，并做交换，交换的次数多。
    2. 选择排序法是每次循环找出最值，循环结束后将最值调整到合适位置，交换的次数少。

## 6、快速排序

- 排序思想：通过一趟排序将要排序的数据切分成独立的两部分，其中一部分的所有数据都比另外一部分的所有数据都要小，然后再按此方法对这两部分数据分别进行快速排序，整个排序过程可以递归进行，以此达到整个数据变成有序序列。

## 7、归并排序

- 自顶向下：要将一个数组排序，可以先（递归的）将它分为两半分别排序，然后将结果归并起来。
- 由于归并排序的方法调用过于频繁，会产生过多的额外开销，所以归并排序在处理小规模问题时，比插入排序要慢。在用归并排序处理大规模数据时，使用插入排序来处理小规模的子数组，一般可使归并排序的运行时间缩短10%-15%。
- 自底向上：先两两归并（把每个元素当成一个长度为1的数组），在四四归并，然后八八归并，一直下去。每轮归并中最后一次归并的第二个数组可能比第一个小（注意不要越界）。

## 8、计数排序

- 计数排序不是基于比较的排序算法，其核心在于将输入的数据值转化为键存储在额外开辟的数组空间中。 作为一种线性时间复杂度的排序，计数排序要求输入的数据必须是有确定范围的整数。

## 9、桶排序

- 桶排序是计数排序的升级版。它利用了函数的映射关系，高效与否的关键就在于这个映射函数的确定。桶排序 (Bucket sort)的工作的原理：假设输入数据服从均匀分布，将数据分到有限数量的桶里，每个桶再分别排序（有可能再使用别的排序算法或是以递归方式继续使用桶排序进行排）。

## 10、基数排序

- 基数排序基于分别排序，基数排序是按照低位先排序，然后收集；再按照高位排序，然后再收集；依次类推，直到最高位。有时候有些属性是有优先级顺序的，先按低优先级排序，再按高优先级排序。最后的次序就是高优先级高的在前，高优先级相同的低优先级高的在前。
