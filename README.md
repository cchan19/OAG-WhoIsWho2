# OAG-WhoIsWho2
OAG-WhoIsWho2

队伍：Expelliarmus

A榜 0.8

---

整体思路：求句向量 --> 求相似度 --> 求组内rank

---

代码说明：

1.to_pickle: 保存表格数据

2.gen_valid: 生成测试样本

3.author_name_match: 匹配作者名和id

4.author_org_match: 匹配作者和单位，新增作者id和过往单位匹配

5.gen_train: 生成训练样本

6.gen_feat_v1: 特征

7-10: 使用bert预训练模型得到paper每个字段的句向量，再求相似度

11.gen_feat_v3_bert: 用重新提取的作者过往单位集合求相似度

12.gen_feat_v4_bert: 求组内rank特征

13.baseline_v3: 模型训练预测

---

句向量工具: https://github.com/UKPLab/sentence-transformers

BERT预训练模型下载：https://public.ukp.informatik.tu-darmstadt.de/reimers/sentence-transformers/v0.2/

---

进一步上分思路：
1. 模型融合，包括使用不同模型生成句向量来训练多个模型，和多次随机采样训练样本来训练多个模型。

2. 删除毒特征。

3. 做好EDA，分析训练测试特征分布情况


---

注意事项：b榜只有48小时，所以最好把训练样本和测试样本的代码分开，换榜后只需要重跑测试样本部分的代码。提前准备好代码。
