#### 梯度下降

##### 梯度：

$\nabla=\frac{\mathrm{d}f(\theta)}{\mathrm{d}\theta}$，某一函数沿某点处的方向导数可以最快到达极值点，即函数在该方向变化最快。

- 对于单变量，$f(x)=\frac{1}{2}x^2+2x+1\rightarrow\nabla{x}=\frac{\partial{f(x)}}{\partial{x}}=x+2$
- 对于多变量，$f(\theta)=2\theta_1^2+\theta_2^3+3\theta_3^4\rightarrow\nabla\theta=(4\theta_1, 3\theta_2^2, 12\theta_3^3),\theta=(\theta_1,\theta_2,\theta_3)$

##### 迭代公式：

$x^{(i+1)}=x^i-\eta\nabla{f(x^i)}$，其中$\eta$代表学习速率或步长。

- 步长太大，迭代过快，可能无法收敛，甚至发散，导致错过最优解。
- 步长太小，迭代过慢，寻找最优解的时间过长。

##### 推导：

1. 一阶泰勒展开

   $$f(x)\approx{f(x^k)}+(x-x^k)·\nabla{f(x^k)}\approx{f(x^k)}+\lambda\vec{e}\nabla{f(x^k)}$$，其中$\lambda=||x-x^k||$，$\vec{e}$为$x-x^k$的单位向量。

2. 希望函数值$f(x)$变小且越小越好，则$f(x)<f(x^k)$，

   且$f(x)-f(x^k)\approx{\lambda}\vec{e}\nabla{f(x^k)}<0$，又$\lambda$为向量的模的绝对值，$\lambda>0$，

   有$\vec{e}\nabla{f(x^k)}<0$

   3. 讨论$\vec{e}\nabla{f(x^k)}<0$

      因为$\vec{e}$为$x-x^k$的单位向量，$\nabla{f(x^k)}$也为一个向量，要使$\vec{e}\nabla{f(x^k)}$最小，则$\vec{e}$与$\nabla{f(x^k)}$方向相反，即由$\vec{a}·\vec{b}=||\vec{a}||·||\vec{b}||·\cos{\alpha}$，$\alpha$为$\vec{a}$，$\vec{b}$夹角，当$\alpha={180}^\text{o}$时，$\cos{\alpha}=-1$，推出：

      $$\vec{e}=-\frac{\nabla{f(x^k)}}{||\nabla{f(x^k)}||}$$

4. $x=x^k-\lambda\frac{\nabla{f(x^k)}}{||\nabla{f(x^k)}||}$，简化有$x^{(i+1)}=x^i-\eta\nabla{f(x^i)}$，其中$\eta=\frac{\lambda}{||\nabla{f(x^k)}||}$，可以后期自己调整。