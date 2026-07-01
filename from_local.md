# 从广义局域性到 Fitness Landscape: BB, 重整化, 景观理论, 与 AI

## 结论

局域规则生成状态空间, 状态空间承载景观, 景观上的动力学形成搜索与演化, 重整化提取有效变量. AI 则在真实世界的可压缩结构中学习, 建模, 并搜索这些景观.

因此, 景观理论提供了一种把复杂系统几何化, 动力学化, 可计算化的语言.

核心链条是:

$$
\boxed{
\text{Local rule}
\Rightarrow
\text{state graph}
\Rightarrow
\text{landscape}
\Rightarrow
\text{local dynamics}
\Rightarrow
\text{coarse-graining}
\Rightarrow
\text{effective landscape}
\Rightarrow
\text{prediction, optimization, design, intelligence}
}
$$

## 1. Why Fitness Landscape

Fitness Landscape, FL, 最初常见于演化生物学. 基因型对应适应度, 群体在景观上演化. 如果把 "物种" 广义化, FL 就不再局限于生物学.

只要一个系统具有以下结构, 就可以谈景观:

1. 状态集合.
2. 状态之间的邻接关系.
3. 状态上的目标函数或性质函数.
4. 某种动力学或搜索过程.

因此 FL 可以推广到:

- 生物演化: genotype $\to$ fitness.
- 材料设计: structure $\to$ stability, band gap, optical response.
- 统计物理: configuration $\to$ energy, free energy.
- 机器学习: parameters $\to$ loss, reward.
- AI 搜索: prompt, policy, model state $\to$ performance.
- 复杂系统: local rule $\to$ halting time, complexity, output.
- 科学发现: hypothesis space $\to$ explanatory power, predictive power.

## 2. BB 函数给出的计算论背景

### 2.1 BB(x) 是否需要 BB(x-1)

Busy Beaver 函数, BB, 可以粗略理解为: 在所有 $x$ 个状态的图灵机中, 能停机者的最大运行时间或最大输出.

$BB(x)$ 不是递推函数. 也就是说, $BB(x)$ 不等于某种显式依赖 $BB(x-1)$ 的公式. 定义 $BB(x)$ 不需要先知道 $BB(x-1)$.

但是, 如果要严格证明 $BB(x)$ 的精确值, 必须分类所有 $x$ 状态机器的停机行为. 而 $x-1$ 状态机器可以看成 $x$ 状态机器的子集. 因此证明 $BB(x)$ 的过程中原理上覆盖了 $BB(x-1)$.

这说明 $BB(x)$ 不是楼梯式递推, 而是每一层状态空间的整体审判.

### 2.2 BB 函数的含义

图灵机的局域规则非常简单:

$$ (q,s) \mapsto (q',s',L/R) $$

每一步只看当前状态和当前符号, 并且只移动一格. 规则本身极端局域. 可是这样的局域规则可以产生 BB 级别的停机时间.

这说明, 底层规则局域简单, 不代表整体行为存在可计算的全局捷径.

BB 函数不是单纯的大数怪物. 它是关于局域规则, 整体行为, 和预测极限的边界案例. 即使我们明确了当前的一切规则, 未来也可能不可计算. 理解这种演化只能沿着局域演化链推进, 不能被任意压缩.

换句话说, 不存在能统一判断所有未来的算法. 世界的图景只能近似得到.

## 3. 广义局域化原理

### 3.1 从空间局域性到计算步骤局域性

传统物理中的局域性通常指空间局域性:

> 影响不能瞬间跨越空间.

动力学中的局域性可以理解为时间局域性:

> 下一时刻由当前状态和局域规则决定.

BB 函数进一步提示我们, 还可以定义计算论局域性:

> 对于图灵可计算系统, 不能随意跳过因果计算链, 直接获得全局结论.

因此, 局域性不应该只理解为坐标空间中的近邻关系. 更广义地说:

> 局域性是关于因果依赖链的结构.

这种因果链可以存在于:

- 空间坐标.
- 时间演化.
- 计算步骤.
- 状态转移图.
- 语义依赖图.
- 神经网络的信息流.
- 材料结构的局部扰动.

### 3.2 工作性定义

广义局域化原理可以表述为:

> 任何可达事实都必须沿某种因果链传播. 这条链可以存在于空间, 时间, 或计算步骤中.

世界可以由局域规则生成, 但理解这个世界可能仍然无法跳过局域演化本身.

这正是 BB 函数体现的 computational irreducibility.

## 4. 广义局域性与重整化

### 4.1 局域性使重整化可以定义

重整化可以概括为:

> 微观自由度 $\to$ 粗粒化 $\to$ 有效自由度.

传统 Wilson RG 依赖空间尺度, 局域相互作用, 对称性, 和尺度分离. 短尺度细节被吸收到少数有效参数中, 例如质量, 耦合常数, 弹性模量, 扩散系数等.

如果把局域性推广到因果图, 那么重整化也可以推广:

> 因果链局域性 $\to$ 沿因果图做 coarse-graining.

