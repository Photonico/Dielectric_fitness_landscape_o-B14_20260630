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

## 7. BB 对 FL 的限制: 不是所有景观都能被压缩

BB 函数给 FL 一个重要的反面约束.

如果存在一种通用方法, 可以对任意局域规则产生的景观做有效粗粒化, 并直接判断其长期命运, 那么原则上就可能解决停机问题, 进而计算 BB 函数.

但停机问题不可判定, BB 函数不可计算. 因此:

$$
\boxed{
\text{不存在适用于所有景观的通用压缩, 通用预测, 通用重整化方法}
}
$$

这不是削弱 FL, 而是让 FL 更成熟. FL 不是万能答案, 而是组织问题的语言. 它告诉我们应该问:

- 状态是什么.
- 邻域是什么.
- fitness 是什么.
- 动力学是什么.
- 是否存在有效变量.
- 是否可以粗粒化.
- 是否存在不可压缩区域.

所以 BB 的价值在于提醒:

```text
有景观
≠
景观简单
≠
可以全局预测
≠
可以统一重整化
```

这使 FL 从 toy model 升级为严肃框架, 因为它主动纳入了预测极限.

## 8. AI 与 FL 的关系

AI 与这套框架关系很深. AI 不是 FL 的外部应用, 而是几乎处在这个框架的中心.

### 8.1 神经网络训练本身就是景观动力学

神经网络参数可以写成:

$$
\theta=(w_1,w_2,\cdots,w_N)
$$

损失函数为:

$$
\mathcal{L}(\theta)
$$

于是神经网络天然定义了一个 loss landscape:

$$
(\text{parameter space},\mathcal{L})
$$

训练过程是在景观上的局域运动:

$$
\theta_{t+1}
=
\theta_t
-
\eta\nabla\mathcal{L}(\theta_t)
$$

也就是:

$$
\boxed{
\text{局域梯度更新}
\to
\text{全局能力涌现}
}
$$

这和 FL 的基本思想同构.

### 8.2 深度网络像一种数据驱动的粗粒化

深度网络逐层把原始输入映射成更抽象的表示:

```text
pixels / tokens / atomic structures
  ↓
local features
  ↓
motifs
  ↓
concepts / descriptors
  ↓
predictions / actions
```

这类似于重整化:

$$
\text{micro variables}
\to
\text{effective variables}
$$

不过这不是严格的 Wilson RG. 物理 RG 有明确尺度, 对称性, 固定点, 和流方程. 神经网络中的 RG 类比更接近一种数据驱动, 任务驱动的表示压缩.

更准确的说法是:

$$
\boxed{
\text{深度学习是在数据分布上学习一种有效粗粒化}
}
$$

### 8.3 Transformer 把局域性推广到信息依赖

CNN 的局域性来自空间近邻关系. Transformer 的 attention 看起来是非局域的, 因为任意 token 都可以 attend 到任意 token.

但从广义局域性看, attention 并不是简单破坏局域性. 它把邻域从物理坐标改写为信息相关性:

$$
\text{spatial neighborhood}
\to
\text{semantic neighborhood / dependency neighborhood}
$$

因此 Transformer 展示了:

$$
\boxed{
\text{局域性可以由坐标距离推广为依赖关系距离}
}
$$

这与广义局域化原理一致.

### 8.4 AI 是景观建模器, 搜索器, 和压缩器

AI 与景观有两层关系.

第一层, AI 自己在景观上训练:

$$
\theta \in \text{model landscape}
$$

第二层, AI 可以学习外部世界的景观:

$$
x \in \text{world landscape}
$$

例如在材料设计中:

$$
\text{structure}
\to
E, E_g, \epsilon(\omega), T_c, \text{stability}
$$

AI 可以学习 surrogate model:

$$
\hat F_{\mathrm{AI}}(\text{structure})
\approx
F_{\mathrm{DFT}}(\text{structure})
$$

然后在这个近似景观上搜索高 fitness 区域.

因此 AI 在 FL 中可以扮演三种角色:

```text
预测器: structure → property
景观建模器: samples → surrogate landscape
搜索策略: landscape → candidate structures
```

### 8.5 BB 给 AI 的边界

如果一个 AI 能对任意局域规则都找到有效粗粒化, 并直接预测最终结果, 那么它原则上就能解决停机问题.

这不可能.

因此:

$$
\boxed{
\text{不存在能压缩一切计算过程的通用 AI}
}
$$

AI 的强大不在于打破 BB 限制, 而在于真实世界通常不是任意程序空间. 真实世界存在大量可压缩结构:

- 对称性.
- 局域性.
- 重复 motif.
- 低维有效变量.
- 统计规律.
- 可迁移模式.
- 物理约束.

因此:

$$
\boxed{
\text{AI 的本质能力是在有结构的世界中寻找可压缩景观}
}
$$

## 9. Interpretability 与 Alignment 的景观解释

### 9.1 Interpretability 是寻找有效自由度

神经网络内部有海量参数. Interpretability 试图找到更高层的有效结构, 例如:

- features.
- circuits.
- modules.
- representations.
- latent variables.

这类似于从微观自由度中提取宏观有效变量:

$$
\text{parameters}
\to
\text{effective mechanisms}
$$

因此 interpretability 可以理解成一种广义重整化任务:

$$
\boxed{
\text{从神经网络的微观参数景观中提取人类可理解的有效变量}
}
$$

### 9.2 Alignment 是两个景观之间的匹配问题

训练时优化的是 loss landscape:

$$
\mathcal{L}(\theta)
$$

我们真正关心的是 value landscape:

$$
V(\text{behavior})
$$

问题在于:

$$
\text{local loss decrease}
\not\Rightarrow
\text{global alignment with human intent}
$$

所以 alignment 可以理解为:

$$
\boxed{
\text{如何让训练景观的局部优化方向, 对应人类价值景观中的好区域}
}
$$

这也是 FL 语言的一个优点. 它能把 AI alignment 从抽象问题, 部分转化为景观, 目标函数, 动力学, 盆地, 和泛化的问题.
