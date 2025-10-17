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

(a)

$T(s) = \frac{\frac{s+2}{(s+8)(s-3)s}}{1 + \frac{s+2}{(s+8)(s-3)s}} = \frac{\frac{s+2}{s^3 + 5s^2 - 24s}}{\frac{s^3 + 5s^2 - 23s + 2}{s^3 + 5s^2 - 24s}} = \frac{s+2}{s^3 + 5s^2 - 23s + 2}$

(b)

$T(s) = \frac{Y(s)}{R(s)} = \frac{s+2}{s^3 + 5s^2 - 23s + 2} \cdot \frac{Z(s)}{Z(s)}$

$Y(s) = (s+2) \cdot Z(s)$

$R(s) = (s^3 + 5s^2 - 23s + 2) \cdot Z(s)$

$y(t) = \dot{z}(t) + 2z(t)$

$r(t) = \dddot{z}(t) + 5\ddot{z}(t) - 23\dot{z}(t) + 2z(t)$

$$
x(t) = \begin{bmatrix}
x_1(t) \\
x_2(t) \\
x_3(t) \\
\end{bmatrix} =
\begin{bmatrix}
z(t) \\
\dot{z}(t) \\
\ddot{z}(t) \\
\end{bmatrix} =
\begin{bmatrix}
x_1(t) \\
x_2(t) \\
x_3(t) \\
\end{bmatrix} \\
$$

by r(t)

$\dot{x}_3(t) = \dddot{z}(t)$

$= r(t) - 2z(t) + 23\dot{z}(t) - 5\ddot{z}(t)$

$= r(t) - 2x_1(t) + 23x_2(t) - 5x_3(t)$

by y(t)

$y(t) = 2x_1(t) + x_2(t)$

thus, state variable model is

$$
\dot{X}(t) =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-2 & 23 & -5 \\
\end{bmatrix} x(t) +
\begin{bmatrix}
0 \\
0 \\
1 \\
\end{bmatrix} r(t)
$$

$$
y(t) = \begin{bmatrix}
2 & 1 & 0 \\
\end{bmatrix} x(t)
$$


---
### 3.12

(a)

$T(s) = \frac{Y(s)}{R(s)} = \frac{8s+40}{s^3 + 12s^2 + 44s + 48} \cdot \frac{Z(s)}{Z(s)}$

$Y(s) = (8s+40) \cdot Z(s)$

$R(s) = (s^3 + 12s^2 + 44s + 48) \cdot Z(s)$

$y(t) = 8\dot{z}(t) + 40z(t)$

$r(t) = \dddot{z}(t) + 12\ddot{z}(t) + 44\dot{z}(t) + 48z(t)$

$$
x(t) = \begin{bmatrix}
x_1(t) \\
x_2(t) \\
x_3(t) \\
\end{bmatrix} =
\begin{bmatrix}
z(t) \\
\dot{z}(t) \\
\ddot{z}(t) \\
\end{bmatrix} =
\begin{bmatrix}
x_1(t) \\
x_2(t) \\
x_3(t) \\
\end{bmatrix} \\
$$

by r(t)

$\dot{x}_3(t) = \dddot{z}(t)$

$= r(t) - 48z(t) - 44\dot{z}(t) - 12\ddot{z}(t)$

$= r(t) - 48x_1(t) - 44x_2(t) - 12x_3(t)$

by y(t)

$y(t) = 40x_1(t) + 8x_2(t)$

thus, state variable model is

$$
\dot{X}(t) =
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-48 & -44 & -12 \\
\end{bmatrix} x(t) +
\begin{bmatrix}
0 \\
0 \\
1 \\
\end{bmatrix} r(t)
$$

$$
y(t) = \begin{bmatrix}
40 & 8 & 0 \\
\end{bmatrix} x(t)
$$

(b)

$$
\Phi(s) = [sI - A]^{-1} =
\left(
\begin{bmatrix}
s & 0 & 0 \\
0 & s & 0 \\
0 & 0 & s \\
\end{bmatrix} -
\begin{bmatrix}
0 & 1 & 0 \\
0 & 0 & 1 \\
-48 & 44 & -12 \\
\end{bmatrix} 
\right) ^{-1} =
\begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s + 12 \\
\end{bmatrix}^{-1}
$$

