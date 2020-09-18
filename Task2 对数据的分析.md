




<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
  
    


      
  <div id="readme" class="Box-body readme blob js-code-block-container p-5 p-xl-6 gist-border-0">
    <article class="markdown-body entry-content container-lg" itemprop="text"><h1><a id="user-content-task2-数据分析" class="anchor" aria-hidden="true" href="#task2-数据分析"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Task2 数据分析</h1>
<p>此部分为零基础入门金融风控的 Task2 数据分析部分。</p>
<p>赛题：零基础入门数据挖掘 - 零基础入门金融风控之贷款违约</p>

<h2><a id="user-content-23-代码示例" class="anchor" aria-hidden="true" href="#23-代码示例"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3 代码示例</h2>
<h3><a id="user-content-231-导入数据分析及可视化过程需要的库" class="anchor" aria-hidden="true" href="#231-导入数据分析及可视化过程需要的库"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.1 导入数据分析及可视化过程需要的库</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-k">import</span> <span class="pl-s1">pandas</span> <span class="pl-k">as</span> <span class="pl-s1">pd</span>
<span class="pl-k">import</span> <span class="pl-s1">numpy</span> <span class="pl-k">as</span> <span class="pl-s1">np</span>
<span class="pl-k">import</span> <span class="pl-s1">matplotlib</span>.<span class="pl-s1">pyplot</span> <span class="pl-k">as</span> <span class="pl-s1">plt</span>
<span class="pl-k">import</span> <span class="pl-s1">seaborn</span> <span class="pl-k">as</span> <span class="pl-s1">sns</span>
<span class="pl-k">import</span> <span class="pl-s1">datetime</span>
<span class="pl-k">import</span> <span class="pl-s1">warnings</span>
<span class="pl-s1">warnings</span>.<span class="pl-en">filterwarnings</span>(<span class="pl-s">'ignore'</span>)</pre></div>
<pre><code>/Users/exudingtao/opt/anaconda3/lib/python3.7/site-packages/statsmodels/tools/_testing.py:19: FutureWarning: pandas.util.testing is deprecated. Use the functions in the public API at pandas.testing instead.
  import pandas.util.testing as tm
</code></pre>

<h3><a id="user-content-232-读取文件" class="anchor" aria-hidden="true" href="#232-读取文件"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.2 读取文件</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">'./train.csv'</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_test_a</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">'./testA.csv'</span>)</pre></div>
<h4><a id="user-content-2321读取文件的拓展知识" class="anchor" aria-hidden="true" href="#2321读取文件的拓展知识"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.2.1读取文件的拓展知识</h4>


<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train_sample</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">"./train.csv"</span>,<span class="pl-s1">nrows</span><span class="pl-c1">=</span><span class="pl-c1">5</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#设置chunksize参数，来控制每次迭代数据的大小</span>
<span class="pl-s1">chunker</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">"./train.csv"</span>,<span class="pl-s1">chunksize</span><span class="pl-c1">=</span><span class="pl-c1">5</span>)
<span class="pl-k">for</span> <span class="pl-s1">item</span> <span class="pl-c1">in</span> <span class="pl-s1">chunker</span>:
    <span class="pl-en">print</span>(<span class="pl-en">type</span>(<span class="pl-s1">item</span>))
    <span class="pl-c">#&lt;class 'pandas.core.frame.DataFrame'&gt;</span>
    <span class="pl-en">print</span>(<span class="pl-en">len</span>(<span class="pl-s1">item</span>))
    <span class="pl-c">#5</span></pre></div>
<h3><a id="user-content-233总体了解" class="anchor" aria-hidden="true" href="#233总体了解"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.3总体了解</h3>
<h4><a id="user-content-查看数据集的样本个数和原始特征维度" class="anchor" aria-hidden="true" href="#查看数据集的样本个数和原始特征维度"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>查看数据集的样本个数和原始特征维度</h4>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_test_a</span>.<span class="pl-s1">shape</span></pre></div>
<pre><code>(200000, 48)
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>.<span class="pl-s1">shape</span></pre></div>
<pre><code>(800000, 47)
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>.<span class="pl-s1">columns</span></pre></div>
<pre><code>Index(['id', 'loanAmnt', 'term', 'interestRate', 'installment', 'grade',
       'subGrade', 'employmentTitle', 'employmentLength', 'homeOwnership',
       'annualIncome', 'verificationStatus', 'issueDate', 'isDefault',
       'purpose', 'postCode', 'regionCode', 'dti', 'delinquency_2years',
       'ficoRangeLow', 'ficoRangeHigh', 'openAcc', 'pubRec',
       'pubRecBankruptcies', 'revolBal', 'revolUtil', 'totalAcc',
       'initialListStatus', 'applicationType', 'earliesCreditLine', 'title',
       'policyCode', 'n0', 'n1', 'n2', 'n2.1', 'n4', 'n5', 'n6', 'n7', 'n8',
       'n9', 'n10', 'n11', 'n12', 'n13', 'n14'],
      dtype='object')
</code></pre>
<p>查看一下具体的列名，赛题理解部分已经给出具体的特征含义：</p>
<ul>
<li>id	为贷款清单分配的唯一信用证标识</li>
<li>loanAmnt	贷款金额</li>
<li>term	贷款期限（year）</li>
<li>interestRate	贷款利率</li>
<li>installment	分期付款金额</li>
<li>grade	贷款等级</li>
<li>subGrade	贷款等级之子级</li>
<li>employmentTitle	就业职称</li>
<li>employmentLength	就业年限（年）</li>
<li>homeOwnership	借款人在登记时提供的房屋所有权状况</li>
<li>annualIncome	年收入</li>
<li>verificationStatus	验证状态</li>
<li>issueDate	贷款发放的月份</li>
<li>purpose	借款人在贷款申请时的贷款用途类别</li>
<li>postCode	借款人在贷款申请中提供的邮政编码的前3位数字</li>
<li>regionCode	地区编码</li>
<li>dti	债务收入比</li>
<li>delinquency_2years	借款人过去2年信用档案中逾期30天以上的违约事件数</li>
<li>ficoRangeLow	借款人在贷款发放时的fico所属的下限范围</li>
<li>ficoRangeHigh	借款人在贷款发放时的fico所属的上限范围</li>
<li>openAcc	借款人信用档案中未结信用额度的数量</li>
<li>pubRec	贬损公共记录的数量</li>
<li>pubRecBankruptcies	公开记录清除的数量</li>
<li>revolBal	信贷周转余额合计</li>
<li>revolUtil	循环额度利用率，或借款人使用的相对于所有可用循环信贷的信贷金额</li>
<li>totalAcc	借款人信用档案中当前的信用额度总数</li>
<li>initialListStatus	贷款的初始列表状态</li>
<li>applicationType	表明贷款是个人申请还是与两个共同借款人的联合申请</li>
<li>earliesCreditLine	借款人最早报告的信用额度开立的月份</li>
<li>title	借款人提供的贷款名称</li>
<li>policyCode	公开可用的策略_代码=1新产品不公开可用的策略_代码=2</li>
<li>n系列匿名特征	匿名特征n0-n14，为一些贷款人行为计数特征的处理</li>
</ul>
<p>通过info()来熟悉数据类型</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>.<span class="pl-en">info</span>()</pre></div>
<pre><code>&lt;class 'pandas.core.frame.DataFrame'&gt;
RangeIndex: 800000 entries, 0 to 799999
Data columns (total 47 columns):
 #   Column              Non-Null Count   Dtype  
---  ------              --------------   -----  
 0   id                  800000 non-null  int64  
 1   loanAmnt            800000 non-null  float64
 2   term                800000 non-null  int64  
 3   interestRate        800000 non-null  float64
 4   installment         800000 non-null  float64
 5   grade               800000 non-null  object 
 6   subGrade            800000 non-null  object 
 7   employmentTitle     799999 non-null  float64
 8   employmentLength    753201 non-null  object 
 9   homeOwnership       800000 non-null  int64  
 10  annualIncome        800000 non-null  float64
 11  verificationStatus  800000 non-null  int64  
 12  issueDate           800000 non-null  object 
 13  isDefault           800000 non-null  int64  
 14  purpose             800000 non-null  int64  
 15  postCode            799999 non-null  float64
 16  regionCode          800000 non-null  int64  
 17  dti                 799761 non-null  float64
 18  delinquency_2years  800000 non-null  float64
 19  ficoRangeLow        800000 non-null  float64
 20  ficoRangeHigh       800000 non-null  float64
 21  openAcc             800000 non-null  float64
 22  pubRec              800000 non-null  float64
 23  pubRecBankruptcies  799595 non-null  float64
 24  revolBal            800000 non-null  float64
 25  revolUtil           799469 non-null  float64
 26  totalAcc            800000 non-null  float64
 27  initialListStatus   800000 non-null  int64  
 28  applicationType     800000 non-null  int64  
 29  earliesCreditLine   800000 non-null  object 
 30  title               799999 non-null  float64
 31  policyCode          800000 non-null  float64
 32  n0                  759730 non-null  float64
 33  n1                  759730 non-null  float64
 34  n2                  759730 non-null  float64
 35  n2.1                759730 non-null  float64
 36  n4                  766761 non-null  float64
 37  n5                  759730 non-null  float64
 38  n6                  759730 non-null  float64
 39  n7                  759730 non-null  float64
 40  n8                  759729 non-null  float64
 41  n9                  759730 non-null  float64
 42  n10                 766761 non-null  float64
 43  n11                 730248 non-null  float64
 44  n12                 759730 non-null  float64
 45  n13                 759730 non-null  float64
 46  n14                 759730 non-null  float64
