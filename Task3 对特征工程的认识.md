




<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
  
      
  <div id="readme" class="Box-body readme blob js-code-block-container p-5 p-xl-6 gist-border-0">
    <article class="markdown-body entry-content container-lg" itemprop="text"><h1><a id="user-content-task3-特征工程" class="anchor" aria-hidden="true" href="#task3-特征工程"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Task3 特征工程</h1>

<h2><a id="user-content-33-代码示例" class="anchor" aria-hidden="true" href="#33-代码示例"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3.3 代码示例</h2>
<h3><a id="user-content-331-导入包并读取数据" class="anchor" aria-hidden="true" href="#331-导入包并读取数据"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3.3.1 导入包并读取数据</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-k">import</span> <span class="pl-s1">pandas</span> <span class="pl-k">as</span> <span class="pl-s1">pd</span>
<span class="pl-k">import</span> <span class="pl-s1">numpy</span> <span class="pl-k">as</span> <span class="pl-s1">np</span>
<span class="pl-k">import</span> <span class="pl-s1">matplotlib</span>.<span class="pl-s1">pyplot</span> <span class="pl-k">as</span> <span class="pl-s1">plt</span>
<span class="pl-k">import</span> <span class="pl-s1">seaborn</span> <span class="pl-k">as</span> <span class="pl-s1">sns</span>
<span class="pl-k">import</span> <span class="pl-s1">datetime</span>
<span class="pl-k">from</span> <span class="pl-s1">tqdm</span> <span class="pl-k">import</span> <span class="pl-s1">tqdm</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">preprocessing</span> <span class="pl-k">import</span> <span class="pl-v">LabelEncoder</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-v">SelectKBest</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-s1">chi2</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">preprocessing</span> <span class="pl-k">import</span> <span class="pl-v">MinMaxScaler</span>
<span class="pl-k">import</span> <span class="pl-s1">xgboost</span> <span class="pl-k">as</span> <span class="pl-s1">xgb</span>
<span class="pl-k">import</span> <span class="pl-s1">lightgbm</span> <span class="pl-k">as</span> <span class="pl-s1">lgb</span>
<span class="pl-k">from</span> <span class="pl-s1">catboost</span> <span class="pl-k">import</span> <span class="pl-v">CatBoostRegressor</span>
<span class="pl-k">import</span> <span class="pl-s1">warnings</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">model_selection</span> <span class="pl-k">import</span> <span class="pl-v">StratifiedKFold</span>, <span class="pl-v">KFold</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">metrics</span> <span class="pl-k">import</span> <span class="pl-s1">accuracy_score</span>, <span class="pl-s1">f1_score</span>, <span class="pl-s1">roc_auc_score</span>, <span class="pl-s1">log_loss</span>
<span class="pl-s1">warnings</span>.<span class="pl-en">filterwarnings</span>(<span class="pl-s">'ignore'</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span> <span class="pl-c1">=</span><span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">'../train.csv'</span>)
<span class="pl-s1">data_test_a</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">'../testA.csv'</span>)</pre></div>
<h3><a id="user-content-332特征预处理" class="anchor" aria-hidden="true" href="#332特征预处理"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3.3.2特征预处理</h3>
<ul>
<li>数据EDA部分我们已经对数据的大概和某些特征分布有了了解，数据预处理部分一般我们要处理一些EDA阶段分析出来的问题，这里介绍了数据缺失值的填充，时间格式特征的转化处理，某些对象类别特征的处理。</li>
</ul>
<p>首先我们查找出数据中的对象特征和数值特征</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">numerical_fea</span> <span class="pl-c1">=</span> <span class="pl-en">list</span>(<span class="pl-s1">data_train</span>.<span class="pl-en">select_dtypes</span>(<span class="pl-s1">exclude</span><span class="pl-c1">=</span>[<span class="pl-s">'object'</span>]).<span class="pl-s1">columns</span>)
<span class="pl-s1">category_fea</span> <span class="pl-c1">=</span> <span class="pl-en">list</span>(<span class="pl-en">filter</span>(<span class="pl-k">lambda</span> <span class="pl-s1">x</span>: <span class="pl-s1">x</span> <span class="pl-c1">not</span> <span class="pl-c1">in</span> <span class="pl-s1">numerical_fea</span>,<span class="pl-en">list</span>(<span class="pl-s1">data_train</span>.<span class="pl-s1">columns</span>)))
<span class="pl-s1">label</span> <span class="pl-c1">=</span> <span class="pl-s">'isDefault'</span>
<span class="pl-s1">numerical_fea</span>.<span class="pl-en">remove</span>(<span class="pl-s1">label</span>)</pre></div>
<p>在比赛中数据预处理是必不可少的一部分，对于缺失值的填充往往会影响比赛的结果，在比赛中不妨尝试多种填充然后比较结果选择结果最优的一种；
比赛数据相比真实场景的数据相对要“干净”一些，但是还是会有一定的“脏”数据存在，清洗一些异常值往往会获得意想不到的效果。</p>
<h4><a id="user-content-缺失值填充" class="anchor" aria-hidden="true" href="#缺失值填充"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>缺失值填充</h4>
<ul>
<li>
<p>把所有缺失值替换为指定的值0</p>
<p>data_train = data_train.fillna(0)</p>
</li>
<li>
<p>向用缺失值上面的值替换缺失值</p>
<p>data_train = data_train.fillna(axis=0,method='ffill')</p>
</li>
<li>
<p>纵向用缺失值下面的值替换缺失值,且设置最多只填充两个连续的缺失值</p>
<p>data_train = data_train.fillna(axis=0,method='bfill',limit=2)</p>
</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#查看缺失值情况</span>
<span class="pl-s1">data_train</span>.<span class="pl-en">isnull</span>().<span class="pl-en">sum</span>()</pre></div>
<pre><code>id                        0
loanAmnt                  0
term                      0
interestRate              0
installment               0
grade                     0
subGrade                  0
employmentTitle           1
employmentLength      46799
homeOwnership             0
annualIncome              0
verificationStatus        0
issueDate                 0
isDefault                 0
purpose                   0
postCode                  1
regionCode                0
dti                     239
delinquency_2years        0
ficoRangeLow              0
ficoRangeHigh             0
openAcc                   0
pubRec                    0
pubRecBankruptcies      405
revolBal                  0
revolUtil               531
totalAcc                  0
initialListStatus         0
applicationType           0
earliesCreditLine         0
title                     1
policyCode                0
n0                    40270
n1                    40270
n2                    40270
n2.1                  40270
n4                    33239
n5                    40270
n6                    40270
n7                    40270
n8                    40271
n9                    40270
n10                   33239
n11                   69752
n12                   40270
n13                   40270
n14                   40270
dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#按照平均数填充数值型特征</span>
<span class="pl-s1">data_train</span>[<span class="pl-s1">numerical_fea</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>[<span class="pl-s1">numerical_fea</span>].<span class="pl-en">fillna</span>(<span class="pl-s1">data_train</span>[<span class="pl-s1">numerical_fea</span>].<span class="pl-en">median</span>())
<span class="pl-s1">data_test_a</span>[<span class="pl-s1">numerical_fea</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_test_a</span>[<span class="pl-s1">numerical_fea</span>].<span class="pl-en">fillna</span>(<span class="pl-s1">data_train</span>[<span class="pl-s1">numerical_fea</span>].<span class="pl-en">median</span>())
<span class="pl-c">#按照众数填充类别型特征</span>
<span class="pl-s1">data_train</span>[<span class="pl-s1">category_fea</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>[<span class="pl-s1">category_fea</span>].<span class="pl-en">fillna</span>(<span class="pl-s1">data_train</span>[<span class="pl-s1">category_fea</span>].<span class="pl-en">mode</span>())
<span class="pl-s1">data_test_a</span>[<span class="pl-s1">category_fea</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_test_a</span>[<span class="pl-s1">category_fea</span>].<span class="pl-en">fillna</span>(<span class="pl-s1">data_train</span>[<span class="pl-s1">category_fea</span>].<span class="pl-en">mode</span>())</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>.<span class="pl-en">isnull</span>().<span class="pl-en">sum</span>()</pre></div>
<pre><code>id                        0
loanAmnt                  0
term                      0
interestRate              0
installment               0
grade                     0
subGrade                  0
employmentTitle           0
employmentLength      46799
homeOwnership             0
annualIncome              0
verificationStatus        0
issueDate                 0
isDefault                 0
purpose                   0
postCode                  0
regionCode                0
dti                       0
delinquency_2years        0
ficoRangeLow              0
ficoRangeHigh             0
openAcc                   0
pubRec                    0
pubRecBankruptcies        0
revolBal                  0
revolUtil                 0
totalAcc                  0
initialListStatus         0
applicationType           0
earliesCreditLine         0
title                     0
policyCode                0
n0                        0
n1                        0
n2                        0
n2.1                      0
n4                        0
n5                        0
n6                        0
n7                        0
n8                        0
n9                        0
n10                       0
n11                       0
n12                       0
n13                       0
n14                       0
dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#查看类别特征</span>
<span class="pl-s1">category_fea</span></pre></div>
<pre><code>['grade', 'subGrade', 'employmentLength', 'issueDate', 'earliesCreditLine']
</code></pre>
<ul>
<li>category_fea：对象型类别特征需要进行预处理，其中['issueDate']为时间格式特征。</li>
</ul>
<h4><a id="user-content-时间格式处理" class="anchor" aria-hidden="true" href="#时间格式处理"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>时间格式处理</h4>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#转化成时间格式</span>
<span class="pl-k">for</span> <span class="pl-s1">data</span> <span class="pl-c1">in</span> [<span class="pl-s1">data_train</span>, <span class="pl-s1">data_test_a</span>]:
    <span class="pl-s1">data</span>[<span class="pl-s">'issueDate'</span>] <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">to_datetime</span>(<span class="pl-s1">data</span>[<span class="pl-s">'issueDate'</span>],<span class="pl-s1">format</span><span class="pl-c1">=</span><span class="pl-s">'%Y-%m-%d'</span>)
    <span class="pl-s1">startdate</span> <span class="pl-c1">=</span> <span class="pl-s1">datetime</span>.<span class="pl-s1">datetime</span>.<span class="pl-en">strptime</span>(<span class="pl-s">'2007-06-01'</span>, <span class="pl-s">'%Y-%m-%d'</span>)
    <span class="pl-c">#构造时间特征</span>
    <span class="pl-s1">data</span>[<span class="pl-s">'issueDateDT'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data</span>[<span class="pl-s">'issueDate'</span>].<span class="pl-en">apply</span>(<span class="pl-k">lambda</span> <span class="pl-s1">x</span>: <span class="pl-s1">x</span><span class="pl-c1">-</span><span class="pl-s1">startdate</span>).<span class="pl-s1">dt</span>.<span class="pl-s1">days</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'employmentLength'</span>].<span class="pl-en">value_counts</span>(<span class="pl-s1">dropna</span><span class="pl-c1">=</span><span class="pl-c1">False</span>).<span class="pl-en">sort_index</span>()</pre></div>
<pre><code>1 year        52489
10+ years    262753
2 years       72358
3 years       64152
4 years       47985
5 years       50102
6 years       37254
7 years       35407
8 years       36192
9 years       30272
&lt; 1 year      64237
NaN           46799
Name: employmentLength, dtype: int64
</code></pre>
<h4><a id="user-content-对象类型特征转换到数值" class="anchor" aria-hidden="true" href="#对象类型特征转换到数值"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>对象类型特征转换到数值</h4>
<div class="highlight highlight-source-python"><pre><span class="pl-k">def</span> <span class="pl-en">employmentLength_to_int</span>(<span class="pl-s1">s</span>):
    <span class="pl-k">if</span> <span class="pl-s1">pd</span>.<span class="pl-en">isnull</span>(<span class="pl-s1">s</span>):
        <span class="pl-k">return</span> <span class="pl-s1">s</span>
    <span class="pl-k">else</span>:
        <span class="pl-k">return</span> <span class="pl-s1">np</span>.<span class="pl-en">int8</span>(<span class="pl-s1">s</span>.<span class="pl-en">split</span>()[<span class="pl-c1">0</span>])
<span class="pl-k">for</span> <span class="pl-s1">data</span> <span class="pl-c1">in</span> [<span class="pl-s1">data_train</span>, <span class="pl-s1">data_test_a</span>]:
    <span class="pl-s1">data</span>[<span class="pl-s">'employmentLength'</span>].<span class="pl-en">replace</span>(<span class="pl-s1">to_replace</span><span class="pl-c1">=</span><span class="pl-s">'10+ years'</span>, <span class="pl-s1">value</span><span class="pl-c1">=</span><span class="pl-s">'10 years'</span>, <span class="pl-s1">inplace</span><span class="pl-c1">=</span><span class="pl-c1">True</span>)
    <span class="pl-s1">data</span>[<span class="pl-s">'employmentLength'</span>].<span class="pl-en">replace</span>(<span class="pl-s">'&lt; 1 year'</span>, <span class="pl-s">'0 years'</span>, <span class="pl-s1">inplace</span><span class="pl-c1">=</span><span class="pl-c1">True</span>)
    <span class="pl-s1">data</span>[<span class="pl-s">'employmentLength'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data</span>[<span class="pl-s">'employmentLength'</span>].<span class="pl-en">apply</span>(<span class="pl-s1">employmentLength_to_int</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data</span>[<span class="pl-s">'employmentLength'</span>].<span class="pl-en">value_counts</span>(<span class="pl-s1">dropna</span><span class="pl-c1">=</span><span class="pl-c1">False</span>).<span class="pl-en">sort_index</span>()</pre></div>
<pre><code>0.0     15989
1.0     13182
2.0     18207
3.0     16011
4.0     11833
5.0     12543
6.0      9328
7.0      8823
8.0      8976
9.0      7594
10.0    65772
NaN     11742
Name: employmentLength, dtype: int64
</code></pre>
<ul>
<li>对earliesCreditLine进行预处理</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'earliesCreditLine'</span>].<span class="pl-en">sample</span>(<span class="pl-c1">5</span>)</pre></div>
<pre><code>519915    Sep-2002
564368    Dec-1996
768209    May-2004
453092    Nov-1995
763866    Sep-2000
Name: earliesCreditLine, dtype: object
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-k">for</span> <span class="pl-s1">data</span> <span class="pl-c1">in</span> [<span class="pl-s1">data_train</span>, <span class="pl-s1">data_test_a</span>]:
    <span class="pl-s1">data</span>[<span class="pl-s">'earliesCreditLine'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data</span>[<span class="pl-s">'earliesCreditLine'</span>].<span class="pl-en">apply</span>(<span class="pl-k">lambda</span> <span class="pl-s1">s</span>: <span class="pl-en">int</span>(<span class="pl-s1">s</span>[<span class="pl-c1">-</span><span class="pl-c1">4</span>:]))</pre></div>
<h4><a id="user-content-类别特征处理" class="anchor" aria-hidden="true" href="#类别特征处理"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>类别特征处理</h4>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 部分类别特征</span>
<span class="pl-s1">cate_features</span> <span class="pl-c1">=</span> [<span class="pl-s">'grade'</span>, <span class="pl-s">'subGrade'</span>, <span class="pl-s">'employmentTitle'</span>, <span class="pl-s">'homeOwnership'</span>, <span class="pl-s">'verificationStatus'</span>, <span class="pl-s">'purpose'</span>, <span class="pl-s">'postCode'</span>, <span class="pl-s">'regionCode'</span>, \
                 <span class="pl-s">'applicationType'</span>, <span class="pl-s">'initialListStatus'</span>, <span class="pl-s">'title'</span>, <span class="pl-s">'policyCode'</span>]
<span class="pl-k">for</span> <span class="pl-s1">f</span> <span class="pl-c1">in</span> <span class="pl-s1">cate_features</span>:
    <span class="pl-en">print</span>(<span class="pl-s1">f</span>, <span class="pl-s">'类型数：'</span>, <span class="pl-s1">data</span>[<span class="pl-s1">f</span>].<span class="pl-en">nunique</span>())</pre></div>
<pre><code>grade 类型数： 7
subGrade 类型数： 35
employmentTitle 类型数： 79282
homeOwnership 类型数： 6
verificationStatus 类型数： 3
purpose 类型数： 14
postCode 类型数： 889
regionCode 类型数： 51
applicationType 类型数： 2
initialListStatus 类型数： 2
title 类型数： 12058
policyCode 类型数： 1
</code></pre>
<p>像等级这种类别特征，是有优先级的可以labelencode或者自映射</p>
<div class="highlight highlight-source-python"><pre><span class="pl-k">for</span> <span class="pl-s1">data</span> <span class="pl-c1">in</span> [<span class="pl-s1">data_train</span>, <span class="pl-s1">data_test_a</span>]:
    <span class="pl-s1">data</span>[<span class="pl-s">'grade'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data</span>[<span class="pl-s">'grade'</span>].<span class="pl-en">map</span>({<span class="pl-s">'A'</span>:<span class="pl-c1">1</span>,<span class="pl-s">'B'</span>:<span class="pl-c1">2</span>,<span class="pl-s">'C'</span>:<span class="pl-c1">3</span>,<span class="pl-s">'D'</span>:<span class="pl-c1">4</span>,<span class="pl-s">'E'</span>:<span class="pl-c1">5</span>,<span class="pl-s">'F'</span>:<span class="pl-c1">6</span>,<span class="pl-s">'G'</span>:<span class="pl-c1">7</span>})</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 类型数在2之上，又不是高维稀疏的,且纯分类特征</span>
<span class="pl-k">for</span> <span class="pl-s1">data</span> <span class="pl-c1">in</span> [<span class="pl-s1">data_train</span>, <span class="pl-s1">data_test_a</span>]:
    <span class="pl-s1">data</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">get_dummies</span>(<span class="pl-s1">data</span>, <span class="pl-s1">columns</span><span class="pl-c1">=</span>[<span class="pl-s">'subGrade'</span>, <span class="pl-s">'homeOwnership'</span>, <span class="pl-s">'verificationStatus'</span>, <span class="pl-s">'purpose'</span>, <span class="pl-s">'regionCode'</span>], <span class="pl-s1">drop_first</span><span class="pl-c1">=</span><span class="pl-c1">True</span>)</pre></div>
<h3><a id="user-content-333--异常值处理" class="anchor" aria-hidden="true" href="#333--异常值处理"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3.3.3  异常值处理</h3>
<ul>
<li>当你发现异常值后，一定要先分清是什么原因导致的异常值，然后再考虑如何处理。首先，如果这一异常值并不代表一种规律性的，而是极其偶然的现象，或者说你并不想研究这种偶然的现象，这时可以将其删除。其次，如果异常值存在且代表了一种真实存在的现象，那就不能随便删除。在现有的欺诈场景中很多时候欺诈数据本身相对于正常数据勒说就是异常的，我们要把这些异常点纳入，重新拟合模型，研究其规律。能用监督的用监督模型，不能用的还可以考虑用异常检测的算法来做。</li>
<li>注意test的数据不能删。</li>
</ul>
<h4><a id="user-content-检测异常的方法一均方差" class="anchor" aria-hidden="true" href="#检测异常的方法一均方差"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>检测异常的方法一：均方差</h4>
<p>在统计学中，如果一个数据分布近似正态，那么大约 68% 的数据值会在均值的一个标准差范围内，大约 95% 会在两个标准差范围内，大约 99.7% 会在三个标准差范围内。</p>
<div class="highlight highlight-source-python"><pre><span class="pl-k">def</span> <span class="pl-en">find_outliers_by_3segama</span>(<span class="pl-s1">data</span>,<span class="pl-s1">fea</span>):
    <span class="pl-s1">data_std</span> <span class="pl-c1">=</span> <span class="pl-s1">np</span>.<span class="pl-en">std</span>(<span class="pl-s1">data</span>[<span class="pl-s1">fea</span>])
    <span class="pl-s1">data_mean</span> <span class="pl-c1">=</span> <span class="pl-s1">np</span>.<span class="pl-en">mean</span>(<span class="pl-s1">data</span>[<span class="pl-s1">fea</span>])
    <span class="pl-s1">outliers_cut_off</span> <span class="pl-c1">=</span> <span class="pl-s1">data_std</span> <span class="pl-c1">*</span> <span class="pl-c1">3</span>
    <span class="pl-s1">lower_rule</span> <span class="pl-c1">=</span> <span class="pl-s1">data_mean</span> <span class="pl-c1">-</span> <span class="pl-s1">outliers_cut_off</span>
    <span class="pl-s1">upper_rule</span> <span class="pl-c1">=</span> <span class="pl-s1">data_mean</span> <span class="pl-c1">+</span> <span class="pl-s1">outliers_cut_off</span>
    <span class="pl-s1">data</span>[<span class="pl-s1">fea</span><span class="pl-c1">+</span><span class="pl-s">'_outliers'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data</span>[<span class="pl-s1">fea</span>].<span class="pl-en">apply</span>(<span class="pl-k">lambda</span> <span class="pl-s1">x</span>:<span class="pl-en">str</span>(<span class="pl-s">'异常值'</span>) <span class="pl-k">if</span> <span class="pl-s1">x</span> <span class="pl-c1">&gt;</span> <span class="pl-s1">upper_rule</span> <span class="pl-c1">or</span> <span class="pl-s1">x</span> <span class="pl-c1">&lt;</span> <span class="pl-s1">lower_rule</span> <span class="pl-k">else</span> <span class="pl-s">'正常值'</span>)
    <span class="pl-k">return</span> <span class="pl-s1">data</span></pre></div>
<ul>
<li>得到特征的异常值后可以进一步分析变量异常值和目标变量的关系</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-en">copy</span>()
<span class="pl-k">for</span> <span class="pl-s1">fea</span> <span class="pl-c1">in</span> <span class="pl-s1">numerical_fea</span>:
    <span class="pl-s1">data_train</span> <span class="pl-c1">=</span> <span class="pl-en">find_outliers_by_3segama</span>(<span class="pl-s1">data_train</span>,<span class="pl-s1">fea</span>)
    <span class="pl-en">print</span>(<span class="pl-s1">data_train</span>[<span class="pl-s1">fea</span><span class="pl-c1">+</span><span class="pl-s">'_outliers'</span>].<span class="pl-en">value_counts</span>())
    <span class="pl-en">print</span>(<span class="pl-s1">data_train</span>.<span class="pl-en">groupby</span>(<span class="pl-s1">fea</span><span class="pl-c1">+</span><span class="pl-s">'_outliers'</span>)[<span class="pl-s">'isDefault'</span>].<span class="pl-en">sum</span>())
    <span class="pl-en">print</span>(<span class="pl-s">'*'</span><span class="pl-c1">*</span><span class="pl-c1">10</span>)</pre></div>
<pre><code>正常值    800000
Name: id_outliers, dtype: int64
id_outliers
正常值    159610
Name: isDefault, dtype: int64
**********
正常值    800000
Name: loanAmnt_outliers, dtype: int64
loanAmnt_outliers
正常值    159610
Name: isDefault, dtype: int64
**********
正常值    800000
Name: term_outliers, dtype: int64
term_outliers
正常值    159610
Name: isDefault, dtype: int64
**********
正常值    794259
异常值      5741
Name: interestRate_outliers, dtype: int64
interestRate_outliers
异常值      2916
正常值    156694
Name: isDefault, dtype: int64
**********
正常值    792046
异常值      7954
Name: installment_outliers, dtype: int64
installment_outliers
异常值      2152
正常值    157458
Name: isDefault, dtype: int64
**********
正常值    800000
Name: employmentTitle_outliers, dtype: int64
employmentTitle_outliers
正常值    159610
Name: isDefault, dtype: int64
**********
正常值    799701
异常值       299
Name: homeOwnership_outliers, dtype: int64
homeOwnership_outliers
异常值        62
正常值    159548
Name: isDefault, dtype: int64
**********
正常值    793973
异常值      6027
Name: annualIncome_outliers, dtype: int64
annualIncome_outliers
异常值       756
正常值    158854
Name: isDefault, dtype: int64
**********
正常值    800000
Name: verificationStatus_outliers, dtype: int64
verificationStatus_outliers
正常值    159610
Name: isDefault, dtype: int64
**********
正常值    783003
异常值     16997
Name: purpose_outliers, dtype: int64
purpose_outliers
异常值      3635
正常值    155975
Name: isDefault, dtype: int64
**********
正常值    798931
异常值      1069
Name: postCode_outliers, dtype: int64
postCode_outliers
异常值       221
正常值    159389
Name: isDefault, dtype: int64
**********
正常值    799994
异常值         6
Name: regionCode_outliers, dtype: int64
regionCode_outliers
异常值         1
正常值    159609
Name: isDefault, dtype: int64
**********
正常值    798440
异常值      1560
Name: dti_outliers, dtype: int64
dti_outliers
异常值       466
正常值    159144
Name: isDefault, dtype: int64
**********
正常值    778245
异常值     21755
Name: delinquency_2years_outliers, dtype: int64
delinquency_2years_outliers
异常值      5089
正常值    154521
Name: isDefault, dtype: int64
**********
正常值    788261
异常值     11739
Name: ficoRangeLow_outliers, dtype: int64
ficoRangeLow_outliers
异常值       778
正常值    158832
Name: isDefault, dtype: int64
**********
正常值    788261
异常值     11739
Name: ficoRangeHigh_outliers, dtype: int64
ficoRangeHigh_outliers
异常值       778
正常值    158832
Name: isDefault, dtype: int64
**********
正常值    790889
异常值      9111
Name: openAcc_outliers, dtype: int64
openAcc_outliers
异常值      2195
正常值    157415
Name: isDefault, dtype: int64
**********
正常值    792471
异常值      7529
Name: pubRec_outliers, dtype: int64
pubRec_outliers
异常值      1701
正常值    157909
Name: isDefault, dtype: int64
**********
正常值    794120
异常值      5880
Name: pubRecBankruptcies_outliers, dtype: int64
pubRecBankruptcies_outliers
异常值      1423
正常值    158187
Name: isDefault, dtype: int64
**********
正常值    790001
异常值      9999
Name: revolBal_outliers, dtype: int64
revolBal_outliers
异常值      1359
正常值    158251
Name: isDefault, dtype: int64
**********
正常值    799948
异常值        52
Name: revolUtil_outliers, dtype: int64
revolUtil_outliers
异常值        23
正常值    159587
Name: isDefault, dtype: int64
**********
正常值    791663
异常值      8337
Name: totalAcc_outliers, dtype: int64
totalAcc_outliers
异常值      1668
正常值    157942
Name: isDefault, dtype: int64
**********
正常值    800000
Name: initialListStatus_outliers, dtype: int64
initialListStatus_outliers
正常值    159610
Name: isDefault, dtype: int64
**********
正常值    784586
异常值     15414
Name: applicationType_outliers, dtype: int64
applicationType_outliers
异常值      3875
正常值    155735
Name: isDefault, dtype: int64
**********
正常值    775134
异常值     24866
Name: title_outliers, dtype: int64
title_outliers
异常值      3900
正常值    155710
Name: isDefault, dtype: int64
**********
正常值    800000
Name: policyCode_outliers, dtype: int64
policyCode_outliers
正常值    159610
Name: isDefault, dtype: int64
**********
正常值    782773
异常值     17227
Name: n0_outliers, dtype: int64
n0_outliers
异常值      3485
正常值    156125
Name: isDefault, dtype: int64
**********
正常值    790500
异常值      9500
Name: n1_outliers, dtype: int64
n1_outliers
异常值      2491
正常值    157119
Name: isDefault, dtype: int64
**********
正常值    789067
异常值     10933
Name: n2_outliers, dtype: int64
n2_outliers
异常值      3205
正常值    156405
Name: isDefault, dtype: int64
**********
正常值    789067
异常值     10933
Name: n2.1_outliers, dtype: int64
n2.1_outliers
异常值      3205
正常值    156405
Name: isDefault, dtype: int64
**********
正常值    788660
异常值     11340
Name: n4_outliers, dtype: int64
n4_outliers
异常值      2476
正常值    157134
Name: isDefault, dtype: int64
**********
正常值    790355
异常值      9645
Name: n5_outliers, dtype: int64
n5_outliers
异常值      1858
正常值    157752
Name: isDefault, dtype: int64
**********
正常值    786006
异常值     13994
Name: n6_outliers, dtype: int64
n6_outliers
异常值      3182
正常值    156428
Name: isDefault, dtype: int64
**********
正常值    788430
异常值     11570
Name: n7_outliers, dtype: int64
n7_outliers
异常值      2746
正常值    156864
Name: isDefault, dtype: int64
**********
正常值    789625
异常值     10375
Name: n8_outliers, dtype: int64
n8_outliers
异常值      2131
正常值    157479
Name: isDefault, dtype: int64
**********
正常值    786384
异常值     13616
Name: n9_outliers, dtype: int64
n9_outliers
异常值      3953
正常值    155657
Name: isDefault, dtype: int64
**********
正常值    788979
异常值     11021
Name: n10_outliers, dtype: int64
n10_outliers
异常值      2639
正常值    156971
Name: isDefault, dtype: int64
**********
正常值    799434
异常值       566
Name: n11_outliers, dtype: int64
n11_outliers
异常值       112
正常值    159498
Name: isDefault, dtype: int64
**********
正常值    797585
异常值      2415
Name: n12_outliers, dtype: int64
n12_outliers
异常值       545
正常值    159065
Name: isDefault, dtype: int64
**********
正常值    788907
异常值     11093
Name: n13_outliers, dtype: int64
n13_outliers
异常值      2482
正常值    157128
Name: isDefault, dtype: int64
**********
正常值    788884
异常值     11116
Name: n14_outliers, dtype: int64
n14_outliers
异常值      3364
正常值    156246
Name: isDefault, dtype: int64
**********
</code></pre>
<ul>
<li>例如可以看到异常值在两个变量上的分布几乎复合整体的分布，如果异常值都属于为1的用户数据里面代表什么呢？</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#删除异常值</span>
<span class="pl-k">for</span> <span class="pl-s1">fea</span> <span class="pl-c1">in</span> <span class="pl-s1">numerical_fea</span>:
    <span class="pl-s1">data_train</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>[<span class="pl-s1">data_train</span>[<span class="pl-s1">fea</span><span class="pl-c1">+</span><span class="pl-s">'_outliers'</span>]<span class="pl-c1">==</span><span class="pl-s">'正常值'</span>]
    <span class="pl-s1">data_train</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-en">reset_index</span>(<span class="pl-s1">drop</span><span class="pl-c1">=</span><span class="pl-c1">True</span>) </pre></div>
<h4><a id="user-content-检测异常的方法二箱型图" class="anchor" aria-hidden="true" href="#检测异常的方法二箱型图"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>检测异常的方法二：箱型图</h4>
<ul>
<li>总结一句话：四分位数会将数据分为三个点和四个区间，IQR = Q3 -Q1，下触须=Q1 − 1.5x IQR，上触须=Q3 + 1.5x IQR；</li>
</ul>
<h3><a id="user-content-334-数据分桶" class="anchor" aria-hidden="true" href="#334-数据分桶"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3.3.4 数据分桶</h3>
<ul>
<li>
<p>特征分箱的目的：</p>
<ul>
<li>从模型效果上来看，特征分箱主要是为了降低变量的复杂性，减少变量噪音对模型的影响，提高自变量和因变量的相关度。从而使模型更加稳定。</li>
</ul>
</li>
<li>
<p>数据分桶的对象：</p>
<ul>
<li>将连续变量离散化</li>
<li>将多状态的离散变量合并成少状态</li>
</ul>
</li>
<li>
<p>分箱的原因：</p>
<ul>
<li>数据的特征内的值跨度可能比较大，对有监督和无监督中如k-均值聚类它使用欧氏距离作为相似度函数来测量数据点之间的相似度。都会造成大吃小的影响，其中一种解决方法是对计数值进行区间量化即数据分桶也叫做数据分箱，然后使用量化后的结果。</li>
</ul>
</li>
<li>
<p>分箱的优点：</p>
<ul>
<li>处理缺失值：当数据源可能存在缺失值，此时可以把null单独作为一个分箱。</li>
<li>处理异常值：当数据中存在离群点时，可以把其通过分箱离散化处理，从而提高变量的鲁棒性（抗干扰能力）。例如，age若出现200这种异常值，可分入“age &gt; 60”这个分箱里，排除影响。</li>
<li>业务解释性：我们习惯于线性判断变量的作用，当x越来越大，y就越来越大。但实际x与y之间经常存在着非线性关系，此时可经过WOE变换。</li>
</ul>
</li>
<li>
<p>特别要注意一下分箱的基本原则：</p>
<ul>
<li>（1）最小分箱占比不低于5%</li>
<li>（2）箱内不能全部是好客户</li>
<li>（3）连续箱单调</li>
</ul>
</li>
</ul>
<ol>
<li>固定宽度分箱</li>
</ol>
<p>当数值横跨多个数量级时，最好按照 10 的幂（或任何常数的幂）来进行分组：0<del>9、10</del>99、100<del>999、1000</del>9999，等等。固定宽度分箱非常容易计算，但如果计数值中有比较大的缺口，就会产生很多没有任何数据的空箱子。</p>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 通过除法映射到间隔均匀的分箱中，每个分箱的取值范围都是loanAmnt/1000</span>
<span class="pl-s1">data</span>[<span class="pl-s">'loanAmnt_bin1'</span>] <span class="pl-c1">=</span> <span class="pl-s1">np</span>.<span class="pl-en">floor_divide</span>(<span class="pl-s1">data</span>[<span class="pl-s">'loanAmnt'</span>], <span class="pl-c1">1000</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-c">## 通过对数函数映射到指数宽度分箱</span>
<span class="pl-s1">data</span>[<span class="pl-s">'loanAmnt_bin2'</span>] <span class="pl-c1">=</span> <span class="pl-s1">np</span>.<span class="pl-en">floor</span>(<span class="pl-s1">np</span>.<span class="pl-en">log10</span>(<span class="pl-s1">data</span>[<span class="pl-s">'loanAmnt'</span>]))</pre></div>
<ol start="2">
<li>分位数分箱</li>
</ol>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data</span>[<span class="pl-s">'loanAmnt_bin3'</span>] <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">qcut</span>(<span class="pl-s1">data</span>[<span class="pl-s">'loanAmnt'</span>], <span class="pl-c1">10</span>, <span class="pl-s1">labels</span><span class="pl-c1">=</span><span class="pl-c1">False</span>)</pre></div>
<ol start="3">
<li>卡方分箱及其他分箱方法的尝试</li>
</ol>
<ul>
<li>这一部分属于进阶部分，学有余力的同学可以自行搜索尝试。</li>
</ul>
<h3><a id="user-content-335-特征交互" class="anchor" aria-hidden="true" href="#335-特征交互"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3.3.5 特征交互</h3>
<ul>
<li>交互特征的构造非常简单，使用起来却代价不菲。如果线性模型中包含有交互特征对，那它的训练时间和评分时间就会从 O(n) 增加到 O(n2)，其中 n 是单一特征的数量。</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">for</span> <span class="pl-s1">col</span> <span class="pl-c1">in</span> [<span class="pl-s">'grade'</span>, <span class="pl-s">'subGrade'</span>]: 
    <span class="pl-s1">temp_dict</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-en">groupby</span>([<span class="pl-s1">col</span>])[<span class="pl-s">'isDefault'</span>].<span class="pl-en">agg</span>([<span class="pl-s">'mean'</span>]).<span class="pl-en">reset_index</span>().<span class="pl-en">rename</span>(<span class="pl-s1">columns</span><span class="pl-c1">=</span>{<span class="pl-s">'mean'</span>: <span class="pl-s1">col</span> <span class="pl-c1">+</span> <span class="pl-s">'_target_mean'</span>})
    <span class="pl-s1">temp_dict</span>.<span class="pl-s1">index</span> <span class="pl-c1">=</span> <span class="pl-s1">temp_dict</span>[<span class="pl-s1">col</span>].<span class="pl-s1">values</span>
    <span class="pl-s1">temp_dict</span> <span class="pl-c1">=</span> <span class="pl-s1">temp_dict</span>[<span class="pl-s1">col</span> <span class="pl-c1">+</span> <span class="pl-s">'_target_mean'</span>].<span class="pl-en">to_dict</span>()

    <span class="pl-s1">data_train</span>[<span class="pl-s1">col</span> <span class="pl-c1">+</span> <span class="pl-s">'_target_mean'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>[<span class="pl-s1">col</span>].<span class="pl-en">map</span>(<span class="pl-s1">temp_dict</span>)
    <span class="pl-s1">data_test_a</span>[<span class="pl-s1">col</span> <span class="pl-c1">+</span> <span class="pl-s">'_target_mean'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_test_a</span>[<span class="pl-s1">col</span>].<span class="pl-en">map</span>(<span class="pl-s1">temp_dict</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 其他衍生变量 mean 和 std</span>
<span class="pl-k">for</span> <span class="pl-s1">df</span> <span class="pl-c1">in</span> [<span class="pl-s1">data_train</span>, <span class="pl-s1">data_test_a</span>]:
    <span class="pl-k">for</span> <span class="pl-s1">item</span> <span class="pl-c1">in</span> [<span class="pl-s">'n0'</span>,<span class="pl-s">'n1'</span>,<span class="pl-s">'n2'</span>,<span class="pl-s">'n2.1'</span>,<span class="pl-s">'n4'</span>,<span class="pl-s">'n5'</span>,<span class="pl-s">'n6'</span>,<span class="pl-s">'n7'</span>,<span class="pl-s">'n8'</span>,<span class="pl-s">'n9'</span>,<span class="pl-s">'n10'</span>,<span class="pl-s">'n11'</span>,<span class="pl-s">'n12'</span>,<span class="pl-s">'n13'</span>,<span class="pl-s">'n14'</span>]:
        <span class="pl-s1">df</span>[<span class="pl-s">'grade_to_mean_'</span> <span class="pl-c1">+</span> <span class="pl-s1">item</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s">'grade'</span>] <span class="pl-c1">/</span> <span class="pl-s1">df</span>.<span class="pl-en">groupby</span>([<span class="pl-s1">item</span>])[<span class="pl-s">'grade'</span>].<span class="pl-en">transform</span>(<span class="pl-s">'mean'</span>)
        <span class="pl-s1">df</span>[<span class="pl-s">'grade_to_std_'</span> <span class="pl-c1">+</span> <span class="pl-s1">item</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s">'grade'</span>] <span class="pl-c1">/</span> <span class="pl-s1">df</span>.<span class="pl-en">groupby</span>([<span class="pl-s1">item</span>])[<span class="pl-s">'grade'</span>].<span class="pl-en">transform</span>(<span class="pl-s">'std'</span>)</pre></div>
<p>这里给出一些特征交互的思路，但特征和特征间的交互衍生出新的特征还远远不止于此，抛砖引玉，希望大家多多探索。请学习者尝试其他的特征交互方法。</p>
<h3><a id="user-content-336-特征编码" class="anchor" aria-hidden="true" href="#336-特征编码"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3.3.6 特征编码</h3>
<h4><a id="user-content-labelencode-直接放入树模型中" class="anchor" aria-hidden="true" href="#labelencode-直接放入树模型中"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>labelEncode 直接放入树模型中</h4>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#label-encode:subGrade,postCode,title</span>
<span class="pl-c"># 高维类别特征需要进行转换</span>
<span class="pl-k">for</span> <span class="pl-s1">col</span> <span class="pl-c1">in</span> <span class="pl-en">tqdm</span>([<span class="pl-s">'employmentTitle'</span>, <span class="pl-s">'postCode'</span>, <span class="pl-s">'title'</span>,<span class="pl-s">'subGrade'</span>]):
    <span class="pl-s1">le</span> <span class="pl-c1">=</span> <span class="pl-v">LabelEncoder</span>()
    <span class="pl-s1">le</span>.<span class="pl-en">fit</span>(<span class="pl-en">list</span>(<span class="pl-s1">data_train</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">str</span>).<span class="pl-s1">values</span>) <span class="pl-c1">+</span> <span class="pl-en">list</span>(<span class="pl-s1">data_test_a</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">str</span>).<span class="pl-s1">values</span>))
    <span class="pl-s1">data_train</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">le</span>.<span class="pl-en">transform</span>(<span class="pl-en">list</span>(<span class="pl-s1">data_train</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">str</span>).<span class="pl-s1">values</span>))
    <span class="pl-s1">data_test_a</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">le</span>.<span class="pl-en">transform</span>(<span class="pl-en">list</span>(<span class="pl-s1">data_test_a</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">str</span>).<span class="pl-s1">values</span>))
<span class="pl-en">print</span>(<span class="pl-s">'Label Encoding 完成'</span>)</pre></div>
<pre><code>100%|██████████| 4/4 [00:08&lt;00:00,  2.04s/it]

Label Encoding 完成
</code></pre>
<h4><a id="user-content-逻辑回归等模型要单独增加的特征工程" class="anchor" aria-hidden="true" href="#逻辑回归等模型要单独增加的特征工程"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>逻辑回归等模型要单独增加的特征工程</h4>
<ul>
<li>对特征做归一化，去除相关性高的特征</li>
<li>归一化目的是让训练过程更好更快的收敛，避免特征大吃小的问题</li>
<li>去除相关性是增加模型的可解释性，加快预测过程。</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 举例归一化过程</span>
<span class="pl-c">#伪代码</span>
<span class="pl-k">for</span> <span class="pl-s1">fea</span> <span class="pl-c1">in</span> [要归一化的特征列表]：
    <span class="pl-s1">data</span>[<span class="pl-s1">fea</span>] <span class="pl-c1">=</span> ((<span class="pl-s1">data</span>[<span class="pl-s1">fea</span>] <span class="pl-c1">-</span> <span class="pl-s1">np</span>.<span class="pl-en">min</span>(<span class="pl-s1">data</span>[<span class="pl-s1">fea</span>])) <span class="pl-c1">/</span> (<span class="pl-s1">np</span>.<span class="pl-en">max</span>(<span class="pl-s1">data</span>[<span class="pl-s1">fea</span>]) <span class="pl-c1">-</span> <span class="pl-s1">np</span>.<span class="pl-en">min</span>(<span class="pl-s1">data</span>[<span class="pl-s1">fea</span>])))</pre></div>
<h3><a id="user-content-337-特征选择" class="anchor" aria-hidden="true" href="#337-特征选择"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>3.3.7 特征选择</h3>
<ul>
<li>特征选择技术可以精简掉无用的特征，以降低最终模型的复杂性，它的最终目的是得到一个简约模型，在不降低预测准确率或对预测准确率影响不大的情况下提高计算速度。特征选择不是为了减少训练时间（实际上，一些技术会增加总体训练时间），而是为了减少模型评分时间。</li>
</ul>
<p>特征选择的方法：</p>
<ul>
<li>1 Filter
<ul>
<li>方差选择法</li>
<li>相关系数法（pearson 相关系数）</li>
<li>卡方检验</li>
<li>互信息法</li>
</ul>
</li>
<li>2 Wrapper （RFE）
<ul>
<li>递归特征消除法</li>
</ul>
</li>
<li>3 Embedded
<ul>
<li>基于惩罚项的特征选择法</li>
<li>基于树模型的特征选择</li>
</ul>
</li>
</ul>
<h4><a id="user-content-filter" class="anchor" aria-hidden="true" href="#filter"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Filter</h4>
<ul>
<li>基于特征间的关系进行筛选</li>
</ul>
<p>方差选择法</p>
<ul>
<li>方差选择法中，先要计算各个特征的方差，然后根据设定的阈值，选择方差大于阈值的特征</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-v">VarianceThreshold</span>
<span class="pl-c">#其中参数threshold为方差的阈值</span>
<span class="pl-v">VarianceThreshold</span>(<span class="pl-s1">threshold</span><span class="pl-c1">=</span><span class="pl-c1">3</span>).<span class="pl-en">fit_transform</span>(<span class="pl-s1">train</span>,<span class="pl-s1">target_train</span>)</pre></div>
<p>相关系数法</p>
<ul>
<li>Pearson 相关系数
皮尔森相关系数是一种最简单的，可以帮助理解特征和响应变量之间关系的方法，该方法衡量的是变量之间的线性相关性。
结果的取值区间为 [-1，1] ， -1 表示完全的负相关， +1表示完全的正相关，0 表示没有线性相关。</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-v">SelectKBest</span>
<span class="pl-k">from</span> <span class="pl-s1">scipy</span>.<span class="pl-s1">stats</span> <span class="pl-k">import</span> <span class="pl-s1">pearsonr</span>
<span class="pl-c">#选择K个最好的特征，返回选择特征后的数据</span>
<span class="pl-c">#第一个参数为计算评估特征是否好的函数，该函数输入特征矩阵和目标向量，</span>
<span class="pl-c">#输出二元组（评分，P值）的数组，数组第i项为第i个特征的评分和P值。在此定义为计算相关系数</span>
<span class="pl-c">#参数k为选择的特征个数</span>

<span class="pl-v">SelectKBest</span>(<span class="pl-s1">k</span><span class="pl-c1">=</span><span class="pl-c1">5</span>).<span class="pl-en">fit_transform</span>(<span class="pl-s1">train</span>,<span class="pl-s1">target_train</span>)</pre></div>
<p>卡方检验</p>
<ul>
<li>经典的卡方检验是用于检验自变量对因变量的相关性。 假设自变量有N种取值，因变量有M种取值，考虑自变量等于i且因变量等于j的样本频数的观察值与期望的差距。 其统计量如下： χ2=∑(A−T)2T，其中A为实际值，T为理论值</li>
<li>(注：卡方只能运用在正定矩阵上，否则会报错Input X must be non-negative)</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-v">SelectKBest</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-s1">chi2</span>
<span class="pl-c">#参数k为选择的特征个数</span>

<span class="pl-v">SelectKBest</span>(<span class="pl-s1">chi2</span>, <span class="pl-s1">k</span><span class="pl-c1">=</span><span class="pl-c1">5</span>).<span class="pl-en">fit_transform</span>(<span class="pl-s1">train</span>,<span class="pl-s1">target_train</span>)</pre></div>
<p>互信息法</p>
<ul>
<li>经典的互信息也是评价自变量对因变量的相关性的。 在feature_selection库的SelectKBest类结合最大信息系数法可以用于选择特征，相关代码如下：</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-v">SelectKBest</span>
<span class="pl-k">from</span> <span class="pl-s1">minepy</span> <span class="pl-k">import</span> <span class="pl-v">MINE</span>
<span class="pl-c">#由于MINE的设计不是函数式的，定义mic方法将其为函数式的，</span>
<span class="pl-c">#返回一个二元组，二元组的第2项设置成固定的P值0.5</span>
<span class="pl-k">def</span> <span class="pl-en">mic</span>(<span class="pl-s1">x</span>, <span class="pl-s1">y</span>):
    <span class="pl-s1">m</span> <span class="pl-c1">=</span> <span class="pl-v">MINE</span>()
    <span class="pl-s1">m</span>.<span class="pl-en">compute_score</span>(<span class="pl-s1">x</span>, <span class="pl-s1">y</span>)
    <span class="pl-k">return</span> (<span class="pl-s1">m</span>.<span class="pl-en">mic</span>(), <span class="pl-c1">0.5</span>)
<span class="pl-c">#参数k为选择的特征个数</span>
<span class="pl-v">SelectKBest</span>(<span class="pl-k">lambda</span> <span class="pl-v">X</span>, <span class="pl-v">Y</span>: <span class="pl-en">array</span>(<span class="pl-en">map</span>(<span class="pl-k">lambda</span> <span class="pl-s1">x</span>:<span class="pl-en">mic</span>(<span class="pl-s1">x</span>, <span class="pl-v">Y</span>), <span class="pl-v">X</span>.<span class="pl-v">T</span>)).<span class="pl-v">T</span>, <span class="pl-s1">k</span><span class="pl-c1">=</span><span class="pl-c1">2</span>).<span class="pl-en">fit_transform</span>(<span class="pl-s1">train</span>,<span class="pl-s1">target_train</span>)</pre></div>
<h4><a id="user-content-wrapper-recursive-feature-eliminationrfe" class="anchor" aria-hidden="true" href="#wrapper-recursive-feature-eliminationrfe"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Wrapper （Recursive feature elimination，RFE）</h4>
<ul>
<li>递归特征消除法 递归消除特征法使用一个基模型来进行多轮训练，每轮训练后，消除若干权值系数的特征，再基于新的特征集进行下一轮训练。 在feature_selection库的RFE类可以用于选择特征，相关代码如下（以逻辑回归为例）：</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-v">RFE</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">linear_model</span> <span class="pl-k">import</span> <span class="pl-v">LogisticRegression</span>
<span class="pl-c">#递归特征消除法，返回特征选择后的数据</span>
<span class="pl-c">#参数estimator为基模型</span>
<span class="pl-c">#参数n_features_to_select为选择的特征个数</span>

<span class="pl-v">RFE</span>(<span class="pl-s1">estimator</span><span class="pl-c1">=</span><span class="pl-v">LogisticRegression</span>(), <span class="pl-s1">n_features_to_select</span><span class="pl-c1">=</span><span class="pl-c1">2</span>).<span class="pl-en">fit_transform</span>(<span class="pl-s1">train</span>,<span class="pl-s1">target_train</span>)</pre></div>
<h4><a id="user-content-embedded" class="anchor" aria-hidden="true" href="#embedded"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Embedded</h4>
<ul>
<li>基于惩罚项的特征选择法 使用带惩罚项的基模型，除了筛选出特征外，同时也进行了降维。 在feature_selection库的SelectFromModel类结合逻辑回归模型可以用于选择特征，相关代码如下：</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-v">SelectFromModel</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">linear_model</span> <span class="pl-k">import</span> <span class="pl-v">LogisticRegression</span>
<span class="pl-c">#带L1惩罚项的逻辑回归作为基模型的特征选择</span>

<span class="pl-v">SelectFromModel</span>(<span class="pl-v">LogisticRegression</span>(<span class="pl-s1">penalty</span><span class="pl-c1">=</span><span class="pl-s">"l1"</span>, <span class="pl-v">C</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>)).<span class="pl-en">fit_transform</span>(<span class="pl-s1">train</span>,<span class="pl-s1">target_train</span>)</pre></div>
<ul>
<li>基于树模型的特征选择 树模型中GBDT也可用来作为基模型进行特征选择。 在feature_selection库的SelectFromModel类结合GBDT模型可以用于选择特征，相关代码如下：</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">feature_selection</span> <span class="pl-k">import</span> <span class="pl-v">SelectFromModel</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">ensemble</span> <span class="pl-k">import</span> <span class="pl-v">GradientBoostingClassifier</span>
<span class="pl-c">#GBDT作为基模型的特征选择</span>
<span class="pl-v">SelectFromModel</span>(<span class="pl-v">GradientBoostingClassifier</span>()).<span class="pl-en">fit_transform</span>(<span class="pl-s1">train</span>,<span class="pl-s1">target_train</span>)</pre></div>
<p>本数据集中我们删除非入模特征后，并对缺失值填充，然后用计算协方差的方式看一下特征间相关性，然后进行模型训练</p>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 删除不需要的数据</span>
<span class="pl-k">for</span> <span class="pl-s1">data</span> <span class="pl-c1">in</span> [<span class="pl-s1">data_train</span>, <span class="pl-s1">data_test_a</span>]:
    <span class="pl-s1">data</span>.<span class="pl-en">drop</span>([<span class="pl-s">'issueDate'</span>,<span class="pl-s">'id'</span>], <span class="pl-s1">axis</span><span class="pl-c1">=</span><span class="pl-c1">1</span>,<span class="pl-s1">inplace</span><span class="pl-c1">=</span><span class="pl-c1">True</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s">"纵向用缺失值上面的值替换缺失值"</span>
<span class="pl-s1">data_train</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-en">fillna</span>(<span class="pl-s1">axis</span><span class="pl-c1">=</span><span class="pl-c1">0</span>,<span class="pl-s1">method</span><span class="pl-c1">=</span><span class="pl-s">'ffill'</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">x_train</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-en">drop</span>([<span class="pl-s">'isDefault'</span>,<span class="pl-s">'id'</span>], <span class="pl-s1">axis</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-c">#计算协方差</span>
<span class="pl-s1">data_corr</span> <span class="pl-c1">=</span> <span class="pl-s1">x_train</span>.<span class="pl-en">corrwith</span>(<span class="pl-s1">data_train</span>.<span class="pl-s1">isDefault</span>) <span class="pl-c">#计算相关性</span>
<span class="pl-s1">result</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-v">DataFrame</span>(<span class="pl-s1">columns</span><span class="pl-c1">=</span>[<span class="pl-s">'features'</span>, <span class="pl-s">'corr'</span>])
<span class="pl-s1">result</span>[<span class="pl-s">'features'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_corr</span>.<span class="pl-s1">index</span>
<span class="pl-s1">result</span>[<span class="pl-s">'corr'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_corr</span>.<span class="pl-s1">values</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 当然也可以直接看图</span>
<span class="pl-s1">data_numeric</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>[<span class="pl-s1">numerical_fea</span>]
<span class="pl-s1">correlation</span> <span class="pl-c1">=</span> <span class="pl-s1">data_numeric</span>.<span class="pl-en">corr</span>()

<span class="pl-s1">f</span> , <span class="pl-s1">ax</span> <span class="pl-c1">=</span> <span class="pl-s1">plt</span>.<span class="pl-en">subplots</span>(<span class="pl-s1">figsize</span> <span class="pl-c1">=</span> (<span class="pl-c1">7</span>, <span class="pl-c1">7</span>))
<span class="pl-s1">plt</span>.<span class="pl-en">title</span>(<span class="pl-s">'Correlation of Numeric Features with Price'</span>,<span class="pl-s1">y</span><span class="pl-c1">=</span><span class="pl-c1">1</span>,<span class="pl-s1">size</span><span class="pl-c1">=</span><span class="pl-c1">16</span>)
<span class="pl-s1">sns</span>.<span class="pl-en">heatmap</span>(<span class="pl-s1">correlation</span>,<span class="pl-s1">square</span> <span class="pl-c1">=</span> <span class="pl-c1">True</span>,  <span class="pl-s1">vmax</span><span class="pl-c1">=</span><span class="pl-c1">0.8</span>)</pre></div>
<pre><code>&lt;matplotlib.axes._subplots.AxesSubplot at 0x12d88ad10&gt;
</code></pre>

<span class="pl-k">def</span> <span class="pl-en">cat_model</span>(<span class="pl-s1">x_train</span>, <span class="pl-s1">y_train</span>, <span class="pl-s1">x_test</span>):
    <span class="pl-s1">cat_train</span>, <span class="pl-s1">cat_test</span> <span class="pl-c1">=</span> <span class="pl-en">cv_model</span>(<span class="pl-v">CatBoostRegressor</span>, <span class="pl-s1">x_train</span>, <span class="pl-s1">y_train</span>, <span class="pl-s1">x_test</span>, <span class="pl-s">"cat"</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">lgb_train</span>, <span class="pl-s1">lgb_test</span> <span class="pl-c1">=</span> <span class="pl-en">lgb_model</span>(<span class="pl-s1">x_train</span>, <span class="pl-s1">y_train</span>, <span class="pl-s1">x_test</span>)</pre></div>
<pre><code>************************************ 1 ************************************
Training until validation scores don't improve for 200 rounds
[200]	training's auc: 0.749225	valid_1's auc: 0.729679
[400]	training's auc: 0.765075	valid_1's auc: 0.730496
[600]	training's auc: 0.778745	valid_1's auc: 0.730435
Early stopping, best iteration is:
[455]	training's auc: 0.769202	valid_1's auc: 0.730686
[0.7306859913754798]
************************************ 2 ************************************
Training until validation scores don't improve for 200 rounds
[200]	training's auc: 0.749221	valid_1's auc: 0.731315
[400]	training's auc: 0.765117	valid_1's auc: 0.731658
[600]	training's auc: 0.778542	valid_1's auc: 0.731333
Early stopping, best iteration is:
[407]	training's auc: 0.765671	valid_1's auc: 0.73173
[0.7306859913754798, 0.7317304414673989]
************************************ 3 ************************************
Training until validation scores don't improve for 200 rounds
[200]	training's auc: 0.748436	valid_1's auc: 0.732775
[400]	training's auc: 0.764216	valid_1's auc: 0.733173
Early stopping, best iteration is:
[386]	training's auc: 0.763261	valid_1's auc: 0.733261
[0.7306859913754798, 0.7317304414673989, 0.7332610441015461]
************************************ 4 ************************************
Training until validation scores don't improve for 200 rounds
[200]	training's auc: 0.749631	valid_1's auc: 0.728327
[400]	training's auc: 0.765139	valid_1's auc: 0.728845
Early stopping, best iteration is:
[286]	training's auc: 0.756978	valid_1's auc: 0.728976
[0.7306859913754798, 0.7317304414673989, 0.7332610441015461, 0.7289759386807912]
************************************ 5 ************************************
Training until validation scores don't improve for 200 rounds
[200]	training's auc: 0.748414	valid_1's auc: 0.732727
[400]	training's auc: 0.763727	valid_1's auc: 0.733531
[600]	training's auc: 0.777489	valid_1's auc: 0.733566
Early stopping, best iteration is:
[524]	training's auc: 0.772372	valid_1's auc: 0.733772
[0.7306859913754798, 0.7317304414673989, 0.7332610441015461, 0.7289759386807912, 0.7337723979789789]
lgb_scotrainre_list: [0.7306859913754798, 0.7317304414673989, 0.7332610441015461, 0.7289759386807912, 0.7337723979789789]
lgb_score_mean: 0.7316851627208389
lgb_score_std: 0.0017424259863954693
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">testA_result</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">'../testA_result.csv'</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-en">roc_auc_score</span>(<span class="pl-s1">testA_result</span>[<span class="pl-s">'isDefault'</span>].<span class="pl-s1">values</span>, <span class="pl-s1">lgb_test</span>)</pre></div>
<pre><code>0.7290917729487896
</code></pre>


  </body>
</html>

