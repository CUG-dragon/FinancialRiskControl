




<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
  <link rel="dns-prefetch" href="https://github.githubassets.com">
  <link rel="dns-prefetch" href="https://avatars0.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars1.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars2.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars3.githubusercontent.com">
  <link rel="dns-prefetch" href="https://github-cloud.s3.amazonaws.com">
  <link rel="dns-prefetch" href="https://user-images.githubusercontent.com/">



  <link crossorigin="anonymous" media="all" integrity="sha512-lC+Z9kBc6E9r9umj6DgEEoQP7CX8RgGJGegRUJbthY1Bus2eemD1Kkc1Wbacj7hxeuvVCuyeqfNsKZWxqt1uIw==" rel="stylesheet" href="https://github.githubassets.com/assets/frameworks-942f99f6405ce84f6bf6e9a3e8380412.css" />
  
    <link crossorigin="anonymous" media="all" integrity="sha512-vckDZXppKshlQSYtQYc4xzzjru24vQuDCkQV/cKmhrjGOM1Icv4j8ndrOloEmfUYPHhq60/qlJqeP/fY371Pow==" rel="stylesheet" href="https://github.githubassets.com/assets/github-bdc903657a692ac86541262d418738c7.css" />
    
       
  
<h3><a id="user-content-124-赛题流程" class="anchor" aria-hidden="true" href="#124-赛题流程"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>1.2.4. 赛题流程</h3>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/baf3abb3b945608363c4e7a0be0a8a158629463b/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031303232363131302e706e67"><img src="https://camo.githubusercontent.com/baf3abb3b945608363c4e7a0be0a8a158629463b/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031303232363131302e706e67" alt="1_1.png" data-canonical-src="https://img-blog.csdnimg.cn/20200913010226110.png" style="max-width:100%;"></a></p>
<h3><a id="user-content-13-代码示例" class="anchor" aria-hidden="true" href="#13-代码示例"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>1.3 代码示例</h3>
<p>本部分为对于数据读取和指标评价的示例。</p>
<h3><a id="user-content-131-数据读取pandas" class="anchor" aria-hidden="true" href="#131-数据读取pandas"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>1.3.1 数据读取pandas</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-k">import</span> <span class="pl-s1">pandas</span> <span class="pl-k">as</span> <span class="pl-s1">pd</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">train</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">'train.csv'</span>)
<span class="pl-s1">testA</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">'testA.csv'</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-en">print</span>(<span class="pl-s">'Train data shape:'</span>,<span class="pl-s1">train</span>.<span class="pl-s1">shape</span>)
<span class="pl-en">print</span>(<span class="pl-s">'TestA data shape:'</span>,<span class="pl-s1">testA</span>.<span class="pl-s1">shape</span>)</pre></div>
<pre><code>Train data shape: (800000, 47)
TestA data shape: (200000, 48)
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">train</span>.<span class="pl-en">head</span>()</pre></div>
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
      <th>3</th>
      <td>3</td>
      <td>11000.0</td>
      <td>3</td>
      <td>7.26</td>
      <td>340.96</td>
      <td>A</td>
      <td>A4</td>
      <td>46854.0</td>
      <td>10+ years</td> 
      <td>1</td>
      <td>...</td>
      <td>16.0</td>
      <td>4.0</td>
      <td>7.0</td>
      <td>21.0</td>
      <td>6.0</td>
      <td>9.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>1.0</td>
    </tr>
    <tr>
      <th>4</th>
      <td>4</td>
      <td>3000.0</td>
      <td>3</td>
      <td>12.99</td>
      <td>101.07</td>
      <td>C</td>
      <td>C2</td>
      <td>54.0</td>
      <td>NaN</td>
      <td>1</td>
      <td>...</td>
      <td>4.0</td>
      <td>9.0</td>
      <td>10.0</td>
      <td>15.0</td>
      <td>7.0</td>
      <td>12.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>0.0</td>
      <td>4.0</td>
    </tr>
  </tbody>
