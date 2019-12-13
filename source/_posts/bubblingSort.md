---
title: 冒泡排序
date: 2017-01-03
categories: 算法
tag: 排序
---

冒泡排序：
---

* 背景介绍： 是一种简单的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。这个算法的名字由来是因为越小的元素会经由交换慢慢“浮”到数列的顶端。----- 来自 [wikipedia](https://zh.wikipedia.org/wiki/%E5%86%92%E6%B3%A1%E6%8E%92%E5%BA%8F) 
* 算法规则： 由于算法每次都将一个最大的元素往上冒，我们可以将待排序集合(0...n)看成两部分，一部分为(k..n)的待排序unsorted集合，另一部分为(0...k)的已排序sorted集合，每一次都在unsorted集合从前往后遍历，选出一个数，如果这个数比其后面的数大，则进行交换。完成一轮之后，就肯定能将这一轮unsorted集合中最大的数移动到集合的最后，并且将这个数从unsorted中删除，移入sorted中。

* 代码实现（Java版本）
```
public void sort(int[] args) 
        {
        	//第一层循环从数组的最后往前遍历
    		for (int i = args.length - 1; i > 0 ; --i) {
                //这里循环的上界是 i - 1，在这里体现出 “将每一趟排序选出来的最大的数从sorted中移除”
    			for (int j = 0; j < i; j++) {
                    //保证在相邻的两个数中比较选出最大的并且进行交换(冒泡过程)
    				if (args[j] > args[j+1]) {
    					int temp = args[j];
    					args[j] = args[j+1];
    					args[j+1] = temp;
    				}
    			}
    		}
	    }
```