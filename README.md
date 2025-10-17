# ctrl_week6_assignment

### 전기공학과 2019732047 박성훈
---
### 3.1

$M \frac {d^2y(t)} {dt^2} + b \frac {dy(t)} {dt} + ky(t) = F(t)$

(a)

$x_1(t) = y(t)$ , $x_2(t) = \frac {dy(t)} {dt}$

(b)

$\frac {dx_1(t)} {dt} = x_2(t)$

$\frac {dx_2(t)} {dt} = - \frac {b} {M} x_2(t) - \frac {k} {M} x_1(t) + \frac {1} {M} F(t)$

(c)

$$
\dot{X}(t) =
\begin{vmatrix}
\dot{x}_1(t)\\
\dot{x}_2(t)\\
\end{vmatrix} =
\begin{vmatrix}
0 & 1\\
-\frac{k}{M} & -\frac{b}{M}\\
\end{vmatrix}
\begin{vmatrix}
x_1(t)\\
x_2(t)\\
\end{vmatrix} +
\begin{vmatrix}
0\\
\frac{1}{M}\\
\end{vmatrix} F(t)
$$

$$y(t) = 
\begin{vmatrix}
1\\
0\\
\end{vmatrix}
\begin{vmatrix}
x_1(t)\\
x_2(t)\\
\end{vmatrix} +
0 \times F(t)
$$

---

### 3.3

using KVL at outer loop

$v_1(t) = L \frac{di_L(t)}{dt} - v_c(t) + v_2(t)$

using KCL at node



using KVL at right loop




