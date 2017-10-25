#第五章

##5.4

这道题与前面讲的二极管平衡电路唯一的不同点为输入电压$u_1$和控制电压$u_2$互换了位置。这样带来的影响有两个：

1.  $g_1 \ne g_2$。这是因为控制电压$u_2$被放到了左边，而$u_1$太小，无法控制二极管的通断。
2.  $u_{D2} = u_1 - u_2$。在原来的二极管平衡电路中，$u_{D2} = u_2 - u_1$，但是在这道题中需要把$u_1$和$u_2$换个位置。


用同样的方法分析这道题，得到：

$$i_1 = g_1(t)u_{D1} = g_DK(\omega_2 t)(u_1+u_2)$$，

$$i_2 = g_2(t) u_{D2} = g_DK(\omega_2 t - \pi) (u_1 - u_2)$$

假设两个变压器的匝数比都是1，则有$i_{L1} = i_1$，$i_{L2} = i_2$。

因此负载上的电流

$$\begin{align}i_L &= i_{L1} - i_{L2} \\ &= i_1 - i_2 \\ &= g_D  K(\omega_2) (u_1+u_2) - g_DK(\omega_2 t - \pi) (u_1 - u_2) \\ &= g_D \left\{ \left[ K(\omega_2 t) - K(\omega_2t - \pi) \right] u_1 + \left[ K(\omega_2 t) + K(\omega_2 t - \pi) \right] u_2 \right\} \end{align}$$

因为$$K(\omega_2 t) - K(\omega_2 t - \pi) = K'(\omega_2 t)$$，$$K(\omega_2 t) + K(\omega_2 t - \pi) = 1$$，因此

$$i_L = g_D (K'(\omega_2 t) + u_2)$$

又因为将$$K'(\omega_2 t)$$用泰勒展开后为[^1]

$$K'(\omega_2 t) = \frac 4 \pi \cos \omega_2 t - \frac 4 {3\pi} \cos 3 \omega_2 t + \frac 4 {5\pi} \cos 5 \omega_2 t + \cdots \\ + (-1)^{n+1} \frac 4 {(2n+1) \pi} \cos (2n+1) \omega_2 t + \cdots$$

所以$$i_L = g_D[(\frac 4 \pi \cos \omega_2 t - \frac 4 {3\pi} \cos 3 \omega_2 t + \frac 4 {5\pi} \cos 5 \omega_2 t + \cdots)U_1 \cos \omega_1 t + U_2 \cos \omega_2 t]$$

$$u_o (t) = i_L R_L$$

与153页的式（5 - 44）相比，少了$\omega_1$分量，多了$\omega_2$分量，其它频率分量的振幅是后者的两倍。

##5-5

分析方法同上一题，

$$u_{D1} =  u_{D2} = u_1 + u_2$$

$$i_1 = g_1(t)u_{D1} = g_D K(\omega_2 t) (u_1 + u_2)$$，$$i_2 = g_2(t)u_{D2} = g_D K(\omega_2 t - \pi)(u_1+u_2)$$

$$\begin{align}i_L &= i_1 - i_2 \\ &= g_D (u_1 + u_2) (K(\omega_2 t) - K(\omega_2 t - \pi)) \\ &= g_D(u_1 + u_2)K'(\omega_2 t) \\ &= g_D(U_1 \cos \omega_1 t + U_2 \cos \omega_2 t) ( \frac 4 \pi \cos \omega_2 t - \frac 4 {3\pi} \cos 3\omega_2 t + \cdots) \end{align}$$

接着利用积化和差公式，可以分析出$i_L$中的频率分量为$(2n + 1) \omega_2 \pm \omega_1$，$2n \omega_2$，其中$n = 0, 1, 2, \cdots$。与153页的式子相比，少了$\omega_1$分量，多了$2n\omega_2$分量。

## 5-9

由时变跨导$g_m(t)$的定义[^2]可得，

$$g_m(t) = \frac {di_D} {du_{GS}} = - \frac {2I_{DSS}} {V_p} (1 - \frac {u_{GS}} {V_p})$$

当$u_{GS} = 0$时，有$$g_{m0} = - \frac {2 I_{DSS}}{V_p}$$，（$V_p \lt 0$ ）

当$u_{GS} = E_{GS} + u_2$时，有$$g_m(t) = - \frac {2I_{DSS}} {V_p} (1 - \frac{E_{GS}} {V_p}) + \frac {2I_{DSS}} {V_p} \cdot \frac {u_2} {V_p}$$

将$g_{m0}$代入，得$$g_m(t) = g_{m0} (1 - \frac {E_{GS}}{V_p}) - g_{m0} \frac {u_2} {V_p}$$

当$u_2 = U_2 \cos \omega_2 t$，$E_{GS} = V_p / 2$时，$$g_m(t) = \frac 1 2 g_{m0} - g_{m0} \frac {U_2}{V_p} \cos \omega_2 t$$

由此可知，$$g_{m1} = g_{m0} \frac {U_2}{|V_p|}$$，静态工作点跨导$$g_{mG} = \frac 1 2 g_{m0}$$

当$U_2 = |V_p - E_{GS}|$，$E_{GS} = V_p / 2$时，由上式得$$g_{m1} = \frac 1 2 g_{m0}$$

因此$g_{m1}$为静态工作点跨导。

## 注释

[^1]: 这个展开式在书上156页
[^2]: 原始定义在书上148页，$g(t) = f'(E_Q + U_2 \cos \omega_2 t)$。在场效应管的频谱搬移电路那一节，这个字母多加了一个m，不知道这个m是什么意思。但是定义和原来基本相同，即$$g_m = \frac {d i_D} {du_{GS}}$$。

 