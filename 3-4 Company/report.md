---
header-includes:
    - \usepackage{ctex}
---

# 3-4 Company 解题报告

## 原理

员工编号范围 $n$ 较大，但允许的员工数量 $\mathcal{O}(m)$ 较小，从而通过哈希将员工编号映射到较小的空间即可用普通数组存储。

## 遇到的问题

如何快速进行“所有员工注销”操作。朴素的算法是 $\mathcal{O}(m)$。用校验环的方法优化：将已登录员工的代码储存在一个栈中，并引入一个辅助栈，记录每个位置对应的员工编号的哈希。执行“所有员工注销”操作，只需将栈顶置零($\mathcal{O}(1)$)，这样辅助栈中记录的信息即失效。

## 复杂度分析

- 时间复杂度：每个操作都是 $\mathcal{O}(1)$，总共$\mathcal{O}(m)$。   

- 空间复杂度：哈希表、记录员工在代码栈中位置的数组、代码栈、校验栈，都是$\mathcal{O}(m)$，总共$\mathcal{O}(m)$。