Thinking1	在实际工作中，FM和MF哪个应用的更多，为什么		
实际工作中FM应用更多，MF预测模型中只考虑了user和item两个特性维度，多维特征MF无法解决问题，而FM可以将多维特性进行二阶特征组合，利用更多信息进行推荐。进一步讲，当FM的特性维度只有user和item时，FM相当于MF，即MF为FM的特例。

Thinking2	FFM与FM有哪些区别？
1.FM矩阵将User和Item都进行了one-hot编码作为特征，使得特征维度非常巨大且稀疏
2.矩阵分解MF是FM的特例，即特征只有User ID 和Item ID的FM模型
3.矩阵分解MF只适用于评分预测，进行简单的特征计算，无法利用其他特征，而FM引入了更多辅助信息（Side information）作为特征
4.FM在计算二阶特征组合系数的时候，使用了MF

Thinking3	DeepFM相比于FM解决了哪些问题，原理是怎样的
FM模型在构造高阶特征组合时，计算量会非常大，为了解决高阶特征组合的问题，引入了DeepFM
DeepFM相当于FM+DNN组合，将一阶和二阶特征组合利用FM模型进行预测，在高阶部分利用DNN进行预测，然后将两者进行组合，最终形成最后的预测结果.

Thinking4	假设一个小说网站，有N部小说，每部小说都有摘要描述。如何针对该网站制定基于内容的推荐系统，即用户看了某部小说后，推荐其他相关的小说。原理和步骤是怎样的	
主要的推荐原理就是以小说描述为特征，推荐相似度高的小说，具体步骤如下：
step1.特征提取：将小说的描述内容进行分词，利用N—Gram或者TF——IDF方法进行特征提取
N-Gram，提取N个连续字的集合，作为特征
TF-IDF，按照(min_df, max_df)提取关键词，并生成TFIDF矩阵
step2.相似度计算
将小说的特征向量化，可以利用余弦相似度计算小说之间的相似度
step3.将小说按相似度高低排序，推荐topN个内容

Thinking5	Word2Vec的应用场景有哪些
一 计算相似度&利用相似度进行推荐
1.可以利用相同原理(将用户关注大V的顺序近似的看成文章)进行大V推荐
2.可以实现商品推荐(将用户关注大V的顺序近似的看成文章)
3.挖掘物品的关联
二nlp中应用
1.可以用来分析文本中相近的词
2.根据不同语种里相同单词的词向量之间的特定关系做机器翻译
3.完形填空造句
三 个人认为也是一种编码和降维的方法，应该可以用在其他学习数据输入部分
