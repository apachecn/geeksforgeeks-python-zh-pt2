# 分层 K 折交叉验证

> 原文:[https://www . geesforgeks . org/strategic-k-fold-交叉验证/](https://www.geeksforgeeks.org/stratified-k-fold-cross-validation/)

在机器学习中，当我们想要训练我们的 ML 模型时，我们使用 sklearn 中的 train_test_split()类将整个数据集分成训练集和测试集。然后我们在训练集上训练我们的模型，并在测试集上测试我们的模型。我们将在这种方法中面临的问题是:

每当我们改变 train_test_split()中存在的随机状态参数时，我们对于不同的随机状态得到不同的精度，因此我们不能精确地指出我们的模型的精度。
train _ test _ split()通过随机抽样将数据集拆分为 training_test 和 test_set。但是分层抽样被执行。

**什么是随机抽样和分层抽样？**
假设你想做一个调查，决定从一个特定的州打 1000 个电话，如果你选择 1000 个完全男性或者 1000 个完全女性或者 900 个女性和 100 个男性(随机)询问他们对某个特定产品的意见。然后基于这 1000 个意见，你不能决定整个州对你产品的意见。这是随机抽样。
但是在分层抽样中，假设该州的人口为 51.3%的男性和 48.7%的女性，那么对于从该州选择的 1000 人，如果你选择 531 名男性(1000 人中的 51.3%)和 487 名女性(1000 人中的 48.7%)，即 531 名男性+ 487 名女性(总数=1000 人)，询问他们的意见。那么这些人群就代表了整个州。这被称为分层抽样。

**为什么机器学习不首选随机抽样？**
我们来考虑一个二元类分类问题。假设我们的数据集由 100 个样本组成，其中 80 个是负类{ 0 }，20 个是正类{ 1 }。

**随机采样:**
如果我们进行随机采样，将数据集以 8:2 的比例分别拆分为训练集和测试集。那么我们可能在 training_set 中获得所有负类{0}，即 training_test 中的 80 个样本和 test_set 中的所有 20 个正类{1}。现在，如果我们在训练集上训练我们的模型，并在测试集上测试我们的模型，那么显然我们会得到一个糟糕的准确性分数。

**分层抽样:**
在分层抽样中，training_set 由 64 个负类{0} ( 80 的 80%)和 16 个正类{1} ( 20 的 80%)组成，即 training_set 中的 64 个{0}+16 个{1}=80 个样本，以相等的比例表示原始数据集，类似地，test_set 由 16 个负类{ 0 }(80 的 20%)和 4 个正类{ 1 }(20 的 20%)组成，即 16 这种类型的列车测试分割导致良好的准确性。

**对于提到的问题有什么解决方法？**
第一个问题的解决方案是使用 K-Fold 交叉验证，在这个问题中，我们能够针对不同的随机状态参数值获得不同的准确度分数。但是 K-Fold 交叉验证也存在第二个问题，即随机抽样。
第一个和第二个问题的解决方案都是使用分层 K 折叠交叉验证。

**什么是分层 K 折叠交叉验证？**
分层 k 重交叉验证与单纯 k 重交叉验证相同，但在分层 k 重交叉验证中，是分层抽样而不是随机抽样。

**代码:分层 K 折叠交叉验证的 Python 代码实现**

## 蟒蛇 3

```
# This code may not be run on GFG IDE 
# as required packages are not found. 

# STRATIFIES K-FOLD CROSS VALIDATION { 10-fold }

# Import Required Modules.
from statistics import mean, stdev
from sklearn import preprocessing
from sklearn.model_selection import StratifiedKFold
from sklearn import linear_model
from sklearn import datasets

# FEATCHING FEATURES AND TARGET VARIABLES IN ARRAY FORMAT.
cancer = datasets.load_breast_cancer()
# Input_x_Features.
x = cancer.data                        

# Input_ y_Target_Variable.
y = cancer.target                      

# Feature Scaling for input features.
scaler = preprocessing.MinMaxScaler()
x_scaled = scaler.fit_transform(x)

# Create  classifier object.
lr = linear_model.LogisticRegression()

# Create StratifiedKFold object.
skf = StratifiedKFold(n_splits=10, shuffle=True, random_state=1)
lst_accu_stratified = []

for train_index, test_index in skf.split(x, y):
    x_train_fold, x_test_fold = x_scaled[train_index], x_scaled[test_index]
    y_train_fold, y_test_fold = y[train_index], y[test_index]
    lr.fit(x_train_fold, y_train_fold)
    lst_accu_stratified.append(lr.score(x_test_fold, y_test_fold))

# Print the output.
print('List of possible accuracy:', lst_accu_stratified)
print('\nMaximum Accuracy That can be obtained from this model is:',
      max(lst_accu_stratified)*100, '%')
print('\nMinimum Accuracy:',
      min(lst_accu_stratified)*100, '%')
print('\nOverall Accuracy:',
      mean(lst_accu_stratified)*100, '%')
print('\nStandard Deviation is:', stdev(lst_accu_stratified))
```

**输出:**

```
List of possible accuracy: [0.9298245614035088, 0.9649122807017544, 0.9824561403508771, 1.0, 0.9649122807017544, 0.9649122807017544, 0.9824561403508771, 0.9473684210526315, 0.9473684210526315, 0.9821428571428571]

Maximum Accuracy That can be obtained from this model is: 100.0 %

Minimum Accuracy That can be obtained from this model is: 92.98245614035088 %

The overall Accuracy of this model is: 96.66353383458647 %

The Standard Deviation is: 0.02097789213195869
```