dtypes: float64(33), int64(9), object(5)
memory usage: 286.9+ MB
</code></pre>
<p>总体粗略的查看数据集各个特征的一些基本统计量</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>.<span class="pl-en">describe</span>()</pre></div>
<div>
&lt;style scoped&gt;
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }
<pre><code>.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
</code></pre>
&lt;/style&gt;
<table border="1">
  <thead>
    <tr>
      <th></th>
      <th>id</th>
      <th>loanAmnt</th>
      <th>term</th>
      <th>interestRate</th>
      <th>installment</th>
      <th>employmentTitle</th>
      <th>homeOwnership</th>
      <th>annualIncome</th>
      <th>verificationStatus</th>
      <th>isDefault</th>
      <th>...</th>
      <th>n5</th>
      <th>n6</th>
      <th>n7</th>
      <th>n8</th>
      <th>n9</th>
      <th>n10</th>
      <th>n11</th>
      <th>n12</th>
      <th>n13</th>
      <th>n14</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>800000.000000</td>
      <td>800000.000000</td>
      <td>800000.000000</td>
      <td>800000.000000</td>
      <td>800000.000000</td>
      <td>799999.000000</td>
      <td>800000.000000</td>
      <td>8.000000e+05</td>
      <td>800000.000000</td>
      <td>800000.000000</td>
      <td>...</td>
      <td>759730.000000</td>
      <td>759730.000000</td>
      <td>759730.000000</td>
      <td>759729.000000</td>
      <td>759730.000000</td>
      <td>766761.000000</td>
      <td>730248.000000</td>
      <td>759730.000000</td>
      <td>759730.000000</td>
      <td>759730.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>399999.500000</td>
      <td>14416.818875</td>
      <td>3.482745</td>
      <td>13.238391</td>
      <td>437.947723</td>
      <td>72005.351714</td>
      <td>0.614213</td>
      <td>7.613391e+04</td>
      <td>1.009683</td>
      <td>0.199513</td>
      <td>...</td>
      <td>8.107937</td>
      <td>8.575994</td>
      <td>8.282953</td>
      <td>14.622488</td>
      <td>5.592345</td>
      <td>11.643896</td>
      <td>0.000815</td>
      <td>0.003384</td>
      <td>0.089366</td>
      <td>2.178606</td>
    </tr>
    <tr>
      <th>std</th>
      <td>230940.252015</td>
      <td>8716.086178</td>
      <td>0.855832</td>
      <td>4.765757</td>
      <td>261.460393</td>
      <td>106585.640204</td>
      <td>0.675749</td>
      <td>6.894751e+04</td>
      <td>0.782716</td>
      <td>0.399634</td>
      <td>...</td>
      <td>4.799210</td>
      <td>7.400536</td>
      <td>4.561689</td>
      <td>8.124610</td>
      <td>3.216184</td>
      <td>5.484104</td>
      <td>0.030075</td>
      <td>0.062041</td>
      <td>0.509069</td>
      <td>1.844377</td>
    </tr>
    <tr>
      <th>min</th>
      <td>0.000000</td>
      <td>500.000000</td>
      <td>3.000000</td>
      <td>5.310000</td>
      <td>15.690000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000e+00</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>199999.750000</td>
      <td>8000.000000</td>
      <td>3.000000</td>
      <td>9.750000</td>
      <td>248.450000</td>
      <td>427.000000</td>
      <td>0.000000</td>
      <td>4.560000e+04</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>5.000000</td>
      <td>4.000000</td>
      <td>5.000000</td>
      <td>9.000000</td>
      <td>3.000000</td>
      <td>8.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>1.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>399999.500000</td>
      <td>12000.000000</td>
      <td>3.000000</td>
      <td>12.740000</td>
      <td>375.135000</td>
      <td>7755.000000</td>
      <td>1.000000</td>
      <td>6.500000e+04</td>
      <td>1.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>7.000000</td>
      <td>7.000000</td>
      <td>7.000000</td>
      <td>13.000000</td>
      <td>5.000000</td>
      <td>11.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>2.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>599999.250000</td>
      <td>20000.000000</td>
      <td>3.000000</td>
      <td>15.990000</td>
      <td>580.710000</td>
      <td>117663.500000</td>
      <td>1.000000</td>
      <td>9.000000e+04</td>
      <td>2.000000</td>
      <td>0.000000</td>
      <td>...</td>
      <td>11.000000</td>
      <td>11.000000</td>
      <td>10.000000</td>
      <td>19.000000</td>
      <td>7.000000</td>
      <td>14.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>0.000000</td>
      <td>3.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>799999.000000</td>
      <td>40000.000000</td>
      <td>5.000000</td>
      <td>30.990000</td>
      <td>1715.420000</td>
      <td>378351.000000</td>
      <td>5.000000</td>
      <td>1.099920e+07</td>
      <td>2.000000</td>
      <td>1.000000</td>
      <td>...</td>
      <td>70.000000</td>
      <td>132.000000</td>
      <td>79.000000</td>
      <td>128.000000</td>
      <td>45.000000</td>
      <td>82.000000</td>
      <td>4.000000</td>
      <td>4.000000</td>
      <td>39.000000</td>
      <td>30.000000</td>
    </tr>
  </tbody>
</table>
<p>8 rows × 42 columns</p>
</div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>.<span class="pl-en">head</span>(<span class="pl-c1">3</span>).<span class="pl-en">append</span>(<span class="pl-s1">data_train</span>.<span class="pl-en">tail</span>(<span class="pl-c1">3</span>))</pre></div>
<div>
&lt;style scoped&gt;
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }
<pre><code>.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead th {
    text-align: right;
}
</code></pre>
&lt;/style&gt;
<table border="1">
  <thead>
    <tr>
      <th></th>
      <th>id</th>
      <th>loanAmnt</th>
      <th>term</th>
      <th>interestRate</th>
      <th>installment</th>
      <th>grade</th>
      <th>subGrade</th>
      <th>employmentTitle</th>
      <th>employmentLength</th>
      <th>homeOwnership</th>
      <th>...</th>
      <th>n5</th>
      <th>n6</th>
      <th>n7</th>
      <th>n8</th>
      <th>n9</th>
      <th>n10</th>
      <th>n11</th>
      <th>n12</th>
      <th>n13</th>
      <th>n14</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>0</td>
      <td>35000.0</td>
      <td>5</td>
      <td>19.52</td>
      <td>917.97</td>
      <td>E</td>
      <td>E2</td>
      <td>320.0</td>
      <td>2 years</td>
      <td>2</td>
      <td>...</td>
      <td>9.0</td>
      <td>8.0</td>
      <td>4.0</td>
      <td>12.0</td>
      <td>2.0</td>
      <td>7.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>2.0</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1</td>
      <td>18000.0</td>
      <td>5</td>
      <td>18.49</td>
      <td>461.90</td>
      <td>D</td>
      <td>D2</td>
      <td>219843.0</td>
      <td>5 years</td>
      <td>0</td>
      <td>...</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2</td>
      <td>12000.0</td>
      <td>5</td>
      <td>16.99</td>
      <td>298.17</td>
      <td>D</td>
      <td>D3</td>
      <td>31698.0</td>
      <td>8 years</td>
      <td>0</td>
      <td>...</td>
      <td>0.0</td>
      <td>21.0</td>
      <td>4.0</td>
      <td>5.0</td>
      <td>3.0</td>
      <td>11.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>799997</th>
      <td>799997</td>
      <td>6000.0</td>
      <td>3</td>
      <td>13.33</td>
      <td>203.12</td>
      <td>C</td>
      <td>C3</td>
      <td>2582.0</td>
      <td>10+ years</td>
      <td>1</td>
      <td>...</td>
      <td>4.0</td>
      <td>26.0</td>
      <td>4.0</td>
      <td>10.0</td>
      <td>4.0</td>
      <td>5.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
      <td>4.0</td>
    </tr>
    <tr>
      <th>799998</th>
      <td>799998</td>
      <td>19200.0</td>
      <td>3</td>
      <td>6.92</td>
      <td>592.14</td>
      <td>A</td>
      <td>A4</td>
      <td>151.0</td>
      <td>10+ years</td>
      <td>0</td>
      <td>...</td>
      <td>10.0</td>
      <td>6.0</td>
      <td>12.0</td>
      <td>22.0</td>
      <td>8.0</td>
      <td>16.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>5.0</td>
    </tr>
    <tr>
      <th>799999</th>
      <td>799999</td>
      <td>9000.0</td>
      <td>3</td>
      <td>11.06</td>
      <td>294.91</td>
      <td>B</td>
      <td>B3</td>
      <td>13.0</td>
      <td>5 years</td>
      <td>0</td>
      <td>...</td>
      <td>3.0</td>
      <td>4.0</td>
      <td>4.0</td>
      <td>8.0</td>
      <td>3.0</td>
      <td>7.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>2.0</td>
    </tr>
  </tbody>