例如:

> 微观计算步骤 $\to$ 计算模块 $\to$ 有效计算步骤.

> 原子自由度 $\to$ 局域结构 motif $\to$ 材料描述符 $\to$ 光学响应.

### 4.2 局域性不保证重整化总是成功

局域性使重整化可以尝试, 但不保证存在封闭, 简单, 可计算的有效理论.

物理系统中 RG 经常成功, 是因为真实物理通常还具有额外结构:

- 对称性.
- 守恒律.
- 尺度分离.
- 热化或退相干.
- irrelevant variables 的衰减.
- 宏观变量的闭合性.

因此物理中常见:

$$
10^{23}\ \text{particles}
\to
T, P, \rho, \eta, c_v, \kappa, \cdots
$$

但是图灵机, 元胞自动机, 生命游戏等系统可以出现另一种情况:

> 局域规则 $\to$ 长程逻辑依赖 $\to$ 不可压缩演化.

从 BB 函数可以看到, 不存在一个对所有局域系统都有效的万能粗粒化机器.

更稳妥的表述是:

> 广义局域化原理提供了广义重整化的几何基础, 但计算模拟给出了通用重整化的边界.

## 5. 景观理论与 FL 的核心抽象

### 5.1 景观是什么

最抽象地说, 景观就是:

> 状态空间 + 状态上的标量函数.

可以写成 $(G,F)$, 其中:

- $G=(V,E)$ 是状态图.
- $V$ 是状态集合.
- $E$ 是邻接关系.
- $F:V\to\mathbb{R}$ 是 fitness, energy, loss, cost, reward, optical score 等标量函数.

如果没有邻接关系, 只能说有一个函数. 如果有邻接关系, 才真正有景观几何.

因此, FL 的关键不是单独的 $F(x)$, 而是:

> 状态, 邻域, 函数, 和动力学共同构成景观.

### 5.2 局域性赋予景观几何

局域性定义了谁是谁的邻居. 例如:

- 基因型中的一个突变距离.
- 晶体结构中的一个局域替换, 应变, 层间位移, 缺陷.
- 自旋系统中的一次 spin flip.
- 神经网络参数中的一个小梯度更新.
- 图灵机状态表中的一个局部规则改动.
- 语义空间中 token 之间的依赖关系.

因此:

> 局域性不是景观的附属品, 而是景观几何的来源.

没有邻域, 景观只是散点. 有了邻域, 才有山谷, 山脊, 盆地, 鞍点, 路径, 和势垒.

### 5.3 动力学让景观活起来

FL 不是静态图像. 真正有意义的是景观上的运动:

$$P(x\to y) \neq 0 \quad \text{only if} \quad y \in N(x) $$

这里 $N(x)$ 是 $x$ 的邻域.

不同领域对应不同动力学:

- 演化生物学: mutation + selection.
- 统计物理: thermal fluctuation + energy minimization.
- 材料搜索: structure mutation + relaxation + screening.
- 机器学习: gradient descent, SGD.
- AI agent: policy update + reward optimization.
- 科学发现: hypothesis generation + experimental feedback.

> 景观提供几何, 动力学提供运动.

## 6. 从局域性到 FL 的完整逻辑链

广义局域性可以理解为: 系统的演化并不是在整个状态空间中任意跳跃, 而是由局域规则规定每个状态的因果邻域. 因果邻域生成状态图. 状态图上赋予评价函数, 便得到景观. 动力学沿着局域连接发生. 经过粗粒化或重整化之后, 微观景观被改写为有效景观. 预测, 优化, 设计, 和智能都可以看作这种多尺度景观上的搜索与压缩.

$$
\begin{aligned}
\text{Local rule}
&\Rightarrow
\text{causal neighborhood}
\Rightarrow
G=(V,E)
\Rightarrow
F:V\to \mathbb{R}
\\
&\Rightarrow
D(x\to y)
\Rightarrow
\pi:V\to \bar V
\Rightarrow
(\bar G,\bar F,\bar D)
\\
&\Rightarrow
\text{prediction, optimization, design, intelligence}
\end{aligned}
$$

其中:

$$ G=(V,E) $$

表示由局域规则生成的状态图. 节点 $V$ 是可能状态. 边 $E$ 是允许的局域转移或因果连接.

$$ F:V\to \mathbb{R} $$

表示状态空间上的景观函数. 它可以是能量, 自由能, fitness, loss, reward, 或某种功能性指标.

$$ D(x\to y) $$

表示动力学规则. 它决定系统如何沿着状态图中的边从 $x$ 转移到 $y$.

$$ \pi:V\to \bar V $$

表示粗粒化映射. 多个微观状态被压缩成一个宏观状态, 从而得到有效状态图, 有效景观, 和有效动力学:

$$
(G,F,D)
\quad \longrightarrow \quad
(\bar G,\bar F,\bar D)
$$

最终可以概括为:

> 局域规则生成状态空间的连接结构, 景观赋予状态以评价, 动力学在局域连接上演化, 重整化把微观景观压缩成有效景观.