이 때, 
$A^{-1} = \frac{1}{\det A} \left[ C_{ij} \right]^T$

$$
det\begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s + 12 \\
\end{bmatrix} = s
\left| \begin{matrix} s & -1 \\ 44 & s + 12 \end{matrix} \right|
- (-1)
\left| \begin{matrix} 0 & -1 \\ 48 & s + 12 \end{matrix} \right|
= s(s(s+12) + 44) + (0 + 48)
= s^3 + 12s^2 + 44s + 48


$$
det \begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s + 12 \\
\end{bmatrix}
$$

$$
= \frac{1}{
s^3 + 12s^2 + 44s + 48
}
\begin{bmatrix}
s^2 + 125s + 44 & s + 12 & 1 \\
-48 & s^2 + 12s & s \\
-485 & -445 - 48 & s^2
\end{bmatrix}
$$

$$
G(s) = C \Phi(s) B + D
$$

$$
= 
\begin{bmatrix}
40 & 8 & 0
\end{bmatrix}
\frac{1}{
s^3 + 125s^2 + 445s + 48
}
\begin{bmatrix}
s^2 + 125s + 44 & s + 12 & 1 \\
-48 & s^2 + 12s & s \\
-485 & -445 - 48 & s^2
\end{bmatrix}
\begin{bmatrix}
0 \\ 0 \\ 1
\end{bmatrix}
$$

$$
= \frac{1}{s^3 + 125s^2 + 445s + 48}
\left[
40 \; 8 \; 0
\right]
\begin{bmatrix}
s^2 + 125s + 44 & s + 12 & 1 \\
-48 & s^2 + 12s & s \\
-48s & -44s - 48 & s^2
\end{bmatrix}
\begin{bmatrix}
0 \\ 0 \\ 1
\end{bmatrix}
$$

$$
= \frac{1}{s^3 + 125s^2 + 445s + 48}
\begin{bmatrix}
405s^2 + 480s + 1376 & 8s^2 + 136s + 480 & 8s + 40
\end{bmatrix}
\begin{bmatrix}
0 \\ 0 \\ 1
\end{bmatrix}
$$

$$
= \frac{85140}{s^3 + 125s^2 + 445s + 48}
$$



$$
[C_{ij}] =
\begin{bmatrix}
s(s+12) + 44 & -(0+48) & 0 - 485 \\
-(s^2 + 12s - 0) & s(s+12) - 0 & -(445 + 48) \\
1 - 0 & -(s - 0) & s^2 - 0 \\
\end{bmatrix} =
\begin{bmatrix}
s^2 + 12s + 44 & -48 & -485 \\
-(s^2 + 12s) & s^2 + 12s & -445 - 48 \\
1 & -s & s^2 \\
\end{bmatrix}
$$

$$
[C_{ij}]^T =
\begin{bmatrix}
s^2 + 12s + 44 & s + 12 & 1 \\
-48 & s^2 + 12s & s \\
-485 & -445 - 48 & s^2 \\
\end{bmatrix}
$$

$$
therefore 
\Phi(s) = [sI - A]^{-1} = 
\begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s+12 \\
\end{bmatrix}^{-1}
$$

$$
\Phi(s) = [sI - A]^{-1} =
\begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s + 12
\end{bmatrix}^{-1}
$$

$$
= \frac{1}{\det
\begin{bmatrix}
s & -1 & 0 \\
0 & s & -1 \\
48 & 44 & s + 12
\end{bmatrix}
}
\left[ C_{ij} \right]^T
$$

$$
= \frac{1}{
s^3 + 125s^2 + 445s + 48
}
\begin{bmatrix}
s^2 + 12s + 44 & s + 12 & 1 \\
-48 & s^2 + 12s & s \\
-48s & -44s - 48 & s^2
\end{bmatrix}
$$