</table>
<p>6 rows × 47 columns</p>
</div>
<h3><a id="user-content-234查看数据集中特征缺失值唯一值等" class="anchor" aria-hidden="true" href="#234查看数据集中特征缺失值唯一值等"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.4查看数据集中特征缺失值，唯一值等</h3>
<p>查看缺失值</p>
<div class="highlight highlight-source-python"><pre><span class="pl-en">print</span>(<span class="pl-s">f'There are <span class="pl-s1"><span class="pl-kos">{</span><span class="pl-s1">data_train</span>.<span class="pl-en">isnull</span>().<span class="pl-en">any</span>().<span class="pl-en">sum</span>()<span class="pl-kos">}</span></span> columns in train dataset with missing values.'</span>)</pre></div>
<pre><code>There are 22 columns in train dataset with missing values.
</code></pre>
<p>上面得到训练集有22列特征有缺失值，进一步查看缺失特征中缺失率大于50%的特征</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">have_null_fea_dict</span> <span class="pl-c1">=</span> (<span class="pl-s1">data_train</span>.<span class="pl-en">isnull</span>().<span class="pl-en">sum</span>()<span class="pl-c1">/</span><span class="pl-en">len</span>(<span class="pl-s1">data_train</span>)).<span class="pl-en">to_dict</span>()
<span class="pl-s1">fea_null_moreThanHalf</span> <span class="pl-c1">=</span> {}
<span class="pl-k">for</span> <span class="pl-s1">key</span>,<span class="pl-s1">value</span> <span class="pl-c1">in</span> <span class="pl-s1">have_null_fea_dict</span>.<span class="pl-en">items</span>():
    <span class="pl-k">if</span> <span class="pl-s1">value</span> <span class="pl-c1">&gt;</span> <span class="pl-c1">0.5</span>:
        <span class="pl-s1">fea_null_moreThanHalf</span>[<span class="pl-s1">key</span>] <span class="pl-c1">=</span> <span class="pl-s1">value</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">fea_null_moreThanHalf</span></pre></div>
<pre><code>{}
</code></pre>
<p>具体的查看缺失特征及缺失率</p>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># nan可视化</span>
<span class="pl-s1">missing</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-en">isnull</span>().<span class="pl-en">sum</span>()<span class="pl-c1">/</span><span class="pl-en">len</span>(<span class="pl-s1">data_train</span>)
<span class="pl-s1">missing</span> <span class="pl-c1">=</span> <span class="pl-s1">missing</span>[<span class="pl-s1">missing</span> <span class="pl-c1">&gt;</span> <span class="pl-c1">0</span>]
<span class="pl-s1">missing</span>.<span class="pl-en">sort_values</span>(<span class="pl-s1">inplace</span><span class="pl-c1">=</span><span class="pl-c1">True</span>)
<span class="pl-s1">missing</span>.<span class="pl-s1">plot</span>.<span class="pl-en">bar</span>()</pre></div>
<pre><code>&lt;matplotlib.axes._subplots.AxesSubplot at 0x1229ab890&gt;
</code></pre>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/9433ee7af35a8546efcb24d3a6aedef5b7928014/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313532373730382e706e67"><img src="https://camo.githubusercontent.com/9433ee7af35a8546efcb24d3a6aedef5b7928014/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313532373730382e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913011527708.png" style="max-width:100%;"></a></p>
<ul>
<li>纵向了解哪些列存在 “nan”, 并可以把nan的个数打印，主要的目的在于查看某一列nan存在的个数是否真的很大，如果nan存在的过多，说明这一列对label的影响几乎不起作用了，可以考虑删掉。如果缺失值很小一般可以选择填充。</li>
<li>另外可以横向比较，如果在数据集中，某些样本数据的大部分列都是缺失的且样本足够的情况下可以考虑删除。</li>
</ul>
<p>Tips:
比赛大杀器lgb模型可以自动处理缺失值，Task4模型会具体学习模型了解模型哦！</p>
<p>查看训练集测试集中特征属性只有一值的特征</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">one_value_fea</span> <span class="pl-c1">=</span> [<span class="pl-s1">col</span> <span class="pl-k">for</span> <span class="pl-s1">col</span> <span class="pl-c1">in</span> <span class="pl-s1">data_train</span>.<span class="pl-s1">columns</span> <span class="pl-k">if</span> <span class="pl-s1">data_train</span>[<span class="pl-s1">col</span>].<span class="pl-en">nunique</span>() <span class="pl-c1">&lt;=</span> <span class="pl-c1">1</span>]</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">one_value_fea_test</span> <span class="pl-c1">=</span> [<span class="pl-s1">col</span> <span class="pl-k">for</span> <span class="pl-s1">col</span> <span class="pl-c1">in</span> <span class="pl-s1">data_test_a</span>.<span class="pl-s1">columns</span> <span class="pl-k">if</span> <span class="pl-s1">data_test_a</span>[<span class="pl-s1">col</span>].<span class="pl-en">nunique</span>() <span class="pl-c1">&lt;=</span> <span class="pl-c1">1</span>]</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">one_value_fea</span></pre></div>
<pre><code>['policyCode']
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">one_value_fea_test</span></pre></div>
<pre><code>['policyCode']
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-en">print</span>(<span class="pl-s">f'There are <span class="pl-s1"><span class="pl-kos">{</span><span class="pl-en">len</span>(<span class="pl-s1">one_value_fea</span>)<span class="pl-kos">}</span></span> columns in train dataset with one unique value.'</span>)
<span class="pl-en">print</span>(<span class="pl-s">f'There are <span class="pl-s1"><span class="pl-kos">{</span><span class="pl-en">len</span>(<span class="pl-s1">one_value_fea_test</span>)<span class="pl-kos">}</span></span> columns in test dataset with one unique value.'</span>)</pre></div>
<pre><code>There are 1 columns in train dataset with one unique value.
There are 1 columns in test dataset with one unique value.
</code></pre>
<h3><a id="user-content-总结" class="anchor" aria-hidden="true" href="#总结"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>总结：</h3>
<p>47列数据中有22列都缺少数据，这在现实世界中很正常。‘policyCode’具有一个唯一值（或全部缺失）。有很多连续变量和一些分类变量。</p>
<h3><a id="user-content-235-查看特征的数值类型有哪些对象类型有哪些" class="anchor" aria-hidden="true" href="#235-查看特征的数值类型有哪些对象类型有哪些"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.5 查看特征的数值类型有哪些，对象类型有哪些</h3>
<ul>
<li>特征一般都是由类别型特征和数值型特征组成，而数值型特征又分为连续型和离散型。</li>
<li>类别型特征有时具有非数值关系，有时也具有数值关系。比如‘grade’中的等级A，B，C等，是否只是单纯的分类，还是A优于其他要结合业务判断。</li>
<li>数值型特征本是可以直接入模的，但往往风控人员要对其做分箱，转化为WOE编码进而做标准评分卡等操作。从模型效果上来看，特征分箱主要是为了降低变量的复杂性，减少变量噪音对模型的影响，提高自变量和因变量的相关度。从而使模型更加稳定。</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">numerical_fea</span> <span class="pl-c1">=</span> <span class="pl-en">list</span>(<span class="pl-s1">data_train</span>.<span class="pl-en">select_dtypes</span>(<span class="pl-s1">exclude</span><span class="pl-c1">=</span>[<span class="pl-s">'object'</span>]).<span class="pl-s1">columns</span>)
<span class="pl-s1">category_fea</span> <span class="pl-c1">=</span> <span class="pl-en">list</span>(<span class="pl-en">filter</span>(<span class="pl-k">lambda</span> <span class="pl-s1">x</span>: <span class="pl-s1">x</span> <span class="pl-c1">not</span> <span class="pl-c1">in</span> <span class="pl-s1">numerical_fea</span>,<span class="pl-en">list</span>(<span class="pl-s1">data_train</span>.<span class="pl-s1">columns</span>)))</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">numerical_fea</span></pre></div>
<pre><code>['id',
 'loanAmnt',
 'term',
 'interestRate',
 'installment',
 'employmentTitle',
 'homeOwnership',
 'annualIncome',
 'verificationStatus',
 'isDefault',
 'purpose',
 'postCode',
 'regionCode',
 'dti',
 'delinquency_2years',
 'ficoRangeLow',
 'ficoRangeHigh',
 'openAcc',
 'pubRec',
 'pubRecBankruptcies',
 'revolBal',
 'revolUtil',
 'totalAcc',
 'initialListStatus',
 'applicationType',
 'title',
 'policyCode',
 'n0',
 'n1',
 'n2',
 'n2.1',
 'n4',
 'n5',
 'n6',
 'n7',
 'n8',
 'n9',
 'n10',
 'n11',
 'n12',
 'n13',
 'n14']
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">category_fea</span></pre></div>
<pre><code>['grade', 'subGrade', 'employmentLength', 'issueDate', 'earliesCreditLine']
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>.<span class="pl-s1">grade</span></pre></div>
<pre><code>0         E
1         D
2         D
3         A
4         C
         ..