</table>
<p>5 rows × 47 columns</p>
</div>
<h3><a id="user-content-132-分类指标评价计算示例" class="anchor" aria-hidden="true" href="#132-分类指标评价计算示例"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>1.3.2 分类指标评价计算示例</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-c">## 混淆矩阵</span>
<span class="pl-k">import</span> <span class="pl-s1">numpy</span> <span class="pl-k">as</span> <span class="pl-s1">np</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">metrics</span> <span class="pl-k">import</span> <span class="pl-s1">confusion_matrix</span>
<span class="pl-s1">y_pred</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>]
<span class="pl-s1">y_true</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>]
<span class="pl-en">print</span>(<span class="pl-s">'混淆矩阵:<span class="pl-cce">\n</span>'</span>,<span class="pl-en">confusion_matrix</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_pred</span>))</pre></div>
<pre><code>混淆矩阵:
 [[1 1]
 [1 1]]
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-c">## accuracy</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">metrics</span> <span class="pl-k">import</span> <span class="pl-s1">accuracy_score</span>
<span class="pl-s1">y_pred</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>]
<span class="pl-s1">y_true</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>]
<span class="pl-en">print</span>(<span class="pl-s">'ACC:'</span>,<span class="pl-en">accuracy_score</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_pred</span>))</pre></div>
<pre><code>ACC: 0.5
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-c">## Precision,Recall,F1-score</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span> <span class="pl-k">import</span> <span class="pl-s1">metrics</span>
<span class="pl-s1">y_pred</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>]
<span class="pl-s1">y_true</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>]
<span class="pl-en">print</span>(<span class="pl-s">'Precision'</span>,<span class="pl-s1">metrics</span>.<span class="pl-en">precision_score</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_pred</span>))
<span class="pl-en">print</span>(<span class="pl-s">'Recall'</span>,<span class="pl-s1">metrics</span>.<span class="pl-en">recall_score</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_pred</span>))
<span class="pl-en">print</span>(<span class="pl-s">'F1-score:'</span>,<span class="pl-s1">metrics</span>.<span class="pl-en">f1_score</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_pred</span>))</pre></div>
<pre><code>Precision 0.5
Recall 0.5
F1-score: 0.5
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-c">## P-R曲线</span>
<span class="pl-k">import</span> <span class="pl-s1">matplotlib</span>.<span class="pl-s1">pyplot</span> <span class="pl-k">as</span> <span class="pl-s1">plt</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">metrics</span> <span class="pl-k">import</span> <span class="pl-s1">precision_recall_curve</span>
<span class="pl-s1">y_pred</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>]
<span class="pl-s1">y_true</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>]
<span class="pl-s1">precision</span>, <span class="pl-s1">recall</span>, <span class="pl-s1">thresholds</span> <span class="pl-c1">=</span> <span class="pl-en">precision_recall_curve</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_pred</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">plot</span>(<span class="pl-s1">precision</span>, <span class="pl-s1">recall</span>)</pre></div>
<pre><code>[&lt;matplotlib.lines.Line2D at 0x2170d0d6108&gt;]
</code></pre>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/62cfda126d963927ceafa23a4b218e155a3d2479/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f323032303039313330313032323639362e706e67"><img src="https://camo.githubusercontent.com/62cfda126d963927ceafa23a4b218e155a3d2479/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f323032303039313330313032323639362e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/2020091301022696.png" style="max-width:100%;"></a></p>
<div class="highlight highlight-source-python"><pre><span class="pl-c">## ROC曲线</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">metrics</span> <span class="pl-k">import</span> <span class="pl-s1">roc_curve</span>
<span class="pl-s1">y_pred</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>]
<span class="pl-s1">y_true</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>]
<span class="pl-v">FPR</span>,<span class="pl-v">TPR</span>,<span class="pl-s1">thresholds</span><span class="pl-c1">=</span><span class="pl-en">roc_curve</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_pred</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">title</span>(<span class="pl-s">'ROC'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">plot</span>(<span class="pl-v">FPR</span>, <span class="pl-v">TPR</span>,<span class="pl-s">'b'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">plot</span>([<span class="pl-c1">0</span>,<span class="pl-c1">1</span>],[<span class="pl-c1">0</span>,<span class="pl-c1">1</span>],<span class="pl-s">'r--'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">ylabel</span>(<span class="pl-s">'TPR'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">xlabel</span>(<span class="pl-s">'FPR'</span>)</pre></div>
<pre><code>Text(0.5, 0, 'FPR')
</code></pre>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/9b838d2ba8dc4c3ea8dd66859499c78a12d7b4e2/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f323032303039313330313032323639352e706e67"><img src="https://camo.githubusercontent.com/9b838d2ba8dc4c3ea8dd66859499c78a12d7b4e2/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f323032303039313330313032323639352e706e67" alt="roc.png" data-canonical-src="https://img-blog.csdnimg.cn/2020091301022695.png" style="max-width:100%;"></a></p>
<div class="highlight highlight-source-python"><pre><span class="pl-c">## AUC</span>
<span class="pl-k">import</span> <span class="pl-s1">numpy</span> <span class="pl-k">as</span> <span class="pl-s1">np</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">metrics</span> <span class="pl-k">import</span> <span class="pl-s1">roc_auc_score</span>
<span class="pl-s1">y_true</span> <span class="pl-c1">=</span> <span class="pl-s1">np</span>.<span class="pl-en">array</span>([<span class="pl-c1">0</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>])
<span class="pl-s1">y_scores</span> <span class="pl-c1">=</span> <span class="pl-s1">np</span>.<span class="pl-en">array</span>([<span class="pl-c1">0.1</span>, <span class="pl-c1">0.4</span>, <span class="pl-c1">0.35</span>, <span class="pl-c1">0.8</span>])
<span class="pl-en">print</span>(<span class="pl-s">'AUC socre:'</span>,<span class="pl-en">roc_auc_score</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_scores</span>))</pre></div>
<pre><code>AUC socre: 0.75
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-c">## KS值 在实际操作时往往使用ROC曲线配合求出KS值</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">metrics</span> <span class="pl-k">import</span> <span class="pl-s1">roc_curve</span>
<span class="pl-s1">y_pred</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>]
<span class="pl-s1">y_true</span> <span class="pl-c1">=</span> [<span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">0</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>]
<span class="pl-v">FPR</span>,<span class="pl-v">TPR</span>,<span class="pl-s1">thresholds</span><span class="pl-c1">=</span><span class="pl-en">roc_curve</span>(<span class="pl-s1">y_true</span>, <span class="pl-s1">y_pred</span>)
<span class="pl-v">KS</span><span class="pl-c1">=</span><span class="pl-en">abs</span>(<span class="pl-v">FPR</span><span class="pl-c1">-</span><span class="pl-v">TPR</span>).<span class="pl-en">max</span>()
<span class="pl-en">print</span>(<span class="pl-s">'KS值：'</span>,<span class="pl-v">KS</span>)</pre></div>
<pre><code>KS值： 0.5238095238095237
</code></pre>

</article>
  </div>

    </div>


  </body>
</html>

