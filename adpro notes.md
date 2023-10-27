# 写在前面
Congratulations！
哦，小南瓜派，恭喜你进入probability的世界。这是一个神奇的魔法森林，在这里，你能遇见数不清的notions，看不完的定理，写不完的证明以及更多的无从下手的困惑。但是，既来之，则安之。在接下来的路上，还有无数美丽的风景和不知在哪个角落就会突然蹦出的惊喜，以及烧脑好几天，一个瞬间的“原来如此”就好像得到了一颗糖。
Anyway,出发吧，祝你好运！


# Introduction

A probability space $\color{red}{(\Omega,\mathcal{F},\mathbb{P})}$ is a **non-empty** set $\Omega$ with a $\sigma$-algebra $\mathcal{F}$ and a probability measure $\mathbb{P}$.The $\sigma$-algebra $\mathcal{F}$ is a collection of subsets of $\Omega$ such that 
1.$\empty\in\mathcal{F}$
2.if $A\in\mathcal{F}$,then $A^c\in\mathcal{F}$
3.if $A_n\in\mathcal{F},n\in\mathbb{N}$,then $\cup_{n\in\mathbb{N}}A_n\in\mathcal{F}$
The elements of $\mathcal{F}$ are called events.
>trivial $\sigma$-algrbra:$\{\empty,\Omega\}$,the richest one is $2^{\Omega}$(i.e.the collection of all subsets of $\Omega$)
>
The **probability measure** $\mathbf{P}$ is a function from $\mathcal{F}$ into $[0,1]$,such that 
1.$\mathbf{P}(\Omega)=1$
2.if $A_n,n\in\mathbb{N}$ are $\colorbox{yellow}{disjoint}$ sets from $\mathcal{F}$,then
$$
\mathbf{P}(\cup_{n\in\mathbb{N}}A_n)=\sum_{n=1}^{\infty}\mathbf{P}(A_n)\tag{1}
$$
From (1.1),we could get $\mathbf{P}$ is $\sigma$-additive.
Assume that
$$
\mathbf{P}(A\cup B)=\mathbf{P}(A)+\mathbf{P}(B)
$$ 
for disjoint events $A$ and $B$, then $\mathbf{P}$ is called $\color{red}{\text{finitely additive}}$.
>A measure $\mu$ is called finite if $\mu(\Omega)<\infty$

>Definition[random variable]:a function $\xi:\Omega\to\mathbb{R}$ such that $\{\omega\in\Omega:\xi(\omega)\leq t\}\in\mathcal{F}$ for all $t\in\mathbb{R}$.

The cumulatibe distribution function of $\xi$ is defined as
$$
F(t):=\mathbf{P}\{\omega\in\Omega:\xi(\omega)\leq t\}=:\mathbf{P}\{\xi\leq t\}
$$

Let $X$ be a space,where the random elements take their values.Consider a $\sigma$-algebra $\mathcal{L}$ on $X$.The pair $(X,\mathcal{L})$ is called a measureable space.

>Definition[Random element]
A function $\xi:\Omega\to X$ is called random element if $\{\xi\in A\}:=\{\omega\in\Omega:\xi(\omega)\in A\}\in\mathcal{F}$ for all $A\in\mathcal{L}$.
If $X$ is the real line with its Borel $\sigma$-algebra,we obtain the usual definition of a random variable. 
>
-random vectors: random elements in the space $\mathbb{R}^d$ with its Borel $\sigma$-algebra;
-random sequences:random elements in the space $\mathbb{R}^N$;
-random continuous functions:random elements in the space $C(A)$ of continuous functions from $A$ to $\mathbb{R}$;
-random matrices:random elements taking values in a space of matrices;
>
>[distribution of $\xi$]:the measure $\mu$ on $(X,\mathcal{F})$ defined by
$$
\mu(A):=\mathbf{P}\{\xi\in A\}:=\mathbf{P}\{\omega\in\Omega:\xi(\omega)\in A \}
$$
It is the image of $\mathbf{P}$ under the map $\xi$.

> Themorem 1.3
Let $\mu$ be a probability measure on $(X,\mathcal{L})$. Then there exists a probability space $(\Omega,\mathcal{F},\mathbf{P})$ and a random element $\xi$ with values in $X$ such that $\mu$ is the distribution of $\xi$.

Two random elements $\xi$ and $\eta$ are identically distributed ($\xi\sim\eta)$ if $\mathbf{P}\{\xi\in A\}=\mathbf{P}\{\eta\in A\}$ for all measurable sets $A$.

# Borel Cantelli Lemma


##  Reminder
Let $a_n,n\geq 1$ be a sequence of **non-negative** numbers.Then writing that $\sum_{n\geq 1}a_n < +\infty $ exactly means that 
$$
\lim_{N\to\infty}\sum_{n\geq N} a_n=0
$$
which is stronger than $\lim_{n\to\infty}a_n=0$.This last condition does indeed not guarantee that $\sum_{n\geq 1}a_n<+\infty$.

>Lemma (Borel-Cantelli)
Let  $A_1,A_2,...$ be events and let
$A=limsup A_n=\cap_{n=1}^{\infty}\cup_{m=n}^{\infty}A_m$
be the event that occurs if infinitely many events $A_1,A_2,...$ occur,this event is also denoted by $\{A_n,i.o\}$.Then the following statments hold:
  If $\sum\mathbf{P}(A_n)<\infty$,then $\mathbf{P}(A)=0$
  If events $A_1,A_2,...$ are independent and $\sum\mathbf{P}(A_n)=\infty$,then $\mathbf{P}(A)=1$
>> which means
Let $(A_n,n\geq 1)$ be a sequence of events in $\mathcal{F}$ such that $\sum_{n\geq 1}\mathbb{P}(A_n)<+\infty$ Then
$\mathbb{P}(\{\omega\in\Omega:\omega\in A_n \text{infinity often}\})=0
$
>> *Proof*: 