799995    C
799996    A
799997    C
799998    A
799999    B
Name: grade, Length: 800000, dtype: object
</code></pre>
<h4><a id="user-content-数值型变量分析数值型肯定是包括连续型变量和离散型变量的找出来" class="anchor" aria-hidden="true" href="#数值型变量分析数值型肯定是包括连续型变量和离散型变量的找出来"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>数值型变量分析，数值型肯定是包括连续型变量和离散型变量的，找出来</h4>
<ul>
<li>划分数值型变量中的连续变量和离散型变量</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#过滤数值型类别特征</span>
<span class="pl-k">def</span> <span class="pl-en">get_numerical_serial_fea</span>(<span class="pl-s1">data</span>,<span class="pl-s1">feas</span>):
    <span class="pl-s1">numerical_serial_fea</span> <span class="pl-c1">=</span> []
    <span class="pl-s1">numerical_noserial_fea</span> <span class="pl-c1">=</span> []
    <span class="pl-k">for</span> <span class="pl-s1">fea</span> <span class="pl-c1">in</span> <span class="pl-s1">feas</span>:
        <span class="pl-s1">temp</span> <span class="pl-c1">=</span> <span class="pl-s1">data</span>[<span class="pl-s1">fea</span>].<span class="pl-en">nunique</span>()
        <span class="pl-k">if</span> <span class="pl-s1">temp</span> <span class="pl-c1">&lt;=</span> <span class="pl-c1">10</span>:
            <span class="pl-s1">numerical_noserial_fea</span>.<span class="pl-en">append</span>(<span class="pl-s1">fea</span>)
            <span class="pl-k">continue</span>
        <span class="pl-s1">numerical_serial_fea</span>.<span class="pl-en">append</span>(<span class="pl-s1">fea</span>)
    <span class="pl-k">return</span> <span class="pl-s1">numerical_serial_fea</span>,<span class="pl-s1">numerical_noserial_fea</span>
<span class="pl-s1">numerical_serial_fea</span>,<span class="pl-s1">numerical_noserial_fea</span> <span class="pl-c1">=</span> <span class="pl-en">get_numerical_serial_fea</span>(<span class="pl-s1">data_train</span>,<span class="pl-s1">numerical_fea</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">numerical_serial_fea</span></pre></div>
<pre><code>['id',
 'loanAmnt',
 'interestRate',
 'installment',
 'employmentTitle',
 'annualIncome',
 'purpose',
 'postCode',
 'regionCode',
 'dti',
 'delinquency_2years',
 'ficoRangeLow',
 'ficoRangeHigh',
 'openAcc',
 'pubRec',
 'pubRecBankruptcies',
 'revolBal',
 'revolUtil',
 'totalAcc',
 'title',
 'n0',
 'n1',
 'n2',
 'n2.1',
 'n4',
 'n5',
 'n6',
 'n7',
 'n8',
 'n9',
 'n10',
 'n13',
 'n14']
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">numerical_noserial_fea</span></pre></div>
<pre><code>['term',
 'homeOwnership',
 'verificationStatus',
 'isDefault',
 'initialListStatus',
 'applicationType',
 'policyCode',
 'n11',
 'n12']
</code></pre>
<ul>
<li>数值类别型变量分析</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'term'</span>].<span class="pl-en">value_counts</span>()<span class="pl-c">#离散型变量</span></pre></div>
<pre><code>3    606902
5    193098
Name: term, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'homeOwnership'</span>].<span class="pl-en">value_counts</span>()<span class="pl-c">#离散型变量</span></pre></div>
<pre><code>0    395732
1    317660
2     86309
3       185
5        81
4        33
Name: homeOwnership, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'verificationStatus'</span>].<span class="pl-en">value_counts</span>()<span class="pl-c">#离散型变量</span></pre></div>
<pre><code>1    309810
2    248968
0    241222
Name: verificationStatus, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'initialListStatus'</span>].<span class="pl-en">value_counts</span>()<span class="pl-c">#离散型变量</span></pre></div>
<pre><code>0    466438
1    333562
Name: initialListStatus, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'applicationType'</span>].<span class="pl-en">value_counts</span>()<span class="pl-c">#离散型变量</span></pre></div>
<pre><code>0    784586
1     15414
Name: applicationType, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'policyCode'</span>].<span class="pl-en">value_counts</span>()<span class="pl-c">#离散型变量，无用，全部一个值</span></pre></div>
<pre><code>1.0    800000
Name: policyCode, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'n11'</span>].<span class="pl-en">value_counts</span>()<span class="pl-c">#离散型变量，相差悬殊，用不用再分析</span></pre></div>
<pre><code>0.0    729682
1.0       540
2.0        24
4.0         1
3.0         1
Name: n11, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'n12'</span>].<span class="pl-en">value_counts</span>()<span class="pl-c">#离散型变量，相差悬殊，用不用再分析</span></pre></div>
<pre><code>0.0    757315
1.0      2281
2.0       115
3.0        16
4.0         3
Name: n12, dtype: int64
</code></pre>
<ul>
<li>数值连续型变量分析</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#每个数字特征得分布可视化</span>
<span class="pl-s1">f</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">melt</span>(<span class="pl-s1">data_train</span>, <span class="pl-s1">value_vars</span><span class="pl-c1">=</span><span class="pl-s1">numerical_serial_fea</span>)
<span class="pl-s1">g</span> <span class="pl-c1">=</span> <span class="pl-s1">sns</span>.<span class="pl-v">FacetGrid</span>(<span class="pl-s1">f</span>, <span class="pl-s1">col</span><span class="pl-c1">=</span><span class="pl-s">"variable"</span>,  <span class="pl-s1">col_wrap</span><span class="pl-c1">=</span><span class="pl-c1">2</span>, <span class="pl-s1">sharex</span><span class="pl-c1">=</span><span class="pl-c1">False</span>, <span class="pl-s1">sharey</span><span class="pl-c1">=</span><span class="pl-c1">False</span>)
<span class="pl-s1">g</span> <span class="pl-c1">=</span> <span class="pl-s1">g</span>.<span class="pl-en">map</span>(<span class="pl-s1">sns</span>.<span class="pl-s1">distplot</span>, <span class="pl-s">"value"</span>)</pre></div>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/97d3d6b3f85469da333ec31910f659ca96656b2a/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303434392e706e67"><img src="https://camo.githubusercontent.com/97d3d6b3f85469da333ec31910f659ca96656b2a/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303434392e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913011740449.png" style="max-width:100%;"></a></p>
<ul>
<li>查看某一个数值型变量的分布，查看变量是否符合正态分布，如果不符合正太分布的变量可以log化后再观察下是否符合正态分布。</li>
<li>如果想统一处理一批数据变标准化 必须把这些之前已经正态化的数据提出</li>
<li>正态化的原因：一些情况下正态非正态可以让模型更快的收敛，一些模型要求数据正态（eg. GMM、KNN）,保证数据不要过偏态即可，过于偏态可能会影响模型预测结果。</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#Ploting Transaction Amount Values Distribution</span>
<span class="pl-s1">plt</span>.<span class="pl-en">figure</span>(<span class="pl-s1">figsize</span><span class="pl-c1">=</span>(<span class="pl-c1">16</span>,<span class="pl-c1">12</span>))
<span class="pl-s1">plt</span>.<span class="pl-en">suptitle</span>(<span class="pl-s">'Transaction Values Distribution'</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">22</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">subplot</span>(<span class="pl-c1">221</span>)
<span class="pl-s1">sub_plot_1</span> <span class="pl-c1">=</span> <span class="pl-s1">sns</span>.<span class="pl-en">distplot</span>(<span class="pl-s1">data_train</span>[<span class="pl-s">'loanAmnt'</span>])
<span class="pl-s1">sub_plot_1</span>.<span class="pl-en">set_title</span>(<span class="pl-s">"loanAmnt Distribuition"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">18</span>)
<span class="pl-s1">sub_plot_1</span>.<span class="pl-en">set_xlabel</span>(<span class="pl-s">""</span>)
<span class="pl-s1">sub_plot_1</span>.<span class="pl-en">set_ylabel</span>(<span class="pl-s">"Probability"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">15</span>)

<span class="pl-s1">plt</span>.<span class="pl-en">subplot</span>(<span class="pl-c1">222</span>)
<span class="pl-s1">sub_plot_2</span> <span class="pl-c1">=</span> <span class="pl-s1">sns</span>.<span class="pl-en">distplot</span>(<span class="pl-s1">np</span>.<span class="pl-en">log</span>(<span class="pl-s1">data_train</span>[<span class="pl-s">'loanAmnt'</span>]))
<span class="pl-s1">sub_plot_2</span>.<span class="pl-en">set_title</span>(<span class="pl-s">"loanAmnt (Log) Distribuition"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">18</span>)
<span class="pl-s1">sub_plot_2</span>.<span class="pl-en">set_xlabel</span>(<span class="pl-s">""</span>)
<span class="pl-s1">sub_plot_2</span>.<span class="pl-en">set_ylabel</span>(<span class="pl-s">"Probability"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">15</span>)</pre></div>
<pre><code>Text(0, 0.5, 'Probability')
</code></pre>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/600a24c2ed3042fc43d2d678dfb825aec90b3088/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339392e706e67"><img src="https://camo.githubusercontent.com/600a24c2ed3042fc43d2d678dfb825aec90b3088/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339392e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913011740399.png" style="max-width:100%;"></a></p>
<ul>
<li>非数值类别型变量分析</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">category_fea</span></pre></div>
<pre><code>['grade', 'subGrade', 'employmentLength', 'issueDate', 'earliesCreditLine']
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'grade'</span>].<span class="pl-en">value_counts</span>()</pre></div>
<pre><code>B    233690
C    227118
A    139661
D    119453
E     55661
F     19053
G      5364
Name: grade, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'subGrade'</span>].<span class="pl-en">value_counts</span>()</pre></div>
<pre><code>C1    50763
B4    49516
B5    48965
B3    48600
C2    47068
C3    44751
C4    44272
B2    44227
B1    42382
C5    40264
A5    38045
A4    30928
D1    30538
D2    26528
A1    25909
D3    23410
A3    22655
A2    22124
D4    21139
D5    17838
E1    14064
E2    12746
E3    10925
E4     9273
E5     8653
F1     5925
F2     4340
F3     3577
F4     2859
F5     2352
G1     1759
G2     1231
G3      978
G4      751
G5      645
Name: subGrade, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'employmentLength'</span>].<span class="pl-en">value_counts</span>()</pre></div>
<pre><code>10+ years    262753
2 years       72358
&lt; 1 year      64237
3 years       64152
1 year        52489
5 years       50102
4 years       47985
6 years       37254
8 years       36192
7 years       35407
9 years       30272
Name: employmentLength, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'issueDate'</span>].<span class="pl-en">value_counts</span>()</pre></div>
<pre><code>2016-03-01    29066
2015-10-01    25525
2015-07-01    24496
2015-12-01    23245
2014-10-01    21461
              ...  
2007-08-01       23
2007-07-01       21
2008-09-01       19
2007-09-01        7
2007-06-01        1
Name: issueDate, Length: 139, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'earliesCreditLine'</span>].<span class="pl-en">value_counts</span>()</pre></div>
<pre><code>Aug-2001    5567
Sep-2003    5403
Aug-2002    5403
Oct-2001    5258
Aug-2000    5246
            ... 
