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
\begin{bmatrix}
\dot{x}_1(t)\\
\dot{x}_2(t)\\
\end{bmatrix} =
\begin{bmatrix}
0 & 1\\
-\frac{k}{M} & -\frac{b}{M}\\
\end{bmatrix}
\begin{bmatrix}
x_1(t)\\
x_2(t)\\
\end{bmatrix} +
\begin{bmatrix}
0\\
\frac{1}{M}\\
\end{bmatrix} F(t)
$$

$$y(t) = 
\begin{bmatrix}
1\\
0\\
\end{bmatrix}
\begin{bmatrix}
x_1(t)\\
x_2(t)\\
\end{bmatrix} +
0 \times F(t)
$$

---

### 3.3

using KVL at outer loop

$v_1(t) = L \frac{di_L(t)}{dt} - v_c(t) + v_2(t)$

using KCL at node

$i_L(t) = -C \frac{dV_C(t)}{dt} + i_R(t)$

using KVL at right loop

$i_R(t) \times R = -V_C(t) + V_2(t)$

$i_R(t) = - \frac {1}{R} V_C(t) + \frac {1}{R}V_2(t)$


from those,

$v_1(t) = L \frac{d i_L(t)}{dt} - v_C(t) + v_2(t)$

$i_L(t) = -C \frac{d v_C(t)}{dt} + i_R(t)$

$\frac{d i_L(t)}{dt} = \frac{1}{L} v_1(t) + \frac{1}{L} v_C(t) - \frac{1}{L} v_2(t)$

$\frac{d v_C(t)}{dt} = -\frac{1}{C} i_L(t) + \frac{1}{C} i_R(t) = -\frac{1}{C} i_L(t) - \frac{1}{RC} v_C(t) + \frac{1}{RC} v_2(t)$


$x_1(t) = i_L(t), x_2(t) = V_c(t)$

$$
X(t) = 
\begin{bmatrix}
x_1(t) \\
x_2(t) \\
\end{bmatrix} =
\begin{bmatrix}
i_L(t) \\
v_c(t) \\
\end{bmatrix}
$$

$$
\dot{X}(t) =
\begin{bmatrix}
\dot{x}_1(t) \\
\dot{x}_2(t) \\
\end{bmatrix} =
\begin{bmatrix}
0 & \frac{1}{L} \\
-\frac{1}{C} & -\frac{1}{RC} \\
\end{bmatrix}
\begin{bmatrix}
x_1(t) \\
x_2(t) \\
\end{bmatrix} +
\begin{bmatrix}
\frac{1}{L} & -\frac{1}{L} \\
0 & \frac{1}{RC} \\
\end{bmatrix}
\begin{bmatrix}
v_1(t) \\
v_2(t) \\
\end{bmatrix}
$$

---
### 3.5


---
### 3.12

---
### 3.17

$G(s) = C(sI-A)^{-1}B$

$$
\begin{bmatrix}
1 & 0 & 0 \\
\end{bmatrix}
\left(
\begin{bmatrix}
s & 0 & 0 \\
0 & s & 0 \\
0 & 0 & s \\
\end{bmatrix} -
\begin{bmatrix}
1 & 1 & -1 \\
4 & 3 & 0 \\
-2 & 1 & 10 \\
\end{bmatrix} 
\right) ^{-1}
\begin{bmatrix}
0 \\
0 \\
4 \\
\end{bmatrix}
$$

$$
\begin{bmatrix}
1 & 0 & 0 \\
\end{bmatrix}
\begin{bmatrix}
s-1 & -1 & 1 \\
-4 & s-3 & 0 \\
2 & -1 & s-10
\end{bmatrix}^{-1}
\begin{bmatrix}
0 \\
0 \\
4
\end{bmatrix}
$$


이 때, 

$A^{-1} = \frac{1}{\det A} \left[ C_{ij} \right]^T$

$$
det
\begin{bmatrix}
s-1 & -1 & 1 \\
-4 & s-3 & 0 \\
2 & -1 & s-10
\end{bmatrix} =
det
\begin{bmatrix}
a & -1 & 1 \\
-4 & b & 0 \\
2 & -1 & c
\end{bmatrix}
$$
