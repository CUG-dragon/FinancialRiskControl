




<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
       
  <div id="readme" class="Box-body readme blob js-code-block-container p-5 p-xl-6 gist-border-0">
    <article class="markdown-body entry-content container-lg" itemprop="text"><h2><a id="user-content-task5-模型融合" class="anchor" aria-hidden="true" href="#task5-模型融合"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Task5 模型融合</h2>

<h3><a id="user-content-51-学习目标" class="anchor" aria-hidden="true" href="#51-学习目标"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.1 学习目标</h3>
<p>将之前建模调参的结果进行模型融合。
尝试多种融合方案，提交融合结果并打卡。（模型融合一般用于A榜比赛的尾声和B榜比赛的全程）</p>
<h3><a id="user-content-52-内容介绍" class="anchor" aria-hidden="true" href="#52-内容介绍"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.2 内容介绍</h3>
<p>模型融合是比赛后期上分的重要手段，特别是多人组队学习的比赛中，将不同队友的模型进行融合，可能会收获意想不到的效果哦，往往模型相差越大且模型表现都不错的前提下，模型融合后结果会有大幅提升，以下是模型融合的方式。</p>
<ul>
<li>平均：
<ul>
<li>简单平均法</li>
<li>加权平均法</li>
</ul>
</li>
<li>投票：
<ul>
<li>简单投票法</li>
<li>加权投票法</li>
</ul>
</li>
<li>综合：
<ul>
<li>排序融合</li>
<li>log融合</li>
</ul>
</li>
<li>stacking:
<ul>
<li>构建多层模型，并利用预测结果再拟合预测。</li>
</ul>
</li>
<li>blending：
<ul>
<li>选取部分数据预测训练得到预测结果作为新特征，带入剩下的数据中预测。</li>
</ul>
</li>
<li>boosting/bagging（在Task4中已经提及，就不再赘述）</li>
</ul>
<h3><a id="user-content-53-stackingblending详解" class="anchor" aria-hidden="true" href="#53-stackingblending详解"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.3 stacking\blending详解</h3>
<ul>
<li>stacking
将若干基学习器获得的预测结果，将预测结果作为新的训练集来训练一个学习器。如下图 假设有五个基学习器，将数据带入五基学习器中得到预测结果，再带入模型六中进行训练预测。但是由于直接由五个基学习器获得结果直接带入模型六中，容易导致过拟合。所以在使用五个及模型进行预测的时候，可以考虑使用K折验证，防止过拟合。</li>
</ul>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/8208e1d00c405d9ca57dbd557a6a580e4d9781df/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f323032303039313330313234303235362e706e67"><img src="https://camo.githubusercontent.com/8208e1d00c405d9ca57dbd557a6a580e4d9781df/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f323032303039313330313234303235362e706e67" alt="stacking.png" data-canonical-src="https://img-blog.csdnimg.cn/2020091301240256.png" style="max-width:100%;"></a></p>
<ul>
<li>blending
与stacking不同，blending是将预测的值作为新的特征和原特征合并，构成新的特征值，用于预测。为了防止过拟合，将数据分为两部分d1、d2，使用d1的数据作为训练集，d2数据作为测试集。预测得到的数据作为新特征使用d2的数据作为训练集结合新特征，预测测试集结果。</li>
</ul>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/a8ef2ee92fe0a5dc3b00dee61b6559f25f085f6b/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031323430313935382e706e67"><img src="https://camo.githubusercontent.com/a8ef2ee92fe0a5dc3b00dee61b6559f25f085f6b/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031323430313935382e706e67" alt="blending.png" data-canonical-src="https://img-blog.csdnimg.cn/20200913012401958.png" style="max-width:100%;"></a></p>
<ul>
<li>Blending与stacking的不同
<ul>
<li>stacking
<ul>
<li>stacking中由于两层使用的数据不同，所以可以避免信息泄露的问题。</li>
<li>在组队竞赛的过程中，不需要给队友分享自己的随机种子。</li>
</ul>
</li>
<li>Blending
<ul>
<li>由于blending对将数据划分为两个部分，在最后预测时有部分数据信息将被忽略。</li>
<li>同时在使用第二层数据时可能会因为第二层数据较少产生过拟合现象。</li>
</ul>
</li>
</ul>
</li>
</ul>
<p>参考资料：还是没有理解透彻吗？可以查看参考资料进一步了解哦!
<a href="https://blog.csdn.net/wuzhongqiang/article/details/105012739" rel="nofollow">https://blog.csdn.net/wuzhongqiang/article/details/105012739</a></p>
<h3><a id="user-content-54-代码示例" class="anchor" aria-hidden="true" href="#54-代码示例"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.4 代码示例</h3>
<h3><a id="user-content-541-平均" class="anchor" aria-hidden="true" href="#541-平均"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.4.1 平均：</h3>
<ul>
<li>简单加权平均，结果直接融合
求多个预测结果的平均值。pre1-pren分别是n组模型预测出来的结果，将其进行加权融</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">pre</span> <span class="pl-c1">=</span> (<span class="pl-s1">pre1</span> <span class="pl-c1">+</span> <span class="pl-s1">pre2</span> <span class="pl-c1">+</span> <span class="pl-s1">pre3</span> <span class="pl-c1">+</span>...<span class="pl-c1">+</span><span class="pl-s1">pren</span> )<span class="pl-c1">/</span><span class="pl-s1">n</span></pre></div>
<ul>
<li>加权平均法
一般根据之前预测模型的准确率，进行加权融合，将准确性高的模型赋予更高的权重。</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-s1">pre</span> <span class="pl-c1">=</span> <span class="pl-c1">0.3</span><span class="pl-s1">pre1</span> <span class="pl-c1">+</span> <span class="pl-c1">0.3</span><span class="pl-s1">pre2</span> <span class="pl-c1">+</span> <span class="pl-c1">0.4</span><span class="pl-s1">pre3</span> </pre></div>
<h3><a id="user-content-542-投票" class="anchor" aria-hidden="true" href="#542-投票"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.4.2 投票</h3>
<ul>
<li>简单投票</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">xgboost</span> <span class="pl-k">import</span> <span class="pl-v">XGBClassifier</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">linear_model</span> <span class="pl-k">import</span> <span class="pl-v">LogisticRegression</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">ensemble</span> <span class="pl-k">import</span> <span class="pl-v">RandomForestClassifier</span>, <span class="pl-v">VotingClassifier</span>
<span class="pl-s1">clf1</span> <span class="pl-c1">=</span> <span class="pl-v">LogisticRegression</span>(<span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-s1">clf2</span> <span class="pl-c1">=</span> <span class="pl-v">RandomForestClassifier</span>(<span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-s1">clf3</span> <span class="pl-c1">=</span> <span class="pl-v">XGBClassifier</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">150</span>, <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-c1">4</span>, <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-c1">2</span>, <span class="pl-s1">subsample</span><span class="pl-c1">=</span><span class="pl-c1">0.7</span>,<span class="pl-s1">objective</span><span class="pl-c1">=</span><span class="pl-s">'binary:logistic'</span>)
 
<span class="pl-s1">vclf</span> <span class="pl-c1">=</span> <span class="pl-v">VotingClassifier</span>(<span class="pl-s1">estimators</span><span class="pl-c1">=</span>[(<span class="pl-s">'lr'</span>, <span class="pl-s1">clf1</span>), (<span class="pl-s">'rf'</span>, <span class="pl-s1">clf2</span>), (<span class="pl-s">'xgb'</span>, <span class="pl-s1">clf3</span>)])
<span class="pl-s1">vclf</span> <span class="pl-c1">=</span> <span class="pl-s1">vclf</span> .<span class="pl-en">fit</span>(<span class="pl-s1">x_train</span>,<span class="pl-s1">y_train</span>)
<span class="pl-en">print</span>(<span class="pl-s1">vclf</span> .<span class="pl-en">predict</span>(<span class="pl-s1">x_test</span>))</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-c1">-</span> 加权投票
在<span class="pl-v">VotingClassifier</span>中加入参数 <span class="pl-s1">voting</span><span class="pl-c1">=</span><span class="pl-s">'soft'</span>, <span class="pl-s1">weights</span><span class="pl-c1">=</span>[<span class="pl-c1">2</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>]，<span class="pl-s1">weights</span>用于调节基模型的权重</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">xgboost</span> <span class="pl-k">import</span> <span class="pl-v">XGBClassifier</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">linear_model</span> <span class="pl-k">import</span> <span class="pl-v">LogisticRegression</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">ensemble</span> <span class="pl-k">import</span> <span class="pl-v">RandomForestClassifier</span>, <span class="pl-v">VotingClassifier</span>
<span class="pl-s1">clf1</span> <span class="pl-c1">=</span> <span class="pl-v">LogisticRegression</span>(<span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-s1">clf2</span> <span class="pl-c1">=</span> <span class="pl-v">RandomForestClassifier</span>(<span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-s1">clf3</span> <span class="pl-c1">=</span> <span class="pl-v">XGBClassifier</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">150</span>, <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-c1">4</span>, <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-c1">2</span>, <span class="pl-s1">subsample</span><span class="pl-c1">=</span><span class="pl-c1">0.7</span>,<span class="pl-s1">objective</span><span class="pl-c1">=</span><span class="pl-s">'binary:logistic'</span>)
 
<span class="pl-s1">vclf</span> <span class="pl-c1">=</span> <span class="pl-v">VotingClassifier</span>(<span class="pl-s1">estimators</span><span class="pl-c1">=</span>[(<span class="pl-s">'lr'</span>, <span class="pl-s1">clf1</span>), (<span class="pl-s">'rf'</span>, <span class="pl-s1">clf2</span>), (<span class="pl-s">'xgb'</span>, <span class="pl-s1">clf3</span>)], <span class="pl-s1">voting</span><span class="pl-c1">=</span><span class="pl-s">'soft'</span>, <span class="pl-s1">weights</span><span class="pl-c1">=</span>[<span class="pl-c1">2</span>, <span class="pl-c1">1</span>, <span class="pl-c1">1</span>])
<span class="pl-s1">vclf</span> <span class="pl-c1">=</span> <span class="pl-s1">vclf</span> .<span class="pl-en">fit</span>(<span class="pl-s1">x_train</span>,<span class="pl-s1">y_train</span>)
<span class="pl-en">print</span>(<span class="pl-s1">vclf</span> .<span class="pl-en">predict</span>(<span class="pl-s1">x_test</span>))</pre></div>
<h3><a id="user-content-543-stacking" class="anchor" aria-hidden="true" href="#543-stacking"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.4.3 Stacking：</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-k">import</span> <span class="pl-s1">warnings</span>
<span class="pl-s1">warnings</span>.<span class="pl-en">filterwarnings</span>(<span class="pl-s">'ignore'</span>)
<span class="pl-k">import</span> <span class="pl-s1">itertools</span>
<span class="pl-k">import</span> <span class="pl-s1">numpy</span> <span class="pl-k">as</span> <span class="pl-s1">np</span>
<span class="pl-k">import</span> <span class="pl-s1">seaborn</span> <span class="pl-k">as</span> <span class="pl-s1">sns</span>
<span class="pl-k">import</span> <span class="pl-s1">matplotlib</span>.<span class="pl-s1">pyplot</span> <span class="pl-k">as</span> <span class="pl-s1">plt</span>
<span class="pl-k">import</span> <span class="pl-s1">matplotlib</span>.<span class="pl-s1">gridspec</span> <span class="pl-k">as</span> <span class="pl-s1">gridspec</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span> <span class="pl-k">import</span> <span class="pl-s1">datasets</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">linear_model</span> <span class="pl-k">import</span> <span class="pl-v">LogisticRegression</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">neighbors</span> <span class="pl-k">import</span> <span class="pl-v">KNeighborsClassifier</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">naive_bayes</span> <span class="pl-k">import</span> <span class="pl-v">GaussianNB</span> 
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">ensemble</span> <span class="pl-k">import</span> <span class="pl-v">RandomForestClassifier</span>
<span class="pl-k">from</span> <span class="pl-s1">mlxtend</span>.<span class="pl-s1">classifier</span> <span class="pl-k">import</span> <span class="pl-v">StackingClassifier</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">model_selection</span> <span class="pl-k">import</span> <span class="pl-s1">cross_val_score</span>, <span class="pl-s1">train_test_split</span>
<span class="pl-k">from</span> <span class="pl-s1">mlxtend</span>.<span class="pl-s1">plotting</span> <span class="pl-k">import</span> <span class="pl-s1">plot_learning_curves</span>
<span class="pl-k">from</span> <span class="pl-s1">mlxtend</span>.<span class="pl-s1">plotting</span> <span class="pl-k">import</span> <span class="pl-s1">plot_decision_regions</span>


<span class="pl-c"># 以python自带的鸢尾花数据集为例</span>
<span class="pl-s1">iris</span> <span class="pl-c1">=</span> <span class="pl-s1">datasets</span>.<span class="pl-en">load_iris</span>()
<span class="pl-v">X</span>, <span class="pl-s1">y</span> <span class="pl-c1">=</span> <span class="pl-s1">iris</span>.<span class="pl-s1">data</span>[:, <span class="pl-c1">1</span>:<span class="pl-c1">3</span>], <span class="pl-s1">iris</span>.<span class="pl-s1">target</span>


<span class="pl-s1">clf1</span> <span class="pl-c1">=</span> <span class="pl-v">KNeighborsClassifier</span>(<span class="pl-s1">n_neighbors</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-s1">clf2</span> <span class="pl-c1">=</span> <span class="pl-v">RandomForestClassifier</span>(<span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-s1">clf3</span> <span class="pl-c1">=</span> <span class="pl-v">GaussianNB</span>()
<span class="pl-s1">lr</span> <span class="pl-c1">=</span> <span class="pl-v">LogisticRegression</span>()
<span class="pl-s1">sclf</span> <span class="pl-c1">=</span> <span class="pl-v">StackingClassifier</span>(<span class="pl-s1">classifiers</span><span class="pl-c1">=</span>[<span class="pl-s1">clf1</span>, <span class="pl-s1">clf2</span>, <span class="pl-s1">clf3</span>], 
                          <span class="pl-s1">meta_classifier</span><span class="pl-c1">=</span><span class="pl-s1">lr</span>)


<span class="pl-s1">label</span> <span class="pl-c1">=</span> [<span class="pl-s">'KNN'</span>, <span class="pl-s">'Random Forest'</span>, <span class="pl-s">'Naive Bayes'</span>, <span class="pl-s">'Stacking Classifier'</span>]
<span class="pl-s1">clf_list</span> <span class="pl-c1">=</span> [<span class="pl-s1">clf1</span>, <span class="pl-s1">clf2</span>, <span class="pl-s1">clf3</span>, <span class="pl-s1">sclf</span>]
    
<span class="pl-s1">fig</span> <span class="pl-c1">=</span> <span class="pl-s1">plt</span>.<span class="pl-en">figure</span>(<span class="pl-s1">figsize</span><span class="pl-c1">=</span>(<span class="pl-c1">10</span>,<span class="pl-c1">8</span>))
<span class="pl-s1">gs</span> <span class="pl-c1">=</span> <span class="pl-s1">gridspec</span>.<span class="pl-v">GridSpec</span>(<span class="pl-c1">2</span>, <span class="pl-c1">2</span>)
<span class="pl-s1">grid</span> <span class="pl-c1">=</span> <span class="pl-s1">itertools</span>.<span class="pl-en">product</span>([<span class="pl-c1">0</span>,<span class="pl-c1">1</span>],<span class="pl-s1">repeat</span><span class="pl-c1">=</span><span class="pl-c1">2</span>)


<span class="pl-s1">clf_cv_mean</span> <span class="pl-c1">=</span> []
<span class="pl-s1">clf_cv_std</span> <span class="pl-c1">=</span> []
<span class="pl-k">for</span> <span class="pl-s1">clf</span>, <span class="pl-s1">label</span>, <span class="pl-s1">grd</span> <span class="pl-c1">in</span> <span class="pl-en">zip</span>(<span class="pl-s1">clf_list</span>, <span class="pl-s1">label</span>, <span class="pl-s1">grid</span>):
        
    <span class="pl-s1">scores</span> <span class="pl-c1">=</span> <span class="pl-en">cross_val_score</span>(<span class="pl-s1">clf</span>, <span class="pl-v">X</span>, <span class="pl-s1">y</span>, <span class="pl-s1">cv</span><span class="pl-c1">=</span><span class="pl-c1">5</span>, <span class="pl-s1">scoring</span><span class="pl-c1">=</span><span class="pl-s">'accuracy'</span>)
    <span class="pl-en">print</span>(<span class="pl-s">"Accuracy: %.2f (+/- %.2f) [%s]"</span> <span class="pl-c1">%</span>(<span class="pl-s1">scores</span>.<span class="pl-en">mean</span>(), <span class="pl-s1">scores</span>.<span class="pl-en">std</span>(), <span class="pl-s1">label</span>))
    <span class="pl-s1">clf_cv_mean</span>.<span class="pl-en">append</span>(<span class="pl-s1">scores</span>.<span class="pl-en">mean</span>())
    <span class="pl-s1">clf_cv_std</span>.<span class="pl-en">append</span>(<span class="pl-s1">scores</span>.<span class="pl-en">std</span>())
        
    <span class="pl-s1">clf</span>.<span class="pl-en">fit</span>(<span class="pl-v">X</span>, <span class="pl-s1">y</span>)
    <span class="pl-s1">ax</span> <span class="pl-c1">=</span> <span class="pl-s1">plt</span>.<span class="pl-en">subplot</span>(<span class="pl-s1">gs</span>[<span class="pl-s1">grd</span>[<span class="pl-c1">0</span>], <span class="pl-s1">grd</span>[<span class="pl-c1">1</span>]])
    <span class="pl-s1">fig</span> <span class="pl-c1">=</span> <span class="pl-en">plot_decision_regions</span>(<span class="pl-v">X</span><span class="pl-c1">=</span><span class="pl-v">X</span>, <span class="pl-s1">y</span><span class="pl-c1">=</span><span class="pl-s1">y</span>, <span class="pl-s1">clf</span><span class="pl-c1">=</span><span class="pl-s1">clf</span>)
    <span class="pl-s1">plt</span>.<span class="pl-en">title</span>(<span class="pl-s1">label</span>)
 

<span class="pl-s1">plt</span>.<span class="pl-en">show</span>()</pre></div>
<pre><code>Accuracy: 0.91 (+/- 0.07) [KNN]
Accuracy: 0.94 (+/- 0.04) [Random Forest]
Accuracy: 0.91 (+/- 0.04) [Naive Bayes]
Accuracy: 0.94 (+/- 0.04) [Stacking Classifier]
</code></pre>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/e532c7cda6ec5d826dacd65fb4e04793ccf9159c/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031323430313839382e706e67"><img src="https://camo.githubusercontent.com/e532c7cda6ec5d826dacd65fb4e04793ccf9159c/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303931333031323430313839382e706e67" alt="png" data-canonical-src="https://img-blog.csdnimg.cn/20200913012401898.png" style="max-width:100%;"></a></p>
<h3><a id="user-content-542-blending" class="anchor" aria-hidden="true" href="#542-blending"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.4.2 blending</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 以python自带的鸢尾花数据集为例</span>
<span class="pl-s1">data_0</span> <span class="pl-c1">=</span> <span class="pl-s1">iris</span>.<span class="pl-s1">data</span>
<span class="pl-s1">data</span> <span class="pl-c1">=</span> <span class="pl-s1">data_0</span>[:<span class="pl-c1">100</span>,:]


<span class="pl-s1">target_0</span> <span class="pl-c1">=</span> <span class="pl-s1">iris</span>.<span class="pl-s1">target</span>
<span class="pl-s1">target</span> <span class="pl-c1">=</span> <span class="pl-s1">target_0</span>[:<span class="pl-c1">100</span>]
 
<span class="pl-c">#模型融合中基学习器</span>
<span class="pl-s1">clfs</span> <span class="pl-c1">=</span> [<span class="pl-v">LogisticRegression</span>(),
        <span class="pl-v">RandomForestClassifier</span>(),
        <span class="pl-v">ExtraTreesClassifier</span>(),
        <span class="pl-v">GradientBoostingClassifier</span>()]
 
<span class="pl-c">#切分一部分数据作为测试集</span>
<span class="pl-v">X</span>, <span class="pl-v">X_predict</span>, <span class="pl-s1">y</span>, <span class="pl-s1">y_predict</span> <span class="pl-c1">=</span> <span class="pl-en">train_test_split</span>(<span class="pl-s1">data</span>, <span class="pl-s1">target</span>, <span class="pl-s1">test_size</span><span class="pl-c1">=</span><span class="pl-c1">0.3</span>, <span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-c1">914</span>)


<span class="pl-c">#切分训练数据集为d1,d2两部分</span>
<span class="pl-v">X_d1</span>, <span class="pl-v">X_d2</span>, <span class="pl-s1">y_d1</span>, <span class="pl-s1">y_d2</span> <span class="pl-c1">=</span> <span class="pl-en">train_test_split</span>(<span class="pl-v">X</span>, <span class="pl-s1">y</span>, <span class="pl-s1">test_size</span><span class="pl-c1">=</span><span class="pl-c1">0.5</span>, <span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-c1">914</span>)
<span class="pl-s1">dataset_d1</span> <span class="pl-c1">=</span> <span class="pl-s1">np</span>.<span class="pl-en">zeros</span>((<span class="pl-v">X_d2</span>.<span class="pl-s1">shape</span>[<span class="pl-c1">0</span>], <span class="pl-en">len</span>(<span class="pl-s1">clfs</span>)))
<span class="pl-s1">dataset_d2</span> <span class="pl-c1">=</span> <span class="pl-s1">np</span>.<span class="pl-en">zeros</span>((<span class="pl-v">X_predict</span>.<span class="pl-s1">shape</span>[<span class="pl-c1">0</span>], <span class="pl-en">len</span>(<span class="pl-s1">clfs</span>)))
 
<span class="pl-k">for</span> <span class="pl-s1">j</span>, <span class="pl-s1">clf</span> <span class="pl-c1">in</span> <span class="pl-en">enumerate</span>(<span class="pl-s1">clfs</span>):
    <span class="pl-c">#依次训练各个单模型</span>
    <span class="pl-s1">clf</span>.<span class="pl-en">fit</span>(<span class="pl-v">X_d1</span>, <span class="pl-s1">y_d1</span>)
    <span class="pl-s1">y_submission</span> <span class="pl-c1">=</span> <span class="pl-s1">clf</span>.<span class="pl-en">predict_proba</span>(<span class="pl-v">X_d2</span>)[:, <span class="pl-c1">1</span>]
    <span class="pl-s1">dataset_d1</span>[:, <span class="pl-s1">j</span>] <span class="pl-c1">=</span> <span class="pl-s1">y_submission</span>
    <span class="pl-c">#对于测试集，直接用这k个模型的预测值作为新的特征。</span>
    <span class="pl-s1">dataset_d2</span>[:, <span class="pl-s1">j</span>] <span class="pl-c1">=</span> <span class="pl-s1">clf</span>.<span class="pl-en">predict_proba</span>(<span class="pl-v">X_predict</span>)[:, <span class="pl-c1">1</span>]
    <span class="pl-en">print</span>(<span class="pl-s">"val auc Score: %f"</span> <span class="pl-c1">%</span> <span class="pl-en">roc_auc_score</span>(<span class="pl-s1">y_predict</span>, <span class="pl-s1">dataset_d2</span>[:, <span class="pl-s1">j</span>]))


<span class="pl-c">#融合使用的模型</span>
<span class="pl-s1">clf</span> <span class="pl-c1">=</span> <span class="pl-v">GradientBoostingClassifier</span>()
<span class="pl-s1">clf</span>.<span class="pl-en">fit</span>(<span class="pl-s1">dataset_d1</span>, <span class="pl-s1">y_d2</span>)
<span class="pl-s1">y_submission</span> <span class="pl-c1">=</span> <span class="pl-s1">clf</span>.<span class="pl-en">predict_proba</span>(<span class="pl-s1">dataset_d2</span>)[:, <span class="pl-c1">1</span>]
<span class="pl-en">print</span>(<span class="pl-s">"Val auc Score of Blending: %f"</span> <span class="pl-c1">%</span> (<span class="pl-en">roc_auc_score</span>(<span class="pl-s1">y_predict</span>, <span class="pl-s1">y_submission</span>)))</pre></div>
<h3><a id="user-content-55-经验总结" class="anchor" aria-hidden="true" href="#55-经验总结"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>5.5 经验总结</h3>
<ul>
<li>简单平均和加权平均是常用的两种比赛中模型融合的方式。其优点是快速、简单。</li>
<li>stacking在众多比赛中大杀四方，但是跑过代码的小伙伴想必能感受到速度之慢，同时stacking多层提升幅度并不能抵消其带来的时间和内存消耗，所以实际环境中应用还是有一定的难度，同时在有答辩环节的比赛中，主办方也会一定程度上考虑模型的复杂程度，所以说并不是模型融合的层数越多越好的。</li>
<li>当然在比赛中将加权平均、stacking、blending等混用也是一种策略，可能会收获意想不到的效果哦！</li>
</ul>

<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/c577d6834b171d50c9e10fb8db72b94720bf32ab/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f323032303039313330313032323639382e706e67237069635f63656e746572"><img src="https://camo.githubusercontent.com/c577d6834b171d50c9e10fb8db72b94720bf32ab/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f323032303039313330313032323639382e706e67237069635f63656e746572" alt="logo.png" data-canonical-src="https://img-blog.csdnimg.cn/2020091301022698.png#pic_center" style="max-width:100%;"></a></p>
</article>
 

  </body>
</html>