$$
G(s) = C \Phi(s) B + D
$$



$$
= \frac{1}{s^3 + 12s^2 + 44s + 48}
\left[
40 \; 8 \; 0
\right]
\begin{bmatrix}
s^2 + 12s + 44 & s + 12 & 1 \\
-48 & s^2 + 12s & s \\
-48s & -44s - 48 & s^2
\end{bmatrix}
\begin{bmatrix}
0 \\ 0 \\ 1
\end{bmatrix}
$$

$$
= \frac{1}{s^3 + 125s^2 + 445s + 48}
\begin{bmatrix}
40s^2 + 480s + 1376 & 8s^2 + 136s + 480 & 8s + 40
\end{bmatrix}
\begin{bmatrix}
0 \\ 0 \\ 1
\end{bmatrix}
$$

$$
= \frac{8s+40}{s^3 + 12s^2 + 44s + 48}
$$















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

let 

$s-1=a, s-3=b, s-10=c$

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


$$
= a\begin{vmatrix} 
b & 0 \\ 
-1 & c \\
\end{vmatrix} - 
(-1) \begin{vmatrix}
-4 & 0 \\
2 & c \\
\end{vmatrix} + 
1 \begin{vmatrix} 
-4 & b \\ 
2 & -1 \\ 
\end{vmatrix}
$$

$= abc - 4c + 4 - 2b$

$= (s-1)(s-3)(s-10) - 4(s-10) + 4\cdot2(s-3)$

$= (s^2-4s+3)(s-10) - 4s + 40 + 4 - 2s + 6$

$= s^3-14s^2+31s+20$

$$
\left[ C_{ij} \right] =
\begin{bmatrix}
+(bc-0) & -(-4c-0) & +(4-2b) \\
-(-c+1) & +(ac-2) & -(-a+2) \\
+(0-b) & -(0+4) & +(ab-4) \\
\end{bmatrix} =
\begin{bmatrix}
bc & 4c & 4-2b \\
c-1 & ac-2 & a-2 \\
-b & -4 & ab-4 \\
\end{bmatrix}
$$

$$
\left[ C_{ij} \right]^{T} =
\begin{bmatrix}
bc & c-1 & -b \\
4c & ac-2 & -4 \\
4-2b & a-2 & ab-4 \\
\end{bmatrix}
$$

$G(s) = C(sI-A)^{-1}B$

$$
=\begin{bmatrix}
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
=\begin{bmatrix}
1 & 0 & 0 \\
\end{bmatrix}
\begin{bmatrix}
s-1 & -1 & 1 \\
-4 & s-3 & 0 \\
2 & -1 & s-10 \\
\end{bmatrix}^{-1}
\begin{bmatrix}
0 \\
0 \\
4 \\
\end{bmatrix}
$$

$$
=\begin{bmatrix}
1 & 0 & 0 \\
\end{bmatrix}
\frac{1}{s^3-14s^2+37s+20}
\begin{bmatrix}
bc & c-1 & -b \\
4c & ac-2 & -4 \\
4-2b & a-2 & ab-4 \\
\end{bmatrix}
\begin{bmatrix}
0 \\
0 \\
4 \\
\end{bmatrix}
$$

$$
= \frac{1}{s^3-14s^2+37s+20}
\begin{bmatrix}
1 & 0 & 0 \\
\end{bmatrix}
\begin{bmatrix}
bc & c-1 & -b \\
4c & ac-2 & -4 \\
4-2b & a-2 & ab-4 \\
\end{bmatrix}
\begin{bmatrix}
0 \\
0 \\
4 \\
\end{bmatrix}
$$

$$
= \frac{1}{s^3-14s^2+37s+20}
\begin{bmatrix}
bc & c-1 & -b \\
\end{bmatrix}
\begin{bmatrix}
0 \\
0 \\
4 \\
\end{bmatrix}
$$

$= \frac{1}{s^3-14s^2+37s+20} \times -4b = \frac{-4s+12}{s^3-14s^2+37s+20}$

$G(s) = \frac{-4s+12}{s^3-14s^2+37s+20}$



































