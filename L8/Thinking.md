# 1. CTR点击率预估中，GBDT+LR原理？
在CTR预估中,GBDT负责特征构造,LR负责回归预测.
具体而言GBDT利用多颗决策树对样本进行拟合,最后的结果进行OneHot编码可以呈现很多初始特征的组合,实现特征组合
LR利用GBDT得到的特征组合结果预测最终结果

why we need feature combination？
18岁 女 和少女不是一回事吗？这个可能是人脑的强大之处了，会根据特征进行自动的组合，机器不会
LR模型本质是对数线性模型,对非线性的关系表达能力不够，可能对样本拟合效果并不好，加入特征组合其实是提前做好的非线性表达,这样机器的拟合能力就上来了.

# 2. Wide&Deep模型结构是怎样的，为什么能具备记忆和泛化能力？

线性回归模型LR和深度神经网络DNN的组合,分别负责wide和deep部分

* 记忆能力指的是对已有特征的拟合,是在历史数据中探索相关可能性,只要在历史中出现的特征，LR都可以进行拟合,所以是memory能力
* 泛化能力是指对没有出现的特征组合探索,深度神经网络可以根据已有的特征学习出新的特征向量,这些向量不是已有的,所以具有推理泛化能力

# 3. CIR预估中,使用FM和DNN结合的方式,有哪些结合的方式,代表的模型有哪些？

FM和DNN有两个维度的组合
线性方式组合:DeepFM
深度方向组合:FNN,NFM

# 4.surprise工具中的baseline算法原理是怎样的？BaselineOnly和KNNbaseline区别

bui = u+bu+bi 

# 5. GBDT和随机森林都是树模型，区别

GBDT 是Boosting方法得到最后结果,树与树之间是递进的串联关系
Random Forest是Bagging方法的到最后结果,树与树之间是并行的并联关系

# 6. 基于领域的协同过滤都有哪些算法

UserCF 基于用户的协同过滤
ItemCF 基于物品的协同过滤算法




