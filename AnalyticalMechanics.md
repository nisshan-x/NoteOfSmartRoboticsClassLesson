# 第１週　解析力学の概要、ラグランジュの運動方程式

* [Youtube](https://www.youtube.com/watch?v=kwGFway0duQ)
* [pdf](http:/www.ritsumei.ac.jp/~uemura-m/AnalyticalMechanics/AnalyticalMechanics1stWeek.pdf)

## 力学とは

力に関係した現象を数学的に調べる。

## 力学の分類

* 静力学　：　**力/トルク** と **力/トルク** の関係を調べる
* 動力学　：　**力/トルク** と **運動** の関係を調べる

## 解析力学の概要

**運動方程式(動力学)** を統一的に導出

運動方程式の例

```math
m\ddot{x} = f
```

$\ddot{x}$は運動、fは力を表す

## 運動方程式の用途

* シミュレーション
* 制御の設計
* 運動の解析
* CG・ゲーム

## 解析力学の物理的位置づけ

1. ニュートン力学(1687)
1. 解析力学(1788)
1. 相対性理論(1905)
1. 量子力学(1900)
1. 超弦理論(1960)

## ラグランジュの運動方程式

```math
ポテンシャルエネルギー : U
```

```math
運動エネルギー : K
```

```math
ラグランジアン : L = K - U
```

```math
一般化座標 : \bf{X}
```

```math
ラグランジュの運動方程式 : \frac{d}{dt}(\frac{\partial L}{\partial \dot{\bf{X}}}) - \frac{\partial L}{\partial \bf{X}} = 0
```

ラグランジアンは定義。

### ポテンシャルエネルギー

例： 高さhの位置にある質量mの物体

<img alt="fig" src="figures/lesson-01/fig_01.JPG" width="50%">

```math
U = mgh
```

例： バネ係数kにつながる質量mの物体がxの位置にあるとき

<img alt="fig" src="figures/lesson-01/fig_02.JPG" width="50%">

```math
U = \frac{1}{2}kx^2
```

### 運動エネルギー

例： 速さvで動く、質量mの物体

<img alt="fig" src="figures/lesson-01/fig_03.JPG" width="50%">

```math
K = \frac{1}{2}mv^2

```

### ラグランジュの運動方程式の利点

* 複雑な系でも、統一的な方法で比較的容易に運動方程式を導出できる
* 拘束のある系も取り扱える

### ラグランジュの運動方程式の例　１

質量mの物体が自由落下する。縦方向の位置はx(下向きに正)。

<img alt="fig" src="figures/lesson-01/fig_04.JPG" width="50%">

```math
ポテンシャルエネルギー : U = -mxg \\
```

```math
運動エネルギー : K = \frac{1}{2}m\dot{x}^2 \\
```

```math
ラグランジアン : L = K - U \\
```

```math
座標 : x \\
```

```math
ラグランジュの運動方程式 : \frac{d}{dt}(\frac{\partial L}{\partial \dot{x}}) - \frac{\partial L}{\partial x} = 0
```

$\partial $は偏微分。

ラグランジュの運動方程式を求める。

$L = K - U$より

```math
L = \frac{1}{2}m\dot{x}^2 + mxg
```

$\dot{x}$で偏微分する。

```math
\begin{aligned}
\frac{\partial L}{\partial \dot{x}} &= \frac{\partial (\frac{1}{2}m\dot{x}^2 + mxg)}{\partial \dot{x}} \\
&= \frac{\partial (\frac{1}{2}m\dot{x}^2)}{\partial \dot{x}} + \frac{\partial (mxg)}{\partial \dot{x}} \\
&= \frac{1}{2} \times 2 \times m\dot{x} + 0 \\
&= m\dot{x}
\end{aligned}
```

時間tで全微分する

```math
\begin{aligned}
\frac{d}{dt}(\frac{\partial L}{\partial \dot{x}}) &= \frac{d}{dt}(m\dot{x}) \\
&= m\ddot{x}
\end{aligned}
```

第二項の計算

```math
\begin{aligned}
\frac{\partial L}{\partial x} &= \frac{\partial (\frac{1}{2}m\dot{x}^2 + mxg)}{\partial x} \\
&= \frac{\partial (\frac{1}{2}m\dot{x}^2)}{\partial x} + \frac{\partial (mxg)}{\partial x} \\
&= 0 + mg \\
&= mg
\end{aligned}
```

よってラグランジュの運動方程式は

```math
\begin{aligned}
\frac{d}{dt}(\frac{\partial L}{\partial \dot{x}}) - \frac{\partial L}{\partial x} = 0
\\
m\ddot{x} - mg = 0
\end{aligned}
```

### ラグランジュの運動方程式の例　２

水平な面に置かれた質点ｍの物体がバネにつながっている。バネ係数k、位置は水平方向にx。

<img alt="fig" src="figures/lesson-01/fig_02.JPG" width="50%">

ポテンシャルエネルギー

```math
U = \frac{1}{2}kx^2
```

運動エネルギー

```math
K = \frac{1}{2}m\dot{x}^2
```

ラグランジアン

```math
\begin{aligned}
L &= K - U \\
&= \frac{1}{2}m\dot{x}^2 - \frac{1}{2}kx^2
\end{aligned}
```

ラグランジュの運動方程式を解く。

```math
\begin{aligned}
\frac{d}{dt}(\frac{\partial L}{\partial \dot{x}}) - \frac{\partial L}{\partial x} &= 0 \\
\frac{d}{dt}(\frac{\partial (\frac{1}{2}m\dot{x}^2 - \frac{1}{2}kx^2)}{\partial \dot{x}}) - \frac{\partial (\frac{1}{2}m\dot{x}^2 - \frac{1}{2}kx^2)}{\partial x} &= 0 \\
\frac{d}{dt}(m\dot{x}-0) -  (0 - kx) &= 0 \\
m\ddot{x} -  (0 - kx) &= 0 \\
m\ddot{x} + kx &= 0
\end{aligned}
```

# 第2週　ラグランジュの運動方程式の基礎②、一般化座標

* [Youtube](https://www.youtube.com/watch?v=s1kWqnYJJfQ)
* [pdf](http:/www.ritsumei.ac.jp/~uemura-m/AnalyticalMechanics/AnalyticalMechanics2ndWeek.pdf)

## 質点の運動方程式 (2次元平面)

<img alt="fig" src="figures/lesson-02/fig_01.JPG" width="50%">
(重力はないものとする)

ポテンシャルエネルギー

```math

U = 0
```

運動エネルギー

```math
K = \frac{1}{2}mv^2 = \frac{1}{2}m(\sqrt{\dot{x}^2+\dot{y}^2})^2 = \frac{1}{2}m(\dot{x}^2+\dot{y}^2)
```

ラグランジアン

```math

L = K - U
```

座標

```math
\bf{X} = \begin{pmatrix}
x \\
y
\end{pmatrix}
```

ラグランジュの運動方程式

```math
\begin{aligned}
\frac{d}{dt}(\frac{\partial L}{\partial \dot{\bf{X}}}) - \frac{\partial L}{\partial \bf{X}} &= 0 \\
\frac{d}{dt}(\frac{\partial (\frac{1}{2}m(\dot{x}^2+\dot{y}^2))}{\partial \dot{\bf{X}}}) - \frac{\partial (\frac{1}{2}m(\dot{x}^2+\dot{y}^2))}{\partial \bf{X}} &= 0  \\
\frac{d}{dt}\begin{pmatrix}
\frac{\partial}{\partial \dot{x}} \frac{1}{2}m(\dot{x}^2+\dot{y}^2) \\
\frac{\partial}{\partial \dot{y}} \frac{1}{2}m(\dot{x}^2+\dot{y}^2)
\end{pmatrix} - \begin{pmatrix}
\frac{\partial}{\partial {x}}(\frac{1}{2}m(\dot{x}^2+\dot{y}^2)) \\
\frac{\partial}{\partial {y}}(\frac{1}{2}m(\dot{x}^2+\dot{y}^2))
\end{pmatrix} &= 0  \\
\frac{d}{dt}\begin{pmatrix}
m \dot{x} \\
m \dot{y}
\end{pmatrix} - \begin{pmatrix}
0 \\
0
\end{pmatrix} &= 0  \\
\begin{pmatrix}
m \ddot{x} \\
m \ddot{y}
\end{pmatrix} - \begin{pmatrix}
0 \\
0
\end{pmatrix} &= 0  \\
m \ddot{\bf{X}} &= 0
\end{aligned}
```

## 偏微分、全微分のおさらい

```math
f = 7x(t)+3\dot{x}(t)+4y(x(t))+2t
```

### 偏微分

微分対象の変数以外は定数として微分する

```math
\frac{\partial}{\partial x}f = \frac{\partial}{\partial x}(7x(t)+3\dot{x}(t)+4y(x(t))+2t) = 7
```

```math
\frac{\partial}{\partial t}f = \frac{\partial}{\partial x}(7x(t)+3\dot{x}(t)+4y(x(t))+2t) = 2
```

### 全微分

```math
\frac{d}{dt}f = \frac{d}{dt}(7x(t)+3\dot{x}(t)+4y(x(t))+2t) = 7\dot{x}+3\ddot{x}+4\frac{\partial y}{\partial x}+2
```

## 演習

次の偏微分・全微分を計算せよ

### ①

```math
\begin{aligned}
\frac{\partial}{\partial x}(ax^2+bx+c) &= 2ax + b\\
\end{aligned}
```

### ②

```math
\begin{aligned}
\frac{\partial}{\partial x}(x \sin x) &= \sin x + x \cos x
\end{aligned}
```

### ③

だたし、aは定数、x,yはtに依存した変数

```math
\begin{aligned}
\frac{d}{dt}axy = a\dot{x}y + ax\dot{y}
\end{aligned}
```

### ④

だたし、xはtに依存した変数

```math
\begin{aligned}
\frac{d}{dt}\sin x = \frac{\partial}{\partial x} \sin x \times \frac{d}{dt}x = \cos x \times \dot{x} = \dot{x} \cos x
\end{aligned}
```

## 一般化座標

一般化座標の定義： 系の位置を決める最小の変数の組

### 3関節ロボット

<img alt="fig" src="figures/lesson-02/fig_02.JPG" width="50%">

* 関節角度ベクトル $(q_1, q_2, q_3)$ は一般化座標
* 手先位置 $(x, y)$ は一般化座標ではない（系の位置を決められない）

### 質点

<img alt="fig" src="figures/lesson-02/fig_03.JPG" width="50%">

* 座標 $(x, y, r, \theta)$ は一般化座標ではない（変数の数が最小ではない）
* ベクトル $(x, y)$ は一般化座標
* 極座標 $(r, \theta)$ も一般化座標

## 自由度

自由度の定義： 系の位置を決めるのに必要な変数の数

### 質点

* 2次元平面： 2自由度
* 3次元平面： 3自由度

### N個の質点系

* 2次元平面： 2N自由度
* 3次元平面： 3N自由度

### 剛体

<img alt="fig" src="figures/lesson-02/fig_04.JPG" width="50%">

* 2次元平面： 3自由度
* 3次元平面： 6自由度

### 拘束なしのロボットアーム

* 関節の数をNとするとN自由度

## 拘束

### 2つの質点が棒で拘束

<img alt="fig" src="figures/lesson-02/fig_05.JPG" width="50%">

拘束条件

```math
\sqrt{(x_1 - x_2)^2 + (y_1 - y_2)^2} = l
```

自由度

```math
2 + 2 - 1 = 3
```

1は↑の拘束条件の数

### ロボットの手先が壁に拘束

<img alt="fig" src="figures/lesson-02/fig_06.JPG" width="50%">

拘束条件

```math
k_y(q_1, q_2, q_3) = y_{kabe}
```

自由度

```math
3 - 1 = 2
```

## ロボットの先端リンクが壁に固定

<img alt="fig" src="figures/lesson-02/fig_07.JPG" width="50%">

手先の $x$ 座標、 $y$ 座標、手先角度 $\theta$ が拘束
自由度

```math
3 - 3 = 0
```

ロボットは動かない。

## 演習

次の系の自由度を求めよう。

<img alt="fig" src="figures/lesson-02/fig_08.JPG" width="50%">

3関節ロボットと2関節ロボットに分割して考える。
左側の手先と右側の手先の $x$ 座標、 $y$ 座標、手先角度 $\theta$ が拘束

自由度

```math
3 + 2 - 3 = 2
```

# 第３週　運動エネルギー

* [Youtube](https://www.youtube.com/watch?v=IV4GuiRr7_Y)
* [pdf](http:/www.ritsumei.ac.jp/~uemura-m/AnalyticalMechanics/AnalyticalMechanics3rdWeek.pdf)

## 運動エネルギーとは

運動エネルギーの定義： 運動する物体が持つエネルギー

<img alt="fig" src="figures/lesson-03/fig_01.JPG" width="50%">

### 質点の運動エネルギー

```math
K = \frac{1}{2}mv^2
```

### $v^2$ の別表現

```math
v^2 = (\sqrt{\dot{x}^2 + \dot{y}^2})^2 = \dot{x}^2 + \dot{y}^2 = \dot{{\bf{X}}}\cdot\dot{{\bf{X}}}
```

## 内積のおさらい

ベクトルaとbの内積
内積の結果はスカラーになる。

```math
\begin{aligned}
{\bf{a}}\cdot{\bf{b}} &= a_1 b_1 + a_2 b_2 \cdots a_n b_n \\
&= (a_1 a_2 \cdots a_n )\begin{pmatrix}
b_1 \\
b_2 \\
\vdots \\
b_n
\end{pmatrix} \\
&= {\bf{a}}^T{\bf{b}} \\
&= \sum_{i=1}^{n} a_i b_i
\end{aligned}
```

↑すべて別表現

## 演習

### 問い

体重60 [kg] の人が、4 [m/s] で走っている。この人が持つ運動エネルギーを答えよ。

### 解答

```math
\begin{aligned}
K = \frac{1}{2}mv^2 = \frac{1}{2} \times 60 \times 4^2 = 480 [J] \\
1 [cal] \fallingdotseq 4 [J] なので、480 [J] \fallingdotseq 120 [J]
\end{aligned}
```

## 剛体の運動エネルギー（2次元）

### 剛体の運動エネルギー

<img alt="fig" src="figures/lesson-03/fig_02.JPG" width="50%">

```math
K = \frac{1}{2}mv_{cm}^2 + \frac{1}{2}I\omega^2
```

$I$ : 慣性モーメント \
$\omega$ : 角速度

**重心の並進運動**と**重心周りの回転運動**に分離可能

### 別表現

<img alt="fig" src="figures/lesson-03/fig_03.JPG" width="50%">

```math
K = \frac{1}{2}m \dot{{\bf{X_{cm}}}}\cdot\dot{{\bf{X_{cm}}}} + \frac{1}{2}I\dot{\theta}^2
```

## 証明：剛体の運動エネルギー（2次元）

剛体を質点の集まりとして考える <br>
↓　これまでの力学の延長線上で考える <br>
重心の並行移動と重心周りの回転を考える <br>
↓ <br>
全質点の運動エネルギーの和

```math
K = \sum_{i=1}^{n}\frac{1}{2}m_iv_i^2
```

↓ <br>
剛体の運動エネルギー

```math
K = \frac{1}{2}mv_{cm}^2 + \frac{1}{2}I\omega^2
```

## 剛体の重心

剛体を質点の集まりとして考える

### 剛体の重心位置

```math
{\bf{X_{cm}}} = \frac{1}{m}\sum_{i=1}^{N}m_i {\bf{X_i}} \\
```

$m$ : 剛体全体の質点 \
$m_i$ : 各質点の質量 \
${\bf{X_i}}$ : 各質点の位置ベクトル

### ２質点系での例

<img alt="fig" src="figures/lesson-03/fig_04.JPG" width="50%">

```math
x_{cm} = \frac{1}{m_1 + m_2}(m_1 x_1 + m_2 x_2) \\
```

## 各質点の位置

<img alt="fig" src="figures/lesson-03/fig_05.JPG" width="50%">

### 各質点の位置 ${\bf{X_i}}$

```math
{\bf{X_i}} = {\bf{X_{cm}}} + \rho_i \\
\rho_i = l_i\begin{pmatrix}
\cos (\theta + \theta_i) \\
\sin (\theta + \theta_i)
\end{pmatrix}
```

$\rho_i$ : 重心から見た位置

### $\rho_i$の性質①

```math
\begin{aligned}
{\bf{X_{cm}}} &= \frac{1}{m}\sum_{i=l}^{N} m_i {\bf{X_i}} \\
&= \frac{1}{m}\sum_{i=l}^{N} m_i {\bf{X_{cm}}} + \frac{1}{m}\sum_{i=l}^{N} m_i {\bf{\rho_i}} \\
&= {\bf{X_{cm}}} \frac{1}{m}\sum_{i=l}^{N} m_i  + \frac{1}{m}\sum_{i=l}^{N} m_i {\bf{\rho_i}} \\

\frac{1}{m}\sum_{i=l}^{N} m_i &= 1 なので \\
&= {\bf{X_{cm}}} + \frac{1}{m}\sum_{i=l}^{N} m_i {\bf{\rho_i}} \\

\therefore \sum_{i=l}^{N} m_i {\bf{\rho_i}} = 0
\end{aligned}
```

### $\rho_i$の性質②

```math
\begin{aligned}
\dot{\rho_i} \cdot \dot{\rho_i} &= l_i^2 \begin{pmatrix}
- \sin (\theta + \theta_i)\dot{\theta} \\
\cos (\theta + \theta_i)\dot{\theta}
\end{pmatrix} \cdot \begin{pmatrix}
- \sin (\theta + \theta_i)\dot{\theta} \\
\cos (\theta + \theta_i)\dot{\theta}
\end{pmatrix} \\
&= l_i^2\dot{\theta^2} \\
&= l_i^2 \omega^2
\end{aligned}
```

## 剛体の運動エネルギーの導出

```math
\begin{aligned}
v_i^2 &= {\bf{\dot{X_i}}} \cdot {\bf{\dot{X_i}}} \\
&= ({\bf{\dot{X_{cm}}}} + {\bf{\dot{\rho_i}}}) \cdot ({\bf{\dot{X_{cm}}}} + {\bf{\dot{\rho_i}}}) \\
&= {\bf{\dot{X_{cm}}}} \cdot {\bf{\dot{X_{cm}}}} +2{\bf{\dot{X_{cm}}}} \cdot {\bf{\dot{\rho_i}}} + {\bf{\dot{\rho_i}}} \cdot {\bf{\dot{\rho_i}}} \\

\dot{{\bf{X_{cm}}}} \cdot \dot{{\bf{X_{cm}}}} &= v_{cm}^2 と \dot{\rho_i} \cdot \dot{\rho_i} = l_i^2 \omega^2 より \\

&= v_{cm}^2 +2{\bf{\dot{X_{cm}}}} \cdot {\bf{\dot{\rho_i}}} + l_i^2 \omega^2 \\
\end{aligned}
```

### 全体の運動エネルギー

```math
\begin{aligned}

K &= \sum_{i=1}^N \frac{1}{2}m_i v_i^2 \\
&= \sum_{i=1}^N \frac{1}{2}m_i (v_{cm}^2 +2{\bf{\dot{X_{cm}}}} \cdot {\bf{\dot{\rho_i}}} + l_i^2 \omega^2) \\
&= \frac{1}{2}\sum_{i=1}^N m_i v_{cm}^2 + {\bf{\dot{X_{cm}}}} \cdot \sum_{i=1}^N m_i {\bf{\dot{\rho_i}}} + \frac{1}{2}\sum_{i=1}^N m_i l_i^2 \omega^2 \\

\sum_{i=1}^N m_i &= m 、 \sum_{i=1}^N m_i {\bf{\dot{\rho_i}}} = 0 、 \sum_{i=1}^N m_i l_i^2 = I より \\

&= \frac{1}{2}mv_{cm}^2 + \frac{1}{2}I \omega^2
\end{aligned}
```

## 慣性モーメント

| 並進運動 | 単位    | 記号         | 回転運動 | 単位       | 記号                |
| ------ | ------- | ----------  | ------- | -----     | ------------------ |
| 位置    |$[m]$   | $x$          |角度     |$[rad]$    |$\theta$             |
| 速度    |$[m/s]$ |$\dot{x}, v$  |角速度    |$[rad/s]$ |$\dot{\theta}, \omega$|
| 加速度  |$[m/s^2]$|$\ddot{x}, a$|角加速度  |$[rad/s^2]$|$\ddot{\theta}$      |
|力      |$[N]$    |$f$           |力のモーメント、<br>またはトルク|$[Nm]$|$\tau$|
|質量     |$[kg]$   |$m$          |慣性モーメント|$[kgm^2]$|$I$|

## 演習

```math
運動エネルギーを K = \frac{1}{2}mv_{cm}^2 + \frac{1}{2}I \dot{\theta}^2 ポテンシャルエネルギーを U = mgy_{cm} とする剛体の運動方程式を求めよ。ただし、座標は {\bf{X}} = \begin{pmatrix}
x_{cm} \\
y_{cm} \\
\theta
\end{pmatrix} とする。
```

<img alt="fig" src="figures/lesson-03/fig_06.JPG" width="50%">

ラグランジアン

```math
\begin{aligned}
L &= K - U \\
&= \frac{1}{2}mv_{cm}^2 + \frac{1}{2}I \dot{\theta}^2 - mgy_{cm} \\

v_{cm}^2 = \dot{x}^2_{cm} + \dot{y}^2_{cm} より  \\

&= \frac{1}{2}m(\dot{x}^2_{cm} + \dot{y}^2_{cm}) + \frac{1}{2}I \dot{\theta}^2 - mgy_{cm} \\


\end{aligned}
```

ラグランジュの運動方程式

```math
\begin{aligned}
\frac{d}{dt}(\frac{\partial L}{\partial \dot{\bf{X}}}) - \frac{\partial L}{\partial \bf{X}} &= 0
\end{aligned}
```

各項を計算する。第一項の偏微分を解く。

```math
\begin{aligned}
\frac{\partial L}{\partial \dot{\bf{X}}} &= \frac{\partial}{\partial \dot{\bf{X}}} (\frac{1}{2}m(\dot{x}^2_{cm} + \dot{y}^2_{cm}) + \frac{1}{2}I \dot{\theta}^2 - mgy_{cm}) \\
&= \begin{pmatrix}
\frac{\partial}{\partial \dot{x}} (\frac{1}{2}m(\dot{x}^2_{cm} + \dot{y}^2_{cm}) + \frac{1}{2}I \dot{\theta}^2 - mgy_{cm}) \\
\frac{\partial}{\partial \dot{y}} (\frac{1}{2}m(\dot{x}^2_{cm} + \dot{y}^2_{cm}) + \frac{1}{2}I \dot{\theta}^2 - mgy_{cm}) \\
\frac{\partial}{\partial \dot{\theta}} (\frac{1}{2}m(\dot{x}^2_{cm} + \dot{y}^2_{cm}) + \frac{1}{2}I \dot{\theta}^2 - mgy_{cm})
\end{pmatrix} \\
&= \begin{pmatrix}
m\dot{x}_{cm}\\
m\dot{y}_{cm}\\
I \dot{\theta}
\end{pmatrix}

\end{aligned}
```

第一項の全微分を解く。

```math
\begin{aligned}
\frac{d}{dt}(\frac{\partial L}{\partial \dot{\bf{X}}}) &= \frac{d}{dt}\begin{pmatrix}
m\dot{x}_{cm} \\
m\dot{y}_{cm} \\
I\dot{\theta}
\end{pmatrix} \\
&= \begin{pmatrix}
m\ddot{x}_{cm} \\
m\ddot{y}_{cm} \\
I\ddot{\theta}
\end{pmatrix}
\end{aligned}
```

第二項の偏微分を解く。

```math
\begin{aligned}
\frac{\partial L}{\partial \bf{X}} &= \frac{\partial }{\partial \bf{X}}(\frac{1}{2}m(\dot{x}^2_{cm} + \dot{y}^2_{cm}) + \frac{1}{2}I \dot{\theta}^2 - mgy_{cm}) \\
&= \begin{pmatrix}
0 \\
-mg \\
0
\end{pmatrix}
\end{aligned}
```

よって、ラグランジュの運動方程式

```math
\begin{aligned}
\frac{d}{dt}(\frac{\partial L}{\partial \dot{\bf{X}}}) - \frac{\partial L}{\partial \bf{X}} &= 0 \\

\begin{pmatrix}
m\ddot{x}_{cm} \\
m\ddot{y}_{cm} \\
I\ddot{\theta}
\end{pmatrix} - \begin{pmatrix}
0 \\
-mg \\
0
\end{pmatrix} &= 0 \\

\begin{pmatrix}
m\ddot{x}_{cm} \\
m\ddot{y}_{cm} \\
I\ddot{\theta}
\end{pmatrix} + \begin{pmatrix}
0 \\
mg \\
0
\end{pmatrix} &= 0 \\
\end{aligned}
```

* 重心は放物運動する
* 重心周りは等速回転運動する

# 第４週　３次元空間を移動する剛体の運動エネルギー

* [Youtube](https://www.youtube.com/watch?v=pLsiqW_BP-0)
* [PDF](http:/www.ritsumei.ac.jp/~uemura-m/AnalyticalMechanics/AnalyticalMechanics4thWeek.pdf)

## 剛体の運動エネルギー（3次元）

## 剛体の運動エネルギー

<img alt="fig" src="figures/lesson-04/fig_01.JPG" width="50%">

```math
K = \frac{1}{2}mv_{cm}^2 + \frac{1}{2}\omega^T I \omega^2
```

```math
\begin{aligned}
{\boldsymbol{\omega}} = \begin{pmatrix}
\omega_x \\
\omega_y \\
\omega_z
\end{pmatrix} : 角速度ベクトル  \\
I = \begin{pmatrix}
I_{xx} & I_{xy} & I_{xz} \\
I_{yx} & I_{yy} & I_{yz} \\
I_{zx} & I_{zy} & I_{zz}
\end{pmatrix} : 慣性テンソル \\
\end{aligned}
```

回転軸によって慣性モーメントが違う
剛体に固定した座標系で考える。

## 重心

### 重心位置 ${\bf{X}}_{cm}$

```math
{\bf{X}}_{cm} = \frac{1}{m}\sum_{i=1}^N m_i{\bf{X}}_i
```

### 各質点の位置 ${\bf{X}}_{i}$

```math
{\bf{X}}_{i} = {\bf{X}}_{cm} + {\bf{\rho}}_{i}
```

### ${\bf{\rho}}_{i}$ の性質①

```math
\sum_{i=1}^N mi {\bf{\rho}}_{i} = 0
```

## 各質点の速度

<img alt="fig" src="figures/lesson-04/fig_02.JPG" width="50%">

### 質点の速度

```math
\dot{{\bf{X}}}_{i} = \dot{{\bf{X}}}_{cm} + \dot{{\boldsymbol{\rho}}}_{i}
```

```math
\begin{aligned}
\dot{{\boldsymbol{\rho}}}_{i} \cdot \dot{{\boldsymbol{\rho}}}_{i} &= {\bf{v}}_{ri} \cdot {\bf{v}}_{ri} \\
&= ({\boldsymbol{\omega}} \times {\bf{r}}_i) \cdot ({\boldsymbol{\omega}} \times {\bf{r}}_i) \\
&= ({\bf{R}}_i {\boldsymbol{\omega}}) \cdot ({\bf{R}}_i {\boldsymbol{\omega}}) \\
&= ({\bf{R}}_i {\boldsymbol{\omega}})^T ({\bf{R}}_i {\boldsymbol{\omega}}) \\
&= {\boldsymbol{\omega}}^T {\bf{R}}_i^T {\bf{R}}_i {\boldsymbol{\omega}} \\
&= {\boldsymbol{\omega}}^T \bar{{\bf{R}}}_i {\boldsymbol{\omega}} \\
\end{aligned}
```

```math
\begin{aligned}
ただし {\boldsymbol{\omega}} \times {\bf{r}}_i = \begin{pmatrix}
\omega_y r_{zi} + \omega_z r_{yi} \\
\omega_z r_{xi} + \omega_x r_{zi} \\
\omega_x r_{yi} + \omega_y r_{xi}
\end{pmatrix} より
{\bf{R}}_i = \begin{pmatrix}
0 & r_{zi} & -r_{yi} \\
-r_{zi} & 0 & r_{xi} \\
r_{yi} & -r_{xi} & 0
\end{pmatrix} とする \\
ただし \bar{{\bf{R}}}_i = \begin{pmatrix}
r_{yi}^2 + r_{zi}^2 & -r_{xi}r_{yi} & -r_{zi}r_{xi} \\
-r_{xi}r_{yi} & r_{xi}^2 + r_{zi}^2 & -r_{yi}r_{zi} \\
-r_{zi}r_{xi} & -r_{yi}r_{zi} & r_{xi}^2 + r_{yi}^2
\end{pmatrix} とする
\end{aligned}
```

## 外積のおさらい

<img alt="fig" src="figures/lesson-04/fig_03.JPG" width="50%">

### 外積

```math
\begin{aligned}
{\bf{c}} &= {\bf{b}} \times {\bf{a}} \\
&= \begin{pmatrix}b_x\\b_y\\b_z\end{pmatrix} \times \begin{pmatrix}a_x\\a_y\\a_z\end{pmatrix} \\
&= \begin{pmatrix}
b_y a_z - b_z a_y\\
b_z a_x - b_x a_z\\
b_x a_y - b_y a_x
\end{pmatrix}
\end{aligned}
```

### 軸周りの速度

```math
v = \omega r \sin \theta \\
```

```math
{\bf{v}} = \omega {\bf{e}} \times {\bf{r}} \\
```

```math
ただし |{\bf{e}}| = 1
```

## 外積による3次元速度の計算(続き)

<img alt="fig" src="figures/lesson-04/fig_02.JPG" width="50%">

### 質点の速度

```math
\begin{aligned}
{\bf{v}}_{ri} &= {\boldsymbol{\omega}} \times {\bf{r}}_i \\
{\bf{v}}_{ri} &: 重心から見た質点の速度ベクトル \\
{\bf{r}}_i &: 剛体座標系から見た質点の位置ベクトル
\end{aligned}
```

```math
\begin{aligned}
{\bf{v}}_{ri} &= \omega_x {\bf{e}}_{\bf{x}} \times {\bf{r}}_i
+ \omega_y {\bf{e}}_{\bf{y}} \times {\bf{r}}_i
+ \omega_z {\bf{e}}_{\bf{z}} \times {\bf{r}}_i \\
&= {\boldsymbol{\omega}} \times {\bf{r}}_i
\end{aligned}
```

```math
ただし {\bf{e}}_x = \begin{pmatrix}
1, 0, 0
\end{pmatrix}^T ,
{\bf{e}}_y = \begin{pmatrix}
0, 1, 0
\end{pmatrix}^T ,
{\bf{e}}_z = \begin{pmatrix}
0, 0, 1
\end{pmatrix}^T
```

## 運動エネルギーの導出

```math
\begin{aligned}
v_i^2 &= \dot{{\bf{X}}}_i \cdot \dot{{\bf{X}}}_i \\
&= v_{cm}^2 + 2\dot{{\bf{X}}}_{cm} \cdot \dot{{\boldsymbol{\rho}}}_i + \dot{{\boldsymbol{\rho}}}_i \cdot \dot{{\boldsymbol{\rho}}}_i
\end{aligned}
```

### 運動エネルギー

```math
\begin{aligned}
K &= \sum_{i=1}^N \frac{1}{2}m_i v_i^2 \\
&= \sum_{i=1}^N \frac{1}{2}m_i (v_{cm}^2 + 2\dot{{\bf{X}}}_{cm} \cdot \dot{{\boldsymbol{\rho}}}_i + \dot{{\boldsymbol{\rho}}}_i \cdot \dot{{\boldsymbol{\rho}}}_i) \\
&= \frac{1}{2} \sum_{i=1}^N m_i v_{cm}^2 + \dot{{\bf{X}}}_{cm} \cdot \sum_{i=1}^N m_i \dot{{\boldsymbol{\rho}}}_i + \frac{1}{2} \sum_{i=1}^N m_i {\boldsymbol{\omega}}^T \bar{{\bf{R}}}_i {\boldsymbol{\omega}} \\
\sum_{i=1}^N m_i &= m 、 \sum_{i=1}^N m_i \dot{{\boldsymbol{\rho}}}_i = 0  、 I = \sum_{i=1}^N mi \bar{{\bf{R}}}_i より\\
&= \frac{1}{2} m v_{cm}^2 + \frac{1}{2} {\boldsymbol{\omega}}^T I {\boldsymbol{\omega}} \\
\end{aligned}
```

## 演習

### 問い

```math
\begin{aligned}
質量 m の質点の位置を {\bf{r}} = \begin{pmatrix}r_x\\r_y\\r_z\end{pmatrix} とし、\\
その質点がベクトル {\bf{e}} = \begin{pmatrix}e_x\\e_y\\e_z\end{pmatrix} を回転軸として角速度 ω で回転しているとき、\\
質点の速度 v と運動エネルギー K を求めよ
\end{aligned}
```

### 解答

#### 質点の速度

```math
\begin{aligned}
{\bf{v}} &= \omega {\bf{e}} \times {\bf{r}} \\
&= \omega \begin{pmatrix}e_x\\e_y\\e_z\end{pmatrix} \times \begin{pmatrix}r_x\\r_y\\r_z\end{pmatrix} \\
&= \omega \begin{pmatrix}
e_y r_z - e_z r_y \\
e_z r_x - e_x r_z \\
e_x r_y - e_y r_x
\end{pmatrix}
\end{aligned}
```

#### 運動エネルギー

```math
\begin{aligned}
K &= \frac{1}{2} m v_{cm}^2 + \frac{1}{2} {\boldsymbol{\omega}}^T I {\boldsymbol{\omega}} \\
質点は&慣性テンソルがゼロなので、\\
&= \frac{1}{2} m v_{cm}^2 \\
&= \frac{1}{2} m {\bf{v}} \cdot {\bf{v}} \\
&= \frac{1}{2} m (\omega {\bf{e}} \times {\bf{r}}) \cdot (\omega {\bf{e}} \times {\bf{r}}) \\
\end{aligned}
```

## 以下Latex数式のコピペ用

```math
\begin{aligned}
\begin{pmatrix}
{\bf{x}}
\end{pmatrix}
\end{aligned}
```