May-1960       1
Apr-1958       1
Feb-1960       1
Aug-1946       1
Mar-1958       1
Name: earliesCreditLine, Length: 720, dtype: int64
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">data_train</span>[<span class="pl-s">'isDefault'</span>].<span class="pl-en">value_counts</span>()</pre></div>
<pre><code>0    640390
1    159610
Name: isDefault, dtype: int64
</code></pre>
<h3><a id="user-content-总结-1" class="anchor" aria-hidden="true" href="#总结-1"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>总结：</h3>
<ul>
<li>上面我们用value_counts()等函数看了特征属性的分布，但是图表是概括原始信息最便捷的方式。</li>
<li>数无形时少直觉。</li>
<li>同一份数据集，在不同的尺度刻画上显示出来的图形反映的规律是不一样的。python将数据转化成图表，但结论是否正确需要由你保证。</li>
</ul>
<h3><a id="user-content-236-变量分布可视化" class="anchor" aria-hidden="true" href="#236-变量分布可视化"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.6 变量分布可视化</h3>
<h4><a id="user-content-单一变量分布可视化" class="anchor" aria-hidden="true" href="#单一变量分布可视化"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>单一变量分布可视化</h4>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">plt</span>.<span class="pl-en">figure</span>(<span class="pl-s1">figsize</span><span class="pl-c1">=</span>(<span class="pl-c1">8</span>, <span class="pl-c1">8</span>))
<span class="pl-s1">sns</span>.<span class="pl-en">barplot</span>(<span class="pl-s1">data_train</span>[<span class="pl-s">"employmentLength"</span>].<span class="pl-en">value_counts</span>(<span class="pl-s1">dropna</span><span class="pl-c1">=</span><span class="pl-c1">False</span>)[:<span class="pl-c1">20</span>],
            <span class="pl-s1">data_train</span>[<span class="pl-s">"employmentLength"</span>].<span class="pl-en">value_counts</span>(<span class="pl-s1">dropna</span><span class="pl-c1">=</span><span class="pl-c1">False</span>).<span class="pl-en">keys</span>()[:<span class="pl-c1">20</span>])
