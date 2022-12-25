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
一般化座標 : \boldsymbol{X}
```
```math
ラグランジュの運動方程式 : \frac{d}{dt}(\frac{\partial L}{\partial \dot{\boldsymbol{X}}}) - \frac{\partial L}{\partial \boldsymbol{X}} = 0
```

ラグランジアンは定義。

### ポテンシャルエネルギー

例： 高さhの位置にある質量mの物体

![fig_01](figures/lesson-01/fig_01.JPG)

```math
U = mgh
```

例： バネ係数kにつながる質量mの物体がxの位置にあるとき

![fig_02](figures/lesson-01/fig_02.JPG)

```math
U = \frac{1}{2}kx^2
```

### 運動エネルギー

例： 速さvで動く、質量mの物体

![fig_03](figures/lesson-01/fig_03.JPG)

```math
K = \frac{1}{2}mv^2

```

### ラグランジュの運動方程式の利点

* 複雑な系でも、統一的な方法で比較的容易に運動方程式を導出できる
* 拘束のある系も取り扱える

### ラグランジュの運動方程式の例　１

質量mの物体が自由落下する。縦方向の位置はx(下向きに正)。

![fig_04](figures/lesson-01/fig_04.JPG)

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
&= \frac{1}{2} * 2 * m\dot{x} + 0 \\
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
\frac{d}{dt}(\frac{\partial L}{\partial \dot{x}}) - \frac{\partial L}{\partial x} = 0
\\
m\ddot{x} - mg = 0
```

### ラグランジュの運動方程式の例　２

水平な面に置かれた質点ｍの物体がバネにつながっている。バネ係数k、位置は水平方向にx。

![fig_02](figures/lesson-01/fig_02.JPG)

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

![](figures/lesson-02/fig_01.JPG)
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
\boldsymbol{X} = \begin{pmatrix}
x \\
y
\end{pmatrix}
```

ラグランジュの運動方程式

```math
\begin{aligned}
\frac{d}{dt}(\frac{\partial L}{\partial \dot{\boldsymbol{X}}}) - \frac{\partial L}{\partial \boldsymbol{X}} &= 0 \\
\frac{d}{dt}(\frac{\partial (\frac{1}{2}m(\dot{x}^2+\dot{y}^2))}{\partial \dot{\boldsymbol{X}}}) - \frac{\partial (\frac{1}{2}m(\dot{x}^2+\dot{y}^2))}{\partial \boldsymbol{X}} &= 0  \\
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
m \ddot{\boldsymbol{X}} &= 0
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
\frac{d}{dt}\sin x = \frac{\partial}{\partial x} \sin x * \frac{d}{dt}x = \cos x * \dot{x} = \dot{x} \cos x
\end{aligned}
```

## 一般化座標

一般化座標の定義： 系の位置を決める最小の変数の組

### 3関節ロボット

![](figures/lesson-02/fig_02.JPG)

* 関節角度ベクトル $(q_1, q_2, q_3)$ は一般化座標
* 手先位置 $(x, y)$ は一般化座標ではない（系の位置を決められない）

### 質点

![](figures/lesson-02/fig_03.JPG)

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

![](figures/lesson-02/fig_04.JPG)

* 2次元平面： 3自由度
* 3次元平面： 6自由度

### 拘束なしのロボットアーム

* 関節の数をNとするとN自由度

## 拘束

### 2つの質点が棒で拘束

![](figures/lesson-02/fig_05.JPG)

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

![](figures/lesson-02/fig_06.JPG)

拘束条件

```math
k_y(q_1, q_2, q_3) = y_{kabe}
```

自由度

```math
3 - 1 = 2
```

## ロボットの先端リンクが壁に固定

![](figures/lesson-02/fig_07.JPG)

手先の $x$ 座標、 $y$ 座標、手先角度 $\theta$ が拘束
自由度

```math
3 - 3 = 0
```

ロボットは動かない。

## 演習

次の系の自由度を求めよう。

![](figures/lesson-02/fig_08.JPG)

3関節ロボットと2関節ロボットに分割して考える。
左側の手先と右側の手先の $x$ 座標、 $y$ 座標、手先角度 $\theta$ が拘束

自由度

```math
3 + 2 - 3 = 2
```



```math
\begin{aligned}
\end{aligned}
```