<span class="pl-s1">plt</span>.<span class="pl-en">show</span>()</pre></div>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/9ab0e6ed1d06edcad8a96ff3eeb79f73cad24a68/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339312e706e67"><img src="https://camo.githubusercontent.com/9ab0e6ed1d06edcad8a96ff3eeb79f73cad24a68/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339312e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913011740391.png" style="max-width:100%;"></a></p>
<h4><a id="user-content-根绝y值不同可视化x某个特征的分布" class="anchor" aria-hidden="true" href="#根绝y值不同可视化x某个特征的分布"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>根绝y值不同可视化x某个特征的分布</h4>
<ul>
<li>首先查看类别型变量在不同y值上的分布</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">train_loan_fr</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-s1">loc</span>[<span class="pl-s1">data_train</span>[<span class="pl-s">'isDefault'</span>] <span class="pl-c1">==</span> <span class="pl-c1">1</span>]
<span class="pl-s1">train_loan_nofr</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-s1">loc</span>[<span class="pl-s1">data_train</span>[<span class="pl-s">'isDefault'</span>] <span class="pl-c1">==</span> <span class="pl-c1">0</span>]</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">fig</span>, ((<span class="pl-s1">ax1</span>, <span class="pl-s1">ax2</span>), (<span class="pl-s1">ax3</span>, <span class="pl-s1">ax4</span>)) <span class="pl-c1">=</span> <span class="pl-s1">plt</span>.<span class="pl-en">subplots</span>(<span class="pl-c1">2</span>, <span class="pl-c1">2</span>, <span class="pl-s1">figsize</span><span class="pl-c1">=</span>(<span class="pl-c1">15</span>, <span class="pl-c1">8</span>))
<span class="pl-s1">train_loan_fr</span>.<span class="pl-en">groupby</span>(<span class="pl-s">'grade'</span>)[<span class="pl-s">'grade'</span>].<span class="pl-en">count</span>().<span class="pl-en">plot</span>(<span class="pl-s1">kind</span><span class="pl-c1">=</span><span class="pl-s">'barh'</span>, <span class="pl-s1">ax</span><span class="pl-c1">=</span><span class="pl-s1">ax1</span>, <span class="pl-s1">title</span><span class="pl-c1">=</span><span class="pl-s">'Count of grade fraud'</span>)
<span class="pl-s1">train_loan_nofr</span>.<span class="pl-en">groupby</span>(<span class="pl-s">'grade'</span>)[<span class="pl-s">'grade'</span>].<span class="pl-en">count</span>().<span class="pl-en">plot</span>(<span class="pl-s1">kind</span><span class="pl-c1">=</span><span class="pl-s">'barh'</span>, <span class="pl-s1">ax</span><span class="pl-c1">=</span><span class="pl-s1">ax2</span>, <span class="pl-s1">title</span><span class="pl-c1">=</span><span class="pl-s">'Count of grade non-fraud'</span>)
<span class="pl-s1">train_loan_fr</span>.<span class="pl-en">groupby</span>(<span class="pl-s">'employmentLength'</span>)[<span class="pl-s">'employmentLength'</span>].<span class="pl-en">count</span>().<span class="pl-en">plot</span>(<span class="pl-s1">kind</span><span class="pl-c1">=</span><span class="pl-s">'barh'</span>, <span class="pl-s1">ax</span><span class="pl-c1">=</span><span class="pl-s1">ax3</span>, <span class="pl-s1">title</span><span class="pl-c1">=</span><span class="pl-s">'Count of employmentLength fraud'</span>)
<span class="pl-s1">train_loan_nofr</span>.<span class="pl-en">groupby</span>(<span class="pl-s">'employmentLength'</span>)[<span class="pl-s">'employmentLength'</span>].<span class="pl-en">count</span>().<span class="pl-en">plot</span>(<span class="pl-s1">kind</span><span class="pl-c1">=</span><span class="pl-s">'barh'</span>, <span class="pl-s1">ax</span><span class="pl-c1">=</span><span class="pl-s1">ax4</span>, <span class="pl-s1">title</span><span class="pl-c1">=</span><span class="pl-s">'Count of employmentLength non-fraud'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">show</span>()</pre></div>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/60c0c7cc071b5aaf81f168863e9ab3fa6a4aace3/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339382e706e67"><img src="https://camo.githubusercontent.com/60c0c7cc071b5aaf81f168863e9ab3fa6a4aace3/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339382e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913011740398.png" style="max-width:100%;"></a></p>
<ul>
<li>其次查看连续型变量在不同y值上的分布</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">fig</span>, ((<span class="pl-s1">ax1</span>, <span class="pl-s1">ax2</span>)) <span class="pl-c1">=</span> <span class="pl-s1">plt</span>.<span class="pl-en">subplots</span>(<span class="pl-c1">1</span>, <span class="pl-c1">2</span>, <span class="pl-s1">figsize</span><span class="pl-c1">=</span>(<span class="pl-c1">15</span>, <span class="pl-c1">6</span>))
<span class="pl-s1">data_train</span>.<span class="pl-s1">loc</span>[<span class="pl-s1">data_train</span>[<span class="pl-s">'isDefault'</span>] <span class="pl-c1">==</span> <span class="pl-c1">1</span>] \
    [<span class="pl-s">'loanAmnt'</span>].<span class="pl-en">apply</span>(<span class="pl-s1">np</span>.<span class="pl-s1">log</span>) \
    .<span class="pl-en">plot</span>(<span class="pl-s1">kind</span><span class="pl-c1">=</span><span class="pl-s">'hist'</span>,
          <span class="pl-s1">bins</span><span class="pl-c1">=</span><span class="pl-c1">100</span>,
          <span class="pl-s1">title</span><span class="pl-c1">=</span><span class="pl-s">'Log Loan Amt - Fraud'</span>,
          <span class="pl-s1">color</span><span class="pl-c1">=</span><span class="pl-s">'r'</span>,
          <span class="pl-s1">xlim</span><span class="pl-c1">=</span>(<span class="pl-c1">-</span><span class="pl-c1">3</span>, <span class="pl-c1">10</span>),
         <span class="pl-s1">ax</span><span class="pl-c1">=</span> <span class="pl-s1">ax1</span>)
<span class="pl-s1">data_train</span>.<span class="pl-s1">loc</span>[<span class="pl-s1">data_train</span>[<span class="pl-s">'isDefault'</span>] <span class="pl-c1">==</span> <span class="pl-c1">0</span>] \
    [<span class="pl-s">'loanAmnt'</span>].<span class="pl-en">apply</span>(<span class="pl-s1">np</span>.<span class="pl-s1">log</span>) \
    .<span class="pl-en">plot</span>(<span class="pl-s1">kind</span><span class="pl-c1">=</span><span class="pl-s">'hist'</span>,
          <span class="pl-s1">bins</span><span class="pl-c1">=</span><span class="pl-c1">100</span>,
          <span class="pl-s1">title</span><span class="pl-c1">=</span><span class="pl-s">'Log Loan Amt - Not Fraud'</span>,
          <span class="pl-s1">color</span><span class="pl-c1">=</span><span class="pl-s">'b'</span>,
          <span class="pl-s1">xlim</span><span class="pl-c1">=</span>(<span class="pl-c1">-</span><span class="pl-c1">3</span>, <span class="pl-c1">10</span>),
         <span class="pl-s1">ax</span><span class="pl-c1">=</span><span class="pl-s1">ax2</span>)</pre></div>
<pre><code>&lt;matplotlib.axes._subplots.AxesSubplot at 0x126a44b50&gt;
</code></pre>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/eeff3f5657e255b73ad03543fd8d44f1fc2666ba/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339332e706e67"><img src="https://camo.githubusercontent.com/eeff3f5657e255b73ad03543fd8d44f1fc2666ba/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339332e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913011740393.png" style="max-width:100%;"></a></p>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">total</span> <span class="pl-c1">=</span> <span class="pl-en">len</span>(<span class="pl-s1">data_train</span>)
<span class="pl-s1">total_amt</span> <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>.<span class="pl-en">groupby</span>([<span class="pl-s">'isDefault'</span>])[<span class="pl-s">'loanAmnt'</span>].<span class="pl-en">sum</span>().<span class="pl-en">sum</span>()
<span class="pl-s1">plt</span>.<span class="pl-en">figure</span>(<span class="pl-s1">figsize</span><span class="pl-c1">=</span>(<span class="pl-c1">12</span>,<span class="pl-c1">5</span>))
<span class="pl-s1">plt</span>.<span class="pl-en">subplot</span>(<span class="pl-c1">121</span>)<span class="pl-c">##1代表行，2代表列，所以一共有2个图，1代表此时绘制第一个图。</span>
<span class="pl-s1">plot_tr</span> <span class="pl-c1">=</span> <span class="pl-s1">sns</span>.<span class="pl-en">countplot</span>(<span class="pl-s1">x</span><span class="pl-c1">=</span><span class="pl-s">'isDefault'</span>,<span class="pl-s1">data</span><span class="pl-c1">=</span><span class="pl-s1">data_train</span>)<span class="pl-c">#data_train‘isDefault’这个特征每种类别的数量**</span>
<span class="pl-s1">plot_tr</span>.<span class="pl-en">set_title</span>(<span class="pl-s">"Fraud Loan Distribution <span class="pl-cce">\n</span> 0: good user | 1: bad user"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">14</span>)
<span class="pl-s1">plot_tr</span>.<span class="pl-en">set_xlabel</span>(<span class="pl-s">"Is fraud by count"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">16</span>)
<span class="pl-s1">plot_tr</span>.<span class="pl-en">set_ylabel</span>(<span class="pl-s">'Count'</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">16</span>)
<span class="pl-k">for</span> <span class="pl-s1">p</span> <span class="pl-c1">in</span> <span class="pl-s1">plot_tr</span>.<span class="pl-s1">patches</span>:
    <span class="pl-s1">height</span> <span class="pl-c1">=</span> <span class="pl-s1">p</span>.<span class="pl-en">get_height</span>()
    <span class="pl-s1">plot_tr</span>.<span class="pl-en">text</span>(<span class="pl-s1">p</span>.<span class="pl-en">get_x</span>()<span class="pl-c1">+</span><span class="pl-s1">p</span>.<span class="pl-en">get_width</span>()<span class="pl-c1">/</span><span class="pl-c1">2.</span>,
            <span class="pl-s1">height</span> <span class="pl-c1">+</span> <span class="pl-c1">3</span>,
            <span class="pl-s">'{:1.2f}%'</span>.<span class="pl-en">format</span>(<span class="pl-s1">height</span><span class="pl-c1">/</span><span class="pl-s1">total</span><span class="pl-c1">*</span><span class="pl-c1">100</span>),
            <span class="pl-s1">ha</span><span class="pl-c1">=</span><span class="pl-s">"center"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">15</span>) 
    
<span class="pl-s1">percent_amt</span> <span class="pl-c1">=</span> (<span class="pl-s1">data_train</span>.<span class="pl-en">groupby</span>([<span class="pl-s">'isDefault'</span>])[<span class="pl-s">'loanAmnt'</span>].<span class="pl-en">sum</span>())
<span class="pl-s1">percent_amt</span> <span class="pl-c1">=</span> <span class="pl-s1">percent_amt</span>.<span class="pl-en">reset_index</span>()
<span class="pl-s1">plt</span>.<span class="pl-en">subplot</span>(<span class="pl-c1">122</span>)
<span class="pl-s1">plot_tr_2</span> <span class="pl-c1">=</span> <span class="pl-s1">sns</span>.<span class="pl-en">barplot</span>(<span class="pl-s1">x</span><span class="pl-c1">=</span><span class="pl-s">'isDefault'</span>, <span class="pl-s1">y</span><span class="pl-c1">=</span><span class="pl-s">'loanAmnt'</span>,  <span class="pl-s1">dodge</span><span class="pl-c1">=</span><span class="pl-c1">True</span>, <span class="pl-s1">data</span><span class="pl-c1">=</span><span class="pl-s1">percent_amt</span>)
<span class="pl-s1">plot_tr_2</span>.<span class="pl-en">set_title</span>(<span class="pl-s">"Total Amount in loanAmnt  <span class="pl-cce">\n</span> 0: good user | 1: bad user"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">14</span>)
<span class="pl-s1">plot_tr_2</span>.<span class="pl-en">set_xlabel</span>(<span class="pl-s">"Is fraud by percent"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">16</span>)
<span class="pl-s1">plot_tr_2</span>.<span class="pl-en">set_ylabel</span>(<span class="pl-s">'Total Loan Amount Scalar'</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">16</span>)
<span class="pl-k">for</span> <span class="pl-s1">p</span> <span class="pl-c1">in</span> <span class="pl-s1">plot_tr_2</span>.<span class="pl-s1">patches</span>:
    <span class="pl-s1">height</span> <span class="pl-c1">=</span> <span class="pl-s1">p</span>.<span class="pl-en">get_height</span>()
    <span class="pl-s1">plot_tr_2</span>.<span class="pl-en">text</span>(<span class="pl-s1">p</span>.<span class="pl-en">get_x</span>()<span class="pl-c1">+</span><span class="pl-s1">p</span>.<span class="pl-en">get_width</span>()<span class="pl-c1">/</span><span class="pl-c1">2.</span>,
            <span class="pl-s1">height</span> <span class="pl-c1">+</span> <span class="pl-c1">3</span>,
            <span class="pl-s">'{:1.2f}%'</span>.<span class="pl-en">format</span>(<span class="pl-s1">height</span><span class="pl-c1">/</span><span class="pl-s1">total_amt</span> <span class="pl-c1">*</span> <span class="pl-c1">100</span>),
            <span class="pl-s1">ha</span><span class="pl-c1">=</span><span class="pl-s">"center"</span>, <span class="pl-s1">fontsize</span><span class="pl-c1">=</span><span class="pl-c1">15</span>)     </pre></div>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/f60a6ddd25e15c606517ab3193725d2846038033/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339352e706e67"><img src="https://camo.githubusercontent.com/f60a6ddd25e15c606517ab3193725d2846038033/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303339352e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913011740395.png" style="max-width:100%;"></a></p>
<h3><a id="user-content-236-时间格式数据处理及查看" class="anchor" aria-hidden="true" href="#236-时间格式数据处理及查看"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.6 时间格式数据处理及查看</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#转化成时间格式  issueDateDT特征表示数据日期离数据集中日期最早的日期（2007-06-01）的天数</span>
<span class="pl-s1">data_train</span>[<span class="pl-s">'issueDate'</span>] <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">to_datetime</span>(<span class="pl-s1">data_train</span>[<span class="pl-s">'issueDate'</span>],<span class="pl-s1">format</span><span class="pl-c1">=</span><span class="pl-s">'%Y-%m-%d'</span>)
<span class="pl-s1">startdate</span> <span class="pl-c1">=</span> <span class="pl-s1">datetime</span>.<span class="pl-s1">datetime</span>.<span class="pl-en">strptime</span>(<span class="pl-s">'2007-06-01'</span>, <span class="pl-s">'%Y-%m-%d'</span>)
<span class="pl-s1">data_train</span>[<span class="pl-s">'issueDateDT'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_train</span>[<span class="pl-s">'issueDate'</span>].<span class="pl-en">apply</span>(<span class="pl-k">lambda</span> <span class="pl-s1">x</span>: <span class="pl-s1">x</span><span class="pl-c1">-</span><span class="pl-s1">startdate</span>).<span class="pl-s1">dt</span>.<span class="pl-s1">days</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#转化成时间格式</span>
<span class="pl-s1">data_test_a</span>[<span class="pl-s">'issueDate'</span>] <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">to_datetime</span>(<span class="pl-s1">data_train</span>[<span class="pl-s">'issueDate'</span>],<span class="pl-s1">format</span><span class="pl-c1">=</span><span class="pl-s">'%Y-%m-%d'</span>)
<span class="pl-s1">startdate</span> <span class="pl-c1">=</span> <span class="pl-s1">datetime</span>.<span class="pl-s1">datetime</span>.<span class="pl-en">strptime</span>(<span class="pl-s">'2007-06-01'</span>, <span class="pl-s">'%Y-%m-%d'</span>)
<span class="pl-s1">data_test_a</span>[<span class="pl-s">'issueDateDT'</span>] <span class="pl-c1">=</span> <span class="pl-s1">data_test_a</span>[<span class="pl-s">'issueDate'</span>].<span class="pl-en">apply</span>(<span class="pl-k">lambda</span> <span class="pl-s1">x</span>: <span class="pl-s1">x</span><span class="pl-c1">-</span><span class="pl-s1">startdate</span>).<span class="pl-s1">dt</span>.<span class="pl-s1">days</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">plt</span>.<span class="pl-en">hist</span>(<span class="pl-s1">data_train</span>[<span class="pl-s">'issueDateDT'</span>], <span class="pl-s1">label</span><span class="pl-c1">=</span><span class="pl-s">'train'</span>);
<span class="pl-s1">plt</span>.<span class="pl-en">hist</span>(<span class="pl-s1">data_test_a</span>[<span class="pl-s">'issueDateDT'</span>], <span class="pl-s1">label</span><span class="pl-c1">=</span><span class="pl-s">'test'</span>);
<span class="pl-s1">plt</span>.<span class="pl-en">legend</span>();
<span class="pl-s1">plt</span>.<span class="pl-en">title</span>(<span class="pl-s">'Distribution of issueDateDT dates'</span>);
<span class="pl-c">#train 和 test issueDateDT 日期有重叠 所以使用基于时间的分割进行验证是不明智的</span></pre></div>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/3cbbc820dfc0bc9c97aafba6d404265576e207d8/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303337372e706e67"><img src="https://camo.githubusercontent.com/3cbbc820dfc0bc9c97aafba6d404265576e207d8/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031313734303337372e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913011740377.png" style="max-width:100%;"></a></p>
<h3><a id="user-content-237-掌握透视图可以让我们更好的了解数据" class="anchor" aria-hidden="true" href="#237-掌握透视图可以让我们更好的了解数据"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.7 掌握透视图可以让我们更好的了解数据</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-c">#透视图 索引可以有多个，“columns（列）”是可选的，聚合函数aggfunc最后是被应用到了变量“values”中你所列举的项目上。</span>
<span class="pl-s1">pivot</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">pivot_table</span>(<span class="pl-s1">data_train</span>, <span class="pl-s1">index</span><span class="pl-c1">=</span>[<span class="pl-s">'grade'</span>], <span class="pl-s1">columns</span><span class="pl-c1">=</span>[<span class="pl-s">'issueDateDT'</span>], <span class="pl-s1">values</span><span class="pl-c1">=</span>[<span class="pl-s">'loanAmnt'</span>], <span class="pl-s1">aggfunc</span><span class="pl-c1">=</span><span class="pl-s1">np</span>.<span class="pl-s1">sum</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">pivot</span></pre></div>
<div>
&lt;style scoped&gt;
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }
<pre><code>.dataframe tbody tr th {
    vertical-align: top;
}

.dataframe thead tr th {
    text-align: left;
}

.dataframe thead tr:last-of-type th {
    text-align: right;
}
</code></pre>
&lt;/style&gt;
<table border="1">
  <thead>
    <tr>
      <th></th>
      <th colspan="21">loanAmnt</th>
    </tr>
    <tr>
      <th>issueDateDT</th>
      <th>0</th>
      <th>30</th>
      <th>61</th>
      <th>92</th>
      <th>122</th>
      <th>153</th>
      <th>183</th>
      <th>214</th>
      <th>245</th>
      <th>274</th>
      <th>...</th>
      <th>3926</th>
      <th>3957</th>
      <th>3987</th>
      <th>4018</th>
      <th>4048</th>
      <th>4079</th>
      <th>4110</th>
      <th>4140</th>
      <th>4171</th>
      <th>4201</th>
    </tr>
    <tr>
      <th>grade</th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>A</th>
      <td>NaN</td>
      <td>53650.0</td>
      <td>42000.0</td>
      <td>19500.0</td>
      <td>34425.0</td>
      <td>63950.0</td>
      <td>43500.0</td>
      <td>168825.0</td>
      <td>85600.0</td>
      <td>101825.0</td>
      <td>...</td>
      <td>13093850.0</td>
      <td>11757325.0</td>
      <td>11945975.0</td>
      <td>9144000.0</td>
      <td>7977650.0</td>
      <td>6888900.0</td>
      <td>5109800.0</td>
      <td>3919275.0</td>
      <td>2694025.0</td>
      <td>2245625.0</td>
    </tr>
    <tr>
      <th>B</th>
      <td>NaN</td>
      <td>13000.0</td>
      <td>24000.0</td>
      <td>32125.0</td>
      <td>7025.0</td>
      <td>95750.0</td>
      <td>164300.0</td>
      <td>303175.0</td>
      <td>434425.0</td>
      <td>538450.0</td>
      <td>...</td>
      <td>16863100.0</td>
      <td>17275175.0</td>
      <td>16217500.0</td>
      <td>11431350.0</td>
      <td>8967750.0</td>
      <td>7572725.0</td>
      <td>4884600.0</td>
      <td>4329400.0</td>
      <td>3922575.0</td>
      <td>3257100.0</td>
    </tr>
    <tr>
      <th>C</th>
      <td>NaN</td>
      <td>68750.0</td>
      <td>8175.0</td>
      <td>10000.0</td>
      <td>61800.0</td>
      <td>52550.0</td>
      <td>175375.0</td>
      <td>151100.0</td>
      <td>243725.0</td>
      <td>393150.0</td>
      <td>...</td>
      <td>17502375.0</td>
      <td>17471500.0</td>
      <td>16111225.0</td>
      <td>11973675.0</td>
      <td>10184450.0</td>
      <td>7765000.0</td>
      <td>5354450.0</td>
      <td>4552600.0</td>
      <td>2870050.0</td>
      <td>2246250.0</td>
    </tr>
    <tr>
      <th>D</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>5500.0</td>
      <td>2850.0</td>
      <td>28625.0</td>
      <td>NaN</td>
      <td>167975.0</td>
      <td>171325.0</td>
      <td>192900.0</td>
      <td>269325.0</td>
      <td>...</td>
      <td>11403075.0</td>
      <td>10964150.0</td>
      <td>10747675.0</td>
      <td>7082050.0</td>
      <td>7189625.0</td>
      <td>5195700.0</td>
      <td>3455175.0</td>
      <td>3038500.0</td>
      <td>2452375.0</td>
      <td>1771750.0</td>
    </tr>
    <tr>
      <th>E</th>
      <td>7500.0</td>
      <td>NaN</td>
      <td>10000.0</td>
      <td>NaN</td>
      <td>17975.0</td>
      <td>1500.0</td>
      <td>94375.0</td>
      <td>116450.0</td>
      <td>42000.0</td>
      <td>139775.0</td>
      <td>...</td>
      <td>3983050.0</td>
      <td>3410125.0</td>
      <td>3107150.0</td>
      <td>2341825.0</td>
      <td>2225675.0</td>
      <td>1643675.0</td>
      <td>1091025.0</td>
      <td>1131625.0</td>
      <td>883950.0</td>
      <td>802425.0</td>
    </tr>
    <tr>
      <th>F</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>31250.0</td>
      <td>2125.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>49000.0</td>
      <td>27000.0</td>
      <td>43000.0</td>
      <td>...</td>
      <td>1074175.0</td>
      <td>868925.0</td>
      <td>761675.0</td>
      <td>685325.0</td>
      <td>665750.0</td>
      <td>685200.0</td>
      <td>316700.0</td>
      <td>315075.0</td>
      <td>72300.0</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>G</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>24625.0</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>...</td>
      <td>56100.0</td>
      <td>243275.0</td>
      <td>224825.0</td>
      <td>64050.0</td>
      <td>198575.0</td>
      <td>245825.0</td>
      <td>53125.0</td>
      <td>23750.0</td>
      <td>25100.0</td>
      <td>1000.0</td>
    </tr>
  </tbody>
</table>
<p>7 rows × 139 columns</p>
</div>
<h3><a id="user-content-238-用pandas_profiling生成数据报告" class="anchor" aria-hidden="true" href="#238-用pandas_profiling生成数据报告"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.3.8 用pandas_profiling生成数据报告</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-k">import</span> <span class="pl-s1">pandas_profiling</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">pfr</span> <span class="pl-c1">=</span> <span class="pl-s1">pandas_profiling</span>.<span class="pl-v">ProfileReport</span>(<span class="pl-s1">data_train</span>)
<span class="pl-s1">pfr</span>.<span class="pl-en">to_file</span>(<span class="pl-s">"./example.html"</span>)</pre></div>
<h2><a id="user-content-24-总结" class="anchor" aria-hidden="true" href="#24-总结"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>2.4 总结</h2>
<p>数据探索性分析是我们初步了解数据，熟悉数据为特征工程做准备的阶段，甚至很多时候EDA阶段提取出来的特征可以直接当作规则来用。可见EDA的重要性，这个阶段的主要工作还是借助于各个简单的统计量来对数据整体的了解，分析各个类型变量相互之间的关系，以及用合适的图形可视化出来直观观察。希望本节内容能给初学者带来帮助，更期待各位学习者对其中的不足提出建议。</p>

    </div>

</div>

    </main>
  </div>

  </div>

        
<div class="footer container-xl width-full p-responsive" role="contentinfo">
    <div class="position-relative d-flex flex-row-reverse flex-lg-row flex-wrap flex-lg-nowrap flex-justify-center flex-lg-justify-between pt-6 pb-2 mt-6 f6 text-gray border-top border-gray-light ">
      <ul class="list-style-none d-flex flex-wrap col-12 col-lg-5 flex-justify-center flex-lg-justify-between mb-2 mb-lg-0">
        <li class="mr-3 mr-lg-0">&copy; 2020 GitHub, Inc.</li>
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to terms, text:terms" href="https://github.com/site/terms">Terms</a></li>
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to privacy, text:privacy" href="https://github.com/site/privacy">Privacy</a></li>
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to security, text:security" href="https://github.com/security">Security</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://githubstatus.com/" data-ga-click="Footer, go to status, text:status">Status</a></li>
          <li><a data-ga-click="Footer, go to help, text:help" href="https://docs.github.com">Help</a></li>
      </ul>

      <a aria-label="Homepage" title="GitHub" class="footer-octicon d-none d-lg-block mx-lg-4" href="https://github.com">
        <svg height="24" class="octicon octicon-mark-github" viewBox="0 0 16 16" version="1.1" width="24" aria-hidden="true"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0016 8c0-4.42-3.58-8-8-8z"></path></svg>
</a>
      <ul class="list-style-none d-flex flex-wrap col-12 col-lg-5 flex-justify-center flex-lg-justify-between mb-2 mb-lg-0">
          <li class="mr-3 mr-lg-0"><a data-ga-click="Footer, go to contact, text:contact" href="https://github.com/contact">Contact GitHub</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://github.com/pricing" data-ga-click="Footer, go to Pricing, text:Pricing">Pricing</a></li>
        <li class="mr-3 mr-lg-0"><a href="https://docs.github.com" data-ga-click="Footer, go to api, text:api">API</a></li>
        <li class="mr-3 mr-lg-0"><a href="https://services.github.com" data-ga-click="Footer, go to training, text:training">Training</a></li>
          <li class="mr-3 mr-lg-0"><a href="https://github.blog" data-ga-click="Footer, go to blog, text:blog">Blog</a></li>
          <li><a data-ga-click="Footer, go to about, text:about" href="https://github.com/about">About</a></li>
      </ul>
</div>



  </body>
</html>

