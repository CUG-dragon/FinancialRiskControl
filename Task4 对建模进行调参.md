




<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">



      
  <div id="readme" class="Box-body readme blob js-code-block-container p-5 p-xl-6 gist-border-0">
    <article class="markdown-body entry-content container-lg" itemprop="text"><h1><a id="user-content-task4-建模与调参" class="anchor" aria-hidden="true" href="#task4-建模与调参"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>Task4 建模与调参</h1>

<ul>
<li>学习在金融分控领域常用的机器学习模型</li>
<li>学习机器学习模型的建模过程与调参流程</li>
</ul>

<h2><a id="user-content-42-内容介绍" class="anchor" aria-hidden="true" href="#42-内容介绍"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.2 内容介绍</h2>
<ul>
<li>
<p>逻辑回归模型：</p>
<ul>
<li>理解逻辑回归模型；</li>
<li>逻辑回归模型的应用；</li>
<li>逻辑回归的优缺点；</li>
</ul>
</li>
<li>
<p>树模型：</p>
<ul>
<li>理解树模型；</li>
<li>树模型的应用；</li>
<li>树模型的优缺点；</li>
</ul>
</li>
<li>
<p>集成模型</p>
<ul>
<li>基于bagging思想的集成模型
<ul>
<li>随机森林模型</li>
</ul>
</li>
<li>基于boosting思想的集成模型
<ul>
<li>XGBoost模型</li>
<li>LightGBM模型</li>
<li>CatBoost模型</li>
</ul>
</li>
</ul>
</li>
<li>
<p>模型对比与性能评估：</p>
<ul>
<li>回归模型/树模型/集成模型；</li>
<li>模型评估方法；</li>
<li>模型评价结果；</li>
</ul>
</li>
<li>
<p>模型调参：</p>
<ul>
<li>
<p>贪心调参方法；</p>
</li>
<li>
<p>网格调参方法；</p>
</li>
<li>
<p>贝叶斯调参方法；</p>
</li>
</ul>
</li>
</ul>
<h2><a id="user-content-43-模型相关原理介绍" class="anchor" aria-hidden="true" href="#43-模型相关原理介绍"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3 模型相关原理介绍</h2>
<p>由于相关算法原理篇幅较长，本文推荐了一些博客与教材供初学者们进行学习。</p>
<h3><a id="user-content-431-逻辑回归模型" class="anchor" aria-hidden="true" href="#431-逻辑回归模型"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3.1 逻辑回归模型</h3>
<p><a href="https://blog.csdn.net/han_xiaoyang/article/details/49123419" rel="nofollow">https://blog.csdn.net/han_xiaoyang/article/details/49123419</a></p>
<h3><a id="user-content-432-决策树模型" class="anchor" aria-hidden="true" href="#432-决策树模型"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3.2 决策树模型</h3>
<p><a href="https://blog.csdn.net/c406495762/article/details/76262487" rel="nofollow">https://blog.csdn.net/c406495762/article/details/76262487</a></p>
<h3><a id="user-content-433-gbdt模型" class="anchor" aria-hidden="true" href="#433-gbdt模型"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3.3 GBDT模型</h3>
<p><a href="https://zhuanlan.zhihu.com/p/45145899" rel="nofollow">https://zhuanlan.zhihu.com/p/45145899</a></p>
<h3><a id="user-content-434-xgboost模型" class="anchor" aria-hidden="true" href="#434-xgboost模型"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3.4 XGBoost模型</h3>
<p><a href="https://blog.csdn.net/wuzhongqiang/article/details/104854890" rel="nofollow">https://blog.csdn.net/wuzhongqiang/article/details/104854890</a></p>
<h3><a id="user-content-435-lightgbm模型" class="anchor" aria-hidden="true" href="#435-lightgbm模型"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3.5 LightGBM模型</h3>
<p><a href="https://blog.csdn.net/wuzhongqiang/article/details/105350579" rel="nofollow">https://blog.csdn.net/wuzhongqiang/article/details/105350579</a></p>
<h3><a id="user-content-436-catboost模型" class="anchor" aria-hidden="true" href="#436-catboost模型"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3.6 Catboost模型</h3>
<p><a href="https://mp.weixin.qq.com/s/xloTLr5NJBgBspMQtxPoFA" rel="nofollow">https://mp.weixin.qq.com/s/xloTLr5NJBgBspMQtxPoFA</a></p>
<h3><a id="user-content-437-时间序列模型选学" class="anchor" aria-hidden="true" href="#437-时间序列模型选学"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3.7 时间序列模型(选学)</h3>
<p>RNN：<a href="https://zhuanlan.zhihu.com/p/45289691" rel="nofollow">https://zhuanlan.zhihu.com/p/45289691</a></p>
<p>LSTM：<a href="https://zhuanlan.zhihu.com/p/83496936" rel="nofollow">https://zhuanlan.zhihu.com/p/83496936</a></p>
<h3><a id="user-content-438-推荐教材" class="anchor" aria-hidden="true" href="#438-推荐教材"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.3.8 推荐教材：</h3>
<p>《机器学习》 <a href="https://book.douban.com/subject/26708119/" rel="nofollow">https://book.douban.com/subject/26708119/</a></p>
<p>《统计学习方法》 <a href="https://book.douban.com/subject/10590856/" rel="nofollow">https://book.douban.com/subject/10590856/</a></p>
<p>《面向机器学习的特征工程》 <a href="https://book.douban.com/subject/26826639/" rel="nofollow">https://book.douban.com/subject/26826639/</a></p>
<p>《信用评分模型技术与应用》<a href="https://book.douban.com/subject/1488075/" rel="nofollow">https://book.douban.com/subject/1488075/</a></p>
<p>《数据化风控》<a href="https://book.douban.com/subject/30282558/" rel="nofollow">https://book.douban.com/subject/30282558/</a></p>
<h2><a id="user-content-44-模型对比与性能评估" class="anchor" aria-hidden="true" href="#44-模型对比与性能评估"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.4 模型对比与性能评估</h2>
<h3><a id="user-content-441-逻辑回归" class="anchor" aria-hidden="true" href="#441-逻辑回归"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.4.1 逻辑回归</h3>
<ul>
<li>
<p>优点</p>
<ul>
<li>训练速度较快，分类的时候，计算量仅仅只和特征的数目相关；</li>
<li>简单易理解，模型的可解释性非常好，从特征的权重可以看到不同的特征对最后结果的影响；</li>
<li>适合二分类问题，不需要缩放输入特征；</li>
<li>内存资源占用小，只需要存储各个维度的特征值；</li>
</ul>
</li>
<li>
<p>缺点</p>
<ul>
<li>
<p><strong>逻辑回归需要预先处理缺失值和异常值【可参考task3特征工程】；</strong></p>
</li>
<li>
<p>不能用Logistic回归去解决非线性问题，因为Logistic的决策面是线性的；</p>
</li>
<li>
<p>对多重共线性数据较为敏感，且很难处理数据不平衡的问题；</p>
</li>
<li>
<p>准确率并不是很高，因为形式非常简单，很难去拟合数据的真实分布；</p>
</li>
</ul>
</li>
</ul>
<h3><a id="user-content-442-决策树模型" class="anchor" aria-hidden="true" href="#442-决策树模型"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.4.2 决策树模型</h3>
<ul>
<li>优点
<ul>
<li>简单直观，生成的决策树可以可视化展示</li>
<li><strong>数据不需要预处理，不需要归一化，不需要处理缺失数据</strong></li>
<li>既可以处理离散值，也可以处理连续值</li>
</ul>
</li>
<li>缺点
<ul>
<li>决策树算法非常容易过拟合，导致泛化能力不强（可进行适当的剪枝）</li>
<li>采用的是贪心算法，容易得到局部最优解</li>
</ul>
</li>
</ul>
<h3><a id="user-content-443-集成模型集成方法ensemble-method" class="anchor" aria-hidden="true" href="#443-集成模型集成方法ensemble-method"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.4.3 集成模型集成方法（ensemble method）</h3>
<p>通过组合多个学习器来完成学习任务，通过集成方法，可以将多个弱学习器组合成一个强分类器，因此集成学习的泛化能力一般比单一分类器要好。</p>
<p>集成方法主要包括Bagging和Boosting，Bagging和Boosting都是将已有的分类或回归算法通过一定方式组合起来，形成一个更加强大的分类。两种方法都是把若干个分类器整合为一个分类器的方法，只是整合的方式不一样，最终得到不一样的效果。常见的基于Baggin思想的集成模型有：随机森林、基于Boosting思想的集成模型有：Adaboost、GBDT、XgBoost、LightGBM等。</p>
<p><strong>Baggin和Boosting的区别总结如下：</strong></p>
<ul>
<li><strong>样本选择上：</strong> Bagging方法的训练集是从原始集中有放回的选取，所以从原始集中选出的各轮训练集之间是独立的；而Boosting方法需要每一轮的训练集不变，只是训练集中每个样本在分类器中的权重发生变化。而权值是根据上一轮的分类结果进行调整</li>
<li><strong>样例权重上：</strong> Bagging方法使用均匀取样，所以每个样本的权重相等；而Boosting方法根据错误率不断调整样本的权值，错误率越大则权重越大</li>
<li><strong>预测函数上：</strong> Bagging方法中所有预测函数的权重相等；而Boosting方法中每个弱分类器都有相应的权重，对于分类误差小的分类器会有更大的权重</li>
<li><strong>并行计算上：</strong> Bagging方法中各个预测函数可以并行生成；而Boosting方法各个预测函数只能顺序生成，因为后一个模型参数需要前一轮模型的结果。</li>
</ul>
<h3><a id="user-content-444-模型评估方法" class="anchor" aria-hidden="true" href="#444-模型评估方法"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.4.4 模型评估方法</h3>
<p>对于模型来说，其在训练集上面的误差我们称之为<strong>训练误差</strong>或者<strong>经验误差</strong>，而在测试集上的误差称之为<strong>测试误差</strong>。</p>
<p>对于我们来说，我们更关心的是模型对于新样本的学习能力，即我们希望通过对已有样本的学习，尽可能的将所有潜在样本的普遍规律学到手，而如果模型对训练样本学的太好，则有可能把训练样本自身所具有的一些特点当做所有潜在样本的普遍特点，这时候我们就会出现<strong>过拟合</strong>的问题。</p>
<p>因此我们通常将已有的数据集划分为训练集和测试集两部分，其中训练集用来训练模型，而测试集则是用来评估模型对于新样本的判别能力。</p>
<p><strong>对于数据集的划分，我们通常要保证满足以下两个条件：</strong></p>
<ul>
<li>训练集和测试集的分布要与样本真实分布一致，即训练集和测试集都要保证是从样本真实分布中独立同分布采样而得；</li>
<li>训练集和测试集要互斥</li>
</ul>
<p><strong>对于数据集的划分有三种方法：留出法，交叉验证法和自助法，下面挨个介绍：</strong></p>
<ul>
<li>
<p><strong>①留出法</strong></p>
<p>留出法是直接将数据集D划分为两个互斥的集合，其中一个集合作为训练集S，另一个作为测试集T。需要注意的是在划分的时候要尽可能保证数据分布的一致性，即避免因数据划分过程引入额外的偏差而对最终结果产生影响。为了保证数据分布的一致性，通常我们采用<strong>分层采样</strong>的方式来对数据进行采样。</p>
<p><strong>Tips：</strong> 通常，会将数据集D中大约2/3~4/5的样本作为训练集，其余的作为测试集。</p>
</li>
<li>
<p><strong>②交叉验证法</strong></p>
<p><strong>k折交叉验证</strong>通常将数据集D分为k份，其中k-1份作为训练集，剩余的一份作为测试集，这样就可以获得k组训练/测试集，可以进行k次训练与测试，最终返回的是k个测试结果的均值。交叉验证中数据集的划分依然是依据<strong>分层采样</strong>的方式来进行。</p>
<p>对于交叉验证法，其k值的选取往往决定了评估结果的稳定性和保真性，<strong>通常k值选取10。</strong></p>
<p>当k=1的时候，我们称之为<strong>留一法</strong></p>
</li>
<li>
<p><strong>③自助法</strong></p>
<p>我们每次从数据集D中取一个样本作为训练集中的元素，然后把该样本放回，重复该行为m次，这样我们就可以得到大小为m的训练集，在这里面有的样本重复出现，有的样本则没有出现过，我们把那些没有出现过的样本作为测试集。</p>
<p>进行这样采样的原因是因为在D中约有36.8%的数据没有在训练集中出现过。留出法与交叉验证法都是使用<strong>分层采样</strong>的方式进行数据采样与划分，而自助法则是使用<strong>有放回重复采样</strong>的方式进行数据采样</p>
</li>
</ul>
<p><strong>数据集划分总结</strong></p>
<ul>
<li>对于数据量充足的时候，通常采用<strong>留出法</strong>或者<strong>k折交叉验证法</strong>来进行训练/测试集的划分；</li>
<li>对于数据集小且难以有效划分训练/测试集时使用<strong>自助法</strong>；</li>
<li>对于数据集小且可有效划分的时候最好使用<strong>留一法</strong>来进行划分，因为这种方法最为准确</li>
</ul>
<h3><a id="user-content-445-模型评价标准" class="anchor" aria-hidden="true" href="#445-模型评价标准"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.4.5 模型评价标准</h3>
<p>对于本次比赛，我们选用auc作为模型评价标准，类似的评价标准还有ks、f1-score等，具体介绍与实现大家可以回顾下task1中的内容。</p>
<p><strong>一起来看一下auc到底是什么？</strong></p>
<p>在逻辑回归里面，对于正负例的界定，通常会设一个阈值，大于阈值的为正类，小于阈值为负类。如果我们减小这个阀值，更多的样本会被识别为正类，提高正类的识别率，但同时也会使得更多的负类被错误识别为正类。为了直观表示这一现象，引入ROC。</p>
<p>根据分类结果计算得到ROC空间中相应的点，连接这些点就形成ROC curve，横坐标为False Positive Rate(FPR：假正率)，纵坐标为True Positive Rate(TPR：真正率)。 一般情况下，这个曲线都应该处于(0,0)和(1,1)连线的上方,如图：</p>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/fb25a48f0c1defcbda2977b063a5d23a28e3fc4c/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303930353039343930333732342e706e67"><img src="https://camo.githubusercontent.com/fb25a48f0c1defcbda2977b063a5d23a28e3fc4c/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303930353039343930333732342e706e67" alt="ROC&amp;AUC.png" data-canonical-src="https://img-blog.csdnimg.cn/20200905094903724.png" style="max-width:100%;"></a></p>
<p>ROC曲线中的四个点：</p>
<ul>
<li>点(0,1)：即FPR=0, TPR=1，意味着FN＝0且FP＝0，将所有的样本都正确分类；</li>
<li>点(1,0)：即FPR=1，TPR=0，最差分类器，避开了所有正确答案；</li>
<li>点(0,0)：即FPR=TPR=0，FP＝TP＝0，分类器把每个实例都预测为负类；</li>
<li>点(1,1)：分类器把每个实例都预测为正类</li>
</ul>
<p>总之：ROC曲线越接近左上角，该分类器的性能越好，其泛化性能就越好。而且一般来说，如果ROC是光滑的，那么基本可以判断没有太大的overfitting。</p>
<p><strong>但是对于两个模型，我们如何判断哪个模型的泛化性能更优呢？这里我们有主要以下两种方法：</strong></p>
<p>如果模型A的ROC曲线完全包住了模型B的ROC曲线，那么我们就认为模型A要优于模型B；</p>
<p>如果两条曲线有交叉的话，我们就通过比较ROC与X，Y轴所围得曲线的面积来判断，面积越大，模型的性能就越优，<strong>这个面积我们称之为AUC(area under ROC curve)</strong></p>
<h2><a id="user-content-45-代码示例" class="anchor" aria-hidden="true" href="#45-代码示例"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.5 代码示例</h2>
<h3><a id="user-content-451-导入相关关和相关设置" class="anchor" aria-hidden="true" href="#451-导入相关关和相关设置"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.5.1 导入相关关和相关设置</h3>
<div class="highlight highlight-source-python"><pre><span class="pl-k">import</span> <span class="pl-s1">pandas</span> <span class="pl-k">as</span> <span class="pl-s1">pd</span>
<span class="pl-k">import</span> <span class="pl-s1">numpy</span> <span class="pl-k">as</span> <span class="pl-s1">np</span>
<span class="pl-k">import</span> <span class="pl-s1">warnings</span>
<span class="pl-k">import</span> <span class="pl-s1">os</span>
<span class="pl-k">import</span> <span class="pl-s1">seaborn</span> <span class="pl-k">as</span> <span class="pl-s1">sns</span>
<span class="pl-k">import</span> <span class="pl-s1">matplotlib</span>.<span class="pl-s1">pyplot</span> <span class="pl-k">as</span> <span class="pl-s1">plt</span>
<span class="pl-s">"""</span>
<span class="pl-s">sns 相关设置</span>
<span class="pl-s">@return:</span>
<span class="pl-s">"""</span>
<span class="pl-c"># 声明使用 Seaborn 样式</span>
<span class="pl-s1">sns</span>.<span class="pl-en">set</span>()
<span class="pl-c"># 有五种seaborn的绘图风格，它们分别是：darkgrid, whitegrid, dark, white, ticks。默认的主题是darkgrid。</span>
<span class="pl-s1">sns</span>.<span class="pl-en">set_style</span>(<span class="pl-s">"whitegrid"</span>)
<span class="pl-c"># 有四个预置的环境，按大小从小到大排列分别为：paper, notebook, talk, poster。其中，notebook是默认的。</span>
<span class="pl-s1">sns</span>.<span class="pl-en">set_context</span>(<span class="pl-s">'talk'</span>)
<span class="pl-c"># 中文字体设置-黑体</span>
<span class="pl-s1">plt</span>.<span class="pl-s1">rcParams</span>[<span class="pl-s">'font.sans-serif'</span>] <span class="pl-c1">=</span> [<span class="pl-s">'SimHei'</span>]
<span class="pl-c"># 解决保存图像是负号'-'显示为方块的问题</span>
<span class="pl-s1">plt</span>.<span class="pl-s1">rcParams</span>[<span class="pl-s">'axes.unicode_minus'</span>] <span class="pl-c1">=</span> <span class="pl-c1">False</span>
<span class="pl-c"># 解决Seaborn中文显示问题并调整字体大小</span>
<span class="pl-s1">sns</span>.<span class="pl-en">set</span>(<span class="pl-s1">font</span><span class="pl-c1">=</span><span class="pl-s">'SimHei'</span>)</pre></div>
<h3><a id="user-content-452-读取数据" class="anchor" aria-hidden="true" href="#452-读取数据"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.5.2 读取数据</h3>
<p>reduce_mem_usage 函数通过调整数据类型，帮助我们减少数据在内存中占用的空间</p>
<div class="highlight highlight-source-python"><pre><span class="pl-k">def</span> <span class="pl-en">reduce_mem_usage</span>(<span class="pl-s1">df</span>):
    <span class="pl-s1">start_mem</span> <span class="pl-c1">=</span> <span class="pl-s1">df</span>.<span class="pl-en">memory_usage</span>().<span class="pl-en">sum</span>() 
    <span class="pl-en">print</span>(<span class="pl-s">'Memory usage of dataframe is {:.2f} MB'</span>.<span class="pl-en">format</span>(<span class="pl-s1">start_mem</span>))
    
    <span class="pl-k">for</span> <span class="pl-s1">col</span> <span class="pl-c1">in</span> <span class="pl-s1">df</span>.<span class="pl-s1">columns</span>:
        <span class="pl-s1">col_type</span> <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-s1">dtype</span>
        
        <span class="pl-k">if</span> <span class="pl-s1">col_type</span> <span class="pl-c1">!=</span> <span class="pl-s1">object</span>:
            <span class="pl-s1">c_min</span> <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">min</span>()
            <span class="pl-s1">c_max</span> <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">max</span>()
            <span class="pl-k">if</span> <span class="pl-en">str</span>(<span class="pl-s1">col_type</span>)[:<span class="pl-c1">3</span>] <span class="pl-c1">==</span> <span class="pl-s">'int'</span>:
                <span class="pl-k">if</span> <span class="pl-s1">c_min</span> <span class="pl-c1">&gt;</span> <span class="pl-s1">np</span>.<span class="pl-en">iinfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int8</span>).<span class="pl-s1">min</span> <span class="pl-c1">and</span> <span class="pl-s1">c_max</span> <span class="pl-c1">&lt;</span> <span class="pl-s1">np</span>.<span class="pl-en">iinfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int8</span>).<span class="pl-s1">max</span>:
                    <span class="pl-s1">df</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int8</span>)
                <span class="pl-k">elif</span> <span class="pl-s1">c_min</span> <span class="pl-c1">&gt;</span> <span class="pl-s1">np</span>.<span class="pl-en">iinfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int16</span>).<span class="pl-s1">min</span> <span class="pl-c1">and</span> <span class="pl-s1">c_max</span> <span class="pl-c1">&lt;</span> <span class="pl-s1">np</span>.<span class="pl-en">iinfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int16</span>).<span class="pl-s1">max</span>:
                    <span class="pl-s1">df</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int16</span>)
                <span class="pl-k">elif</span> <span class="pl-s1">c_min</span> <span class="pl-c1">&gt;</span> <span class="pl-s1">np</span>.<span class="pl-en">iinfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int32</span>).<span class="pl-s1">min</span> <span class="pl-c1">and</span> <span class="pl-s1">c_max</span> <span class="pl-c1">&lt;</span> <span class="pl-s1">np</span>.<span class="pl-en">iinfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int32</span>).<span class="pl-s1">max</span>:
                    <span class="pl-s1">df</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int32</span>)
                <span class="pl-k">elif</span> <span class="pl-s1">c_min</span> <span class="pl-c1">&gt;</span> <span class="pl-s1">np</span>.<span class="pl-en">iinfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int64</span>).<span class="pl-s1">min</span> <span class="pl-c1">and</span> <span class="pl-s1">c_max</span> <span class="pl-c1">&lt;</span> <span class="pl-s1">np</span>.<span class="pl-en">iinfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int64</span>).<span class="pl-s1">max</span>:
                    <span class="pl-s1">df</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">np</span>.<span class="pl-s1">int64</span>)  
            <span class="pl-k">else</span>:
                <span class="pl-k">if</span> <span class="pl-s1">c_min</span> <span class="pl-c1">&gt;</span> <span class="pl-s1">np</span>.<span class="pl-en">finfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">float16</span>).<span class="pl-s1">min</span> <span class="pl-c1">and</span> <span class="pl-s1">c_max</span> <span class="pl-c1">&lt;</span> <span class="pl-s1">np</span>.<span class="pl-en">finfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">float16</span>).<span class="pl-s1">max</span>:
                    <span class="pl-s1">df</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">np</span>.<span class="pl-s1">float16</span>)
                <span class="pl-k">elif</span> <span class="pl-s1">c_min</span> <span class="pl-c1">&gt;</span> <span class="pl-s1">np</span>.<span class="pl-en">finfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">float32</span>).<span class="pl-s1">min</span> <span class="pl-c1">and</span> <span class="pl-s1">c_max</span> <span class="pl-c1">&lt;</span> <span class="pl-s1">np</span>.<span class="pl-en">finfo</span>(<span class="pl-s1">np</span>.<span class="pl-s1">float32</span>).<span class="pl-s1">max</span>:
                    <span class="pl-s1">df</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">np</span>.<span class="pl-s1">float32</span>)
                <span class="pl-k">else</span>:
                    <span class="pl-s1">df</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s1">np</span>.<span class="pl-s1">float64</span>)
        <span class="pl-k">else</span>:
            <span class="pl-s1">df</span>[<span class="pl-s1">col</span>] <span class="pl-c1">=</span> <span class="pl-s1">df</span>[<span class="pl-s1">col</span>].<span class="pl-en">astype</span>(<span class="pl-s">'category'</span>)

    <span class="pl-s1">end_mem</span> <span class="pl-c1">=</span> <span class="pl-s1">df</span>.<span class="pl-en">memory_usage</span>().<span class="pl-en">sum</span>() 
    <span class="pl-en">print</span>(<span class="pl-s">'Memory usage after optimization is: {:.2f} MB'</span>.<span class="pl-en">format</span>(<span class="pl-s1">end_mem</span>))
    <span class="pl-en">print</span>(<span class="pl-s">'Decreased by {:.1f}%'</span>.<span class="pl-en">format</span>(<span class="pl-c1">100</span> <span class="pl-c1">*</span> (<span class="pl-s1">start_mem</span> <span class="pl-c1">-</span> <span class="pl-s1">end_mem</span>) <span class="pl-c1">/</span> <span class="pl-s1">start_mem</span>))
    
    <span class="pl-k">return</span> <span class="pl-s1">df</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-c"># 读取数据</span>
<span class="pl-s1">data</span> <span class="pl-c1">=</span> <span class="pl-s1">pd</span>.<span class="pl-en">read_csv</span>(<span class="pl-s">'dataset/data_for_model.csv'</span>)
<span class="pl-s1">data</span> <span class="pl-c1">=</span> <span class="pl-en">reduce_mem_usage</span>(<span class="pl-s1">data</span>)</pre></div>
<pre><code>Memory usage of dataframe is 928000128.00 MB
Memory usage after optimization is: 165006456.00 MB
Decreased by 82.2%
</code></pre>
<h3><a id="user-content-453-简单建模" class="anchor" aria-hidden="true" href="#453-简单建模"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.5.3 简单建模</h3>
<blockquote>
<p>Tips1：金融风控的实际项目多涉及到信用评分，因此需要模型特征具有较好的可解释性，所以目前在实际项目中多还是以逻辑回归作为基础模型。但是在比赛中以得分高低为准，不需要严谨的可解释性，所以大多基于集成算法进行建模。</p>
<p>Tips2：因为逻辑回归的算法特性，需要提前对异常值、缺失值数据进行处理【参考task3部分】</p>
<p>Tips3：基于树模型的算法特性，异常值、缺失值处理可以跳过，但是对于业务较为了解的同学也可以自己对缺失异常值进行处理，效果可能会更优于模型处理的结果。</p>
<p>注：以下建模的源数据参考baseline进行了相应的特征工程，对于异常缺失值未进行相应的处理操作。</p>
</blockquote>
<p>建模之前的预操作</p>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">model_selection</span> <span class="pl-k">import</span> <span class="pl-v">KFold</span>
<span class="pl-c"># 分离数据集，方便进行交叉验证</span>
<span class="pl-v">X_train</span> <span class="pl-c1">=</span> <span class="pl-s1">data</span>.<span class="pl-s1">loc</span>[<span class="pl-s1">data</span>[<span class="pl-s">'sample'</span>]<span class="pl-c1">==</span><span class="pl-s">'train'</span>, :].<span class="pl-en">drop</span>([<span class="pl-s">'id'</span>,<span class="pl-s">'issueDate'</span>,<span class="pl-s">'isDefault'</span>, <span class="pl-s">'sample'</span>], <span class="pl-s1">axis</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-v">X_test</span> <span class="pl-c1">=</span> <span class="pl-s1">data</span>.<span class="pl-s1">loc</span>[<span class="pl-s1">data</span>[<span class="pl-s">'sample'</span>]<span class="pl-c1">==</span><span class="pl-s">'test'</span>, :].<span class="pl-en">drop</span>([<span class="pl-s">'id'</span>,<span class="pl-s">'issueDate'</span>,<span class="pl-s">'isDefault'</span>, <span class="pl-s">'sample'</span>], <span class="pl-s1">axis</span><span class="pl-c1">=</span><span class="pl-c1">1</span>)
<span class="pl-s1">y_train</span> <span class="pl-c1">=</span> <span class="pl-s1">data</span>.<span class="pl-s1">loc</span>[<span class="pl-s1">data</span>[<span class="pl-s">'sample'</span>]<span class="pl-c1">==</span><span class="pl-s">'train'</span>, <span class="pl-s">'isDefault'</span>]

<span class="pl-c"># 5折交叉验证</span>
<span class="pl-s1">folds</span> <span class="pl-c1">=</span> <span class="pl-c1">5</span>
<span class="pl-s1">seed</span> <span class="pl-c1">=</span> <span class="pl-c1">2020</span>
<span class="pl-s1">kf</span> <span class="pl-c1">=</span> <span class="pl-v">KFold</span>(<span class="pl-s1">n_splits</span><span class="pl-c1">=</span><span class="pl-s1">folds</span>, <span class="pl-s1">shuffle</span><span class="pl-c1">=</span><span class="pl-c1">True</span>, <span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-s1">seed</span>)</pre></div>
<p>使用Lightgbm进行建模</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s">"""对训练集数据进行划分，分成训练集和验证集，并进行相应的操作"""</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">model_selection</span> <span class="pl-k">import</span> <span class="pl-s1">train_test_split</span>
<span class="pl-k">import</span> <span class="pl-s1">lightgbm</span> <span class="pl-k">as</span> <span class="pl-s1">lgb</span>
<span class="pl-c"># 数据集划分</span>
<span class="pl-v">X_train_split</span>, <span class="pl-v">X_val</span>, <span class="pl-s1">y_train_split</span>, <span class="pl-s1">y_val</span> <span class="pl-c1">=</span> <span class="pl-en">train_test_split</span>(<span class="pl-v">X_train</span>, <span class="pl-s1">y_train</span>, <span class="pl-s1">test_size</span><span class="pl-c1">=</span><span class="pl-c1">0.2</span>)
<span class="pl-s1">train_matrix</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-v">Dataset</span>(<span class="pl-v">X_train_split</span>, <span class="pl-s1">label</span><span class="pl-c1">=</span><span class="pl-s1">y_train_split</span>)
<span class="pl-s1">valid_matrix</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-v">Dataset</span>(<span class="pl-v">X_val</span>, <span class="pl-s1">label</span><span class="pl-c1">=</span><span class="pl-s1">y_val</span>)

<span class="pl-s1">params</span> <span class="pl-c1">=</span> {
            <span class="pl-s">'boosting_type'</span>: <span class="pl-s">'gbdt'</span>,
            <span class="pl-s">'objective'</span>: <span class="pl-s">'binary'</span>,
            <span class="pl-s">'learning_rate'</span>: <span class="pl-c1">0.1</span>,
            <span class="pl-s">'metric'</span>: <span class="pl-s">'auc'</span>,
            <span class="pl-s">'min_child_weight'</span>: <span class="pl-c1">1e-3</span>,
            <span class="pl-s">'num_leaves'</span>: <span class="pl-c1">31</span>,
            <span class="pl-s">'max_depth'</span>: <span class="pl-c1">-</span><span class="pl-c1">1</span>,
            <span class="pl-s">'reg_lambda'</span>: <span class="pl-c1">0</span>,
            <span class="pl-s">'reg_alpha'</span>: <span class="pl-c1">0</span>,
            <span class="pl-s">'feature_fraction'</span>: <span class="pl-c1">1</span>,
            <span class="pl-s">'bagging_fraction'</span>: <span class="pl-c1">1</span>,
            <span class="pl-s">'bagging_freq'</span>: <span class="pl-c1">0</span>,
            <span class="pl-s">'seed'</span>: <span class="pl-c1">2020</span>,
            <span class="pl-s">'nthread'</span>: <span class="pl-c1">8</span>,
            <span class="pl-s">'silent'</span>: <span class="pl-c1">True</span>,
            <span class="pl-s">'verbose'</span>: <span class="pl-c1">-</span><span class="pl-c1">1</span>,
}

<span class="pl-s">"""使用训练集数据进行模型训练"""</span>
<span class="pl-s1">model</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-en">train</span>(<span class="pl-s1">params</span>, <span class="pl-s1">train_set</span><span class="pl-c1">=</span><span class="pl-s1">train_matrix</span>, <span class="pl-s1">valid_sets</span><span class="pl-c1">=</span><span class="pl-s1">valid_matrix</span>, <span class="pl-s1">num_boost_round</span><span class="pl-c1">=</span><span class="pl-c1">20000</span>, <span class="pl-s1">verbose_eval</span><span class="pl-c1">=</span><span class="pl-c1">1000</span>, <span class="pl-s1">early_stopping_rounds</span><span class="pl-c1">=</span><span class="pl-c1">200</span>)</pre></div>
<pre><code>Training until validation scores don't improve for 200 rounds
Early stopping, best iteration is:
[427]	valid_0's auc: 0.724947
</code></pre>
<p>对验证集进行预测</p>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span> <span class="pl-k">import</span> <span class="pl-s1">metrics</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">metrics</span> <span class="pl-k">import</span> <span class="pl-s1">roc_auc_score</span>

<span class="pl-s">"""预测并计算roc的相关指标"""</span>
<span class="pl-s1">val_pre_lgb</span> <span class="pl-c1">=</span> <span class="pl-s1">model</span>.<span class="pl-en">predict</span>(<span class="pl-v">X_val</span>, <span class="pl-s1">num_iteration</span><span class="pl-c1">=</span><span class="pl-s1">model</span>.<span class="pl-s1">best_iteration</span>)
<span class="pl-s1">fpr</span>, <span class="pl-s1">tpr</span>, <span class="pl-s1">threshold</span> <span class="pl-c1">=</span> <span class="pl-s1">metrics</span>.<span class="pl-en">roc_curve</span>(<span class="pl-s1">y_val</span>, <span class="pl-s1">val_pre_lgb</span>)
<span class="pl-s1">roc_auc</span> <span class="pl-c1">=</span> <span class="pl-s1">metrics</span>.<span class="pl-en">auc</span>(<span class="pl-s1">fpr</span>, <span class="pl-s1">tpr</span>)
<span class="pl-en">print</span>(<span class="pl-s">'未调参前lightgbm单模型在验证集上的AUC：{}'</span>.<span class="pl-en">format</span>(<span class="pl-s1">roc_auc</span>))
<span class="pl-s">"""画出roc曲线图"""</span>
<span class="pl-s1">plt</span>.<span class="pl-en">figure</span>(<span class="pl-s1">figsize</span><span class="pl-c1">=</span>(<span class="pl-c1">8</span>, <span class="pl-c1">8</span>))
<span class="pl-s1">plt</span>.<span class="pl-en">title</span>(<span class="pl-s">'Validation ROC'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">plot</span>(<span class="pl-s1">fpr</span>, <span class="pl-s1">tpr</span>, <span class="pl-s">'b'</span>, <span class="pl-s1">label</span> <span class="pl-c1">=</span> <span class="pl-s">'Val AUC = %0.4f'</span> <span class="pl-c1">%</span> <span class="pl-s1">roc_auc</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">ylim</span>(<span class="pl-c1">0</span>,<span class="pl-c1">1</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">xlim</span>(<span class="pl-c1">0</span>,<span class="pl-c1">1</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">legend</span>(<span class="pl-s1">loc</span><span class="pl-c1">=</span><span class="pl-s">'best'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">title</span>(<span class="pl-s">'ROC'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">ylabel</span>(<span class="pl-s">'True Positive Rate'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">xlabel</span>(<span class="pl-s">'False Positive Rate'</span>)
<span class="pl-c"># 画出对角线</span>
<span class="pl-s1">plt</span>.<span class="pl-en">plot</span>([<span class="pl-c1">0</span>,<span class="pl-c1">1</span>],[<span class="pl-c1">0</span>,<span class="pl-c1">1</span>],<span class="pl-s">'r--'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">show</span>()</pre></div>
<pre><code>未调参前lightgbm单模型在验证集上的AUC：0.7249469360631181
</code></pre>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/a7f868966e9695796cb49c0854917fce0be25a76/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303930353039343432303634392e706e67"><img src="https://camo.githubusercontent.com/a7f868966e9695796cb49c0854917fce0be25a76/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303930353039343432303634392e706e67" alt="output_10_1.png" data-canonical-src="https://img-blog.csdnimg.cn/20200905094420649.png" style="max-width:100%;"></a></p>
<p>更进一步的，使用5折交叉验证进行模型性能评估</p>
<div class="highlight highlight-source-python"><pre><span class="pl-k">import</span> <span class="pl-s1">lightgbm</span> <span class="pl-k">as</span> <span class="pl-s1">lgb</span>
<span class="pl-s">"""使用lightgbm 5折交叉验证进行建模预测"""</span>
<span class="pl-s1">cv_scores</span> <span class="pl-c1">=</span> []
<span class="pl-k">for</span> <span class="pl-s1">i</span>, (<span class="pl-s1">train_index</span>, <span class="pl-s1">valid_index</span>) <span class="pl-c1">in</span> <span class="pl-en">enumerate</span>(<span class="pl-s1">kf</span>.<span class="pl-en">split</span>(<span class="pl-v">X_train</span>, <span class="pl-s1">y_train</span>)):
    <span class="pl-en">print</span>(<span class="pl-s">'************************************ {} ************************************'</span>.<span class="pl-en">format</span>(<span class="pl-en">str</span>(<span class="pl-s1">i</span><span class="pl-c1">+</span><span class="pl-c1">1</span>)))
    <span class="pl-v">X_train_split</span>, <span class="pl-s1">y_train_split</span>, <span class="pl-v">X_val</span>, <span class="pl-s1">y_val</span> <span class="pl-c1">=</span> <span class="pl-v">X_train</span>.<span class="pl-s1">iloc</span>[<span class="pl-s1">train_index</span>], <span class="pl-s1">y_train</span>[<span class="pl-s1">train_index</span>], <span class="pl-v">X_train</span>.<span class="pl-s1">iloc</span>[<span class="pl-s1">valid_index</span>], <span class="pl-s1">y_train</span>[<span class="pl-s1">valid_index</span>]
    
    <span class="pl-s1">train_matrix</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-v">Dataset</span>(<span class="pl-v">X_train_split</span>, <span class="pl-s1">label</span><span class="pl-c1">=</span><span class="pl-s1">y_train_split</span>)
    <span class="pl-s1">valid_matrix</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-v">Dataset</span>(<span class="pl-v">X_val</span>, <span class="pl-s1">label</span><span class="pl-c1">=</span><span class="pl-s1">y_val</span>)

    <span class="pl-s1">params</span> <span class="pl-c1">=</span> {
                <span class="pl-s">'boosting_type'</span>: <span class="pl-s">'gbdt'</span>,
                <span class="pl-s">'objective'</span>: <span class="pl-s">'binary'</span>,
                <span class="pl-s">'learning_rate'</span>: <span class="pl-c1">0.1</span>,
                <span class="pl-s">'metric'</span>: <span class="pl-s">'auc'</span>,
        
                <span class="pl-s">'min_child_weight'</span>: <span class="pl-c1">1e-3</span>,
                <span class="pl-s">'num_leaves'</span>: <span class="pl-c1">31</span>,
                <span class="pl-s">'max_depth'</span>: <span class="pl-c1">-</span><span class="pl-c1">1</span>,
                <span class="pl-s">'reg_lambda'</span>: <span class="pl-c1">0</span>,
                <span class="pl-s">'reg_alpha'</span>: <span class="pl-c1">0</span>,
                <span class="pl-s">'feature_fraction'</span>: <span class="pl-c1">1</span>,
                <span class="pl-s">'bagging_fraction'</span>: <span class="pl-c1">1</span>,
                <span class="pl-s">'bagging_freq'</span>: <span class="pl-c1">0</span>,
                <span class="pl-s">'seed'</span>: <span class="pl-c1">2020</span>,
                <span class="pl-s">'nthread'</span>: <span class="pl-c1">8</span>,
                <span class="pl-s">'silent'</span>: <span class="pl-c1">True</span>,
                <span class="pl-s">'verbose'</span>: <span class="pl-c1">-</span><span class="pl-c1">1</span>,
    }
    
    <span class="pl-s1">model</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-en">train</span>(<span class="pl-s1">params</span>, <span class="pl-s1">train_set</span><span class="pl-c1">=</span><span class="pl-s1">train_matrix</span>, <span class="pl-s1">num_boost_round</span><span class="pl-c1">=</span><span class="pl-c1">20000</span>, <span class="pl-s1">valid_sets</span><span class="pl-c1">=</span><span class="pl-s1">valid_matrix</span>, <span class="pl-s1">verbose_eval</span><span class="pl-c1">=</span><span class="pl-c1">1000</span>, <span class="pl-s1">early_stopping_rounds</span><span class="pl-c1">=</span><span class="pl-c1">200</span>)
    <span class="pl-s1">val_pred</span> <span class="pl-c1">=</span> <span class="pl-s1">model</span>.<span class="pl-en">predict</span>(<span class="pl-v">X_val</span>, <span class="pl-s1">num_iteration</span><span class="pl-c1">=</span><span class="pl-s1">model</span>.<span class="pl-s1">best_iteration</span>)
    
    <span class="pl-s1">cv_scores</span>.<span class="pl-en">append</span>(<span class="pl-en">roc_auc_score</span>(<span class="pl-s1">y_val</span>, <span class="pl-s1">val_pred</span>))
    <span class="pl-en">print</span>(<span class="pl-s1">cv_scores</span>)

<span class="pl-en">print</span>(<span class="pl-s">"lgb_scotrainre_list:{}"</span>.<span class="pl-en">format</span>(<span class="pl-s1">cv_scores</span>))
<span class="pl-en">print</span>(<span class="pl-s">"lgb_score_mean:{}"</span>.<span class="pl-en">format</span>(<span class="pl-s1">np</span>.<span class="pl-en">mean</span>(<span class="pl-s1">cv_scores</span>)))
<span class="pl-en">print</span>(<span class="pl-s">"lgb_score_std:{}"</span>.<span class="pl-en">format</span>(<span class="pl-s1">np</span>.<span class="pl-en">std</span>(<span class="pl-s1">cv_scores</span>)))</pre></div>
<pre><code>...
lgb_scotrainre_list:[0.7303837315833632, 0.7258692125145638, 0.7305149209921737, 0.7296117869375041, 0.7294438695369077]
lgb_score_mean:0.7291647043129024
lgb_score_std:0.0016998349834934656
</code></pre>
<h3><a id="user-content-454-模型调参" class="anchor" aria-hidden="true" href="#454-模型调参"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.5.4 模型调参</h3>
<ul>
<li>
<p><strong>1. 贪心调参</strong></p>
<p>先使用当前对模型影响最大的参数进行调优，达到当前参数下的模型最优化，再使用对模型影响次之的参数进行调优，如此下去，直到所有的参数调整完毕。</p>
<p>这个方法的缺点就是可能会调到局部最优而不是全局最优，但是只需要一步一步的进行参数最优化调试即可，容易理解。</p>
<p>需要注意的是在树模型中参数调整的顺序，也就是各个参数对模型的影响程度，这里列举一下日常调参过程中常用的参数和调参顺序：</p>
<ul>
<li>①：max_depth、num_leaves</li>
<li>②：min_data_in_leaf、min_child_weight</li>
<li>③：bagging_fraction、 feature_fraction、bagging_freq</li>
<li>④：reg_lambda、reg_alpha</li>
<li>⑤：min_split_gain</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">model_selection</span> <span class="pl-k">import</span> <span class="pl-s1">cross_val_score</span>

<span class="pl-c"># 调objective</span>
<span class="pl-s1">best_obj</span> <span class="pl-c1">=</span> <span class="pl-en">dict</span>()
<span class="pl-k">for</span> <span class="pl-s1">obj</span> <span class="pl-c1">in</span> <span class="pl-s1">objective</span>:
    <span class="pl-s1">model</span> <span class="pl-c1">=</span> <span class="pl-v">LGBMRegressor</span>(<span class="pl-s1">objective</span><span class="pl-c1">=</span><span class="pl-s1">obj</span>)
    <span class="pl-s">"""预测并计算roc的相关指标"""</span>
    <span class="pl-s1">score</span> <span class="pl-c1">=</span> <span class="pl-en">cross_val_score</span>(<span class="pl-s1">model</span>, <span class="pl-v">X_train</span>, <span class="pl-s1">y_train</span>, <span class="pl-s1">cv</span><span class="pl-c1">=</span><span class="pl-c1">5</span>, <span class="pl-s1">scoring</span><span class="pl-c1">=</span><span class="pl-s">'roc_auc'</span>).<span class="pl-en">mean</span>()
    <span class="pl-s1">best_obj</span>[<span class="pl-s1">obj</span>] <span class="pl-c1">=</span> <span class="pl-s1">score</span>
    
<span class="pl-c"># num_leaves</span>
<span class="pl-s1">best_leaves</span> <span class="pl-c1">=</span> <span class="pl-en">dict</span>()
<span class="pl-k">for</span> <span class="pl-s1">leaves</span> <span class="pl-c1">in</span> <span class="pl-s1">num_leaves</span>:
    <span class="pl-s1">model</span> <span class="pl-c1">=</span> <span class="pl-v">LGBMRegressor</span>(<span class="pl-s1">objective</span><span class="pl-c1">=</span><span class="pl-en">min</span>(<span class="pl-s1">best_obj</span>.<span class="pl-en">items</span>(), <span class="pl-s1">key</span><span class="pl-c1">=</span><span class="pl-k">lambda</span> <span class="pl-s1">x</span>:<span class="pl-s1">x</span>[<span class="pl-c1">1</span>])[<span class="pl-c1">0</span>], <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-s1">leaves</span>)
    <span class="pl-s">"""预测并计算roc的相关指标"""</span>
    <span class="pl-s1">score</span> <span class="pl-c1">=</span> <span class="pl-en">cross_val_score</span>(<span class="pl-s1">model</span>, <span class="pl-v">X_train</span>, <span class="pl-s1">y_train</span>, <span class="pl-s1">cv</span><span class="pl-c1">=</span><span class="pl-c1">5</span>, <span class="pl-s1">scoring</span><span class="pl-c1">=</span><span class="pl-s">'roc_auc'</span>).<span class="pl-en">mean</span>()
    <span class="pl-s1">best_leaves</span>[<span class="pl-s1">leaves</span>] <span class="pl-c1">=</span> <span class="pl-s1">score</span>
    
<span class="pl-c"># max_depth</span>
<span class="pl-s1">best_depth</span> <span class="pl-c1">=</span> <span class="pl-en">dict</span>()
<span class="pl-k">for</span> <span class="pl-s1">depth</span> <span class="pl-c1">in</span> <span class="pl-s1">max_depth</span>:
    <span class="pl-s1">model</span> <span class="pl-c1">=</span> <span class="pl-v">LGBMRegressor</span>(<span class="pl-s1">objective</span><span class="pl-c1">=</span><span class="pl-en">min</span>(<span class="pl-s1">best_obj</span>.<span class="pl-en">items</span>(), <span class="pl-s1">key</span><span class="pl-c1">=</span><span class="pl-k">lambda</span> <span class="pl-s1">x</span>:<span class="pl-s1">x</span>[<span class="pl-c1">1</span>])[<span class="pl-c1">0</span>],
                          <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-en">min</span>(<span class="pl-s1">best_leaves</span>.<span class="pl-en">items</span>(), <span class="pl-s1">key</span><span class="pl-c1">=</span><span class="pl-k">lambda</span> <span class="pl-s1">x</span>:<span class="pl-s1">x</span>[<span class="pl-c1">1</span>])[<span class="pl-c1">0</span>],
                          <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-s1">depth</span>)
    <span class="pl-s">"""预测并计算roc的相关指标"""</span>
    <span class="pl-s1">score</span> <span class="pl-c1">=</span> <span class="pl-en">cross_val_score</span>(<span class="pl-s1">model</span>, <span class="pl-v">X_train</span>, <span class="pl-s1">y_train</span>, <span class="pl-s1">cv</span><span class="pl-c1">=</span><span class="pl-c1">5</span>, <span class="pl-s1">scoring</span><span class="pl-c1">=</span><span class="pl-s">'roc_auc'</span>).<span class="pl-en">mean</span>()
    <span class="pl-s1">best_depth</span>[<span class="pl-s1">depth</span>] <span class="pl-c1">=</span> <span class="pl-s1">score</span>

<span class="pl-s">"""</span>
<span class="pl-s">可依次将模型的参数通过上面的方式进行调整优化，并且通过可视化观察在每一个最优参数下模型的得分情况</span>
<span class="pl-s">"""</span></pre></div>
<p>可依次将模型的参数通过上面的方式进行调整优化，并且通过可视化观察在每一个最优参数下模型的得分情况</p>
</li>
<li>
<p><strong>2. 网格搜索</strong></p>
<p>sklearn 提供GridSearchCV用于进行网格搜索，只需要把模型的参数输进去，就能给出最优化的结果和参数。相比起贪心调参，网格搜索的结果会更优，但是网格搜索只适合于小数据集，一旦数据的量级上去了，很难得出结果。</p>
<p>同样以Lightgbm算法为例，进行网格搜索调参：</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s">"""通过网格搜索确定最优参数"""</span>
<span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">model_selection</span> <span class="pl-k">import</span> <span class="pl-v">GridSearchCV</span>

<span class="pl-k">def</span> <span class="pl-en">get_best_cv_params</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">581</span>, <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-c1">31</span>, <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-c1">-</span><span class="pl-c1">1</span>, <span class="pl-s1">bagging_fraction</span><span class="pl-c1">=</span><span class="pl-c1">1.0</span>, 
                       <span class="pl-s1">feature_fraction</span><span class="pl-c1">=</span><span class="pl-c1">1.0</span>, <span class="pl-s1">bagging_freq</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">min_data_in_leaf</span><span class="pl-c1">=</span><span class="pl-c1">20</span>, <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-c1">0.001</span>, 
                       <span class="pl-s1">min_split_gain</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_lambda</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_alpha</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">param_grid</span><span class="pl-c1">=</span><span class="pl-c1">None</span>):
    <span class="pl-c"># 设置5折交叉验证</span>
    <span class="pl-s1">cv_fold</span> <span class="pl-c1">=</span> <span class="pl-v">StratifiedKFold</span>(<span class="pl-s1">n_splits</span><span class="pl-c1">=</span><span class="pl-c1">5</span>, <span class="pl-s1">random_state</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">shuffle</span><span class="pl-c1">=</span><span class="pl-c1">True</span>, )
    
    <span class="pl-s1">model_lgb</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-v">LGBMClassifier</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-s1">learning_rate</span>,
                                   <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-s1">n_estimators</span>,
                                   <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-s1">num_leaves</span>,
                                   <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-s1">max_depth</span>,
                                   <span class="pl-s1">bagging_fraction</span><span class="pl-c1">=</span><span class="pl-s1">bagging_fraction</span>,
                                   <span class="pl-s1">feature_fraction</span><span class="pl-c1">=</span><span class="pl-s1">feature_fraction</span>,
                                   <span class="pl-s1">bagging_freq</span><span class="pl-c1">=</span><span class="pl-s1">bagging_freq</span>,
                                   <span class="pl-s1">min_data_in_leaf</span><span class="pl-c1">=</span><span class="pl-s1">min_data_in_leaf</span>,
                                   <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-s1">min_child_weight</span>,
                                   <span class="pl-s1">min_split_gain</span><span class="pl-c1">=</span><span class="pl-s1">min_split_gain</span>,
                                   <span class="pl-s1">reg_lambda</span><span class="pl-c1">=</span><span class="pl-s1">reg_lambda</span>,
                                   <span class="pl-s1">reg_alpha</span><span class="pl-c1">=</span><span class="pl-s1">reg_alpha</span>,
                                   <span class="pl-s1">n_jobs</span><span class="pl-c1">=</span> <span class="pl-c1">8</span>
                                  )
    <span class="pl-s1">grid_search</span> <span class="pl-c1">=</span> <span class="pl-v">GridSearchCV</span>(<span class="pl-s1">estimator</span><span class="pl-c1">=</span><span class="pl-s1">model_lgb</span>, 
                               <span class="pl-s1">cv</span><span class="pl-c1">=</span><span class="pl-s1">cv_fold</span>,
                               <span class="pl-s1">param_grid</span><span class="pl-c1">=</span><span class="pl-s1">param_grid</span>,
                               <span class="pl-s1">scoring</span><span class="pl-c1">=</span><span class="pl-s">'roc_auc'</span>
                              )
    <span class="pl-s1">grid_search</span>.<span class="pl-en">fit</span>(<span class="pl-v">X_train</span>, <span class="pl-s1">y_train</span>)

    <span class="pl-en">print</span>(<span class="pl-s">'模型当前最优参数为:{}'</span>.<span class="pl-en">format</span>(<span class="pl-s1">grid_search</span>.<span class="pl-s1">best_params_</span>))
    <span class="pl-en">print</span>(<span class="pl-s">'模型当前最优得分为:{}'</span>.<span class="pl-en">format</span>(<span class="pl-s1">grid_search</span>.<span class="pl-s1">best_score_</span>))</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s">"""以下代码未运行，耗时较长，请谨慎运行，且每一步的最优参数需要在下一步进行手动更新，请注意"""</span>

<span class="pl-s">"""</span>
<span class="pl-s">需要注意一下的是，除了获取上面的获取num_boost_round时候用的是原生的lightgbm（因为要用自带的cv）</span>
<span class="pl-s">下面配合GridSearchCV时必须使用sklearn接口的lightgbm。</span>
<span class="pl-s">"""</span>
<span class="pl-s">"""设置n_estimators 为581，调整num_leaves和max_depth，这里选择先粗调再细调"""</span>
<span class="pl-s1">lgb_params</span> <span class="pl-c1">=</span> {<span class="pl-s">'num_leaves'</span>: <span class="pl-en">range</span>(<span class="pl-c1">10</span>, <span class="pl-c1">80</span>, <span class="pl-c1">5</span>), <span class="pl-s">'max_depth'</span>: <span class="pl-en">range</span>(<span class="pl-c1">3</span>,<span class="pl-c1">10</span>,<span class="pl-c1">2</span>)}
<span class="pl-en">get_best_cv_params</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">581</span>, <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">min_data_in_leaf</span><span class="pl-c1">=</span><span class="pl-c1">20</span>, 
                   <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-c1">0.001</span>,<span class="pl-s1">bagging_fraction</span><span class="pl-c1">=</span><span class="pl-c1">1.0</span>, <span class="pl-s1">feature_fraction</span><span class="pl-c1">=</span><span class="pl-c1">1.0</span>, <span class="pl-s1">bagging_freq</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, 
                   <span class="pl-s1">min_split_gain</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_lambda</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_alpha</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">param_grid</span><span class="pl-c1">=</span><span class="pl-s1">lgb_params</span>)

<span class="pl-s">"""num_leaves为30，max_depth为7，进一步细调num_leaves和max_depth"""</span>
<span class="pl-s1">lgb_params</span> <span class="pl-c1">=</span> {<span class="pl-s">'num_leaves'</span>: <span class="pl-en">range</span>(<span class="pl-c1">25</span>, <span class="pl-c1">35</span>, <span class="pl-c1">1</span>), <span class="pl-s">'max_depth'</span>: <span class="pl-en">range</span>(<span class="pl-c1">5</span>,<span class="pl-c1">9</span>,<span class="pl-c1">1</span>)}
<span class="pl-en">get_best_cv_params</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">85</span>, <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">min_data_in_leaf</span><span class="pl-c1">=</span><span class="pl-c1">20</span>, 
                   <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-c1">0.001</span>,<span class="pl-s1">bagging_fraction</span><span class="pl-c1">=</span><span class="pl-c1">1.0</span>, <span class="pl-s1">feature_fraction</span><span class="pl-c1">=</span><span class="pl-c1">1.0</span>, <span class="pl-s1">bagging_freq</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, 
                   <span class="pl-s1">min_split_gain</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_lambda</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_alpha</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">param_grid</span><span class="pl-c1">=</span><span class="pl-s1">lgb_params</span>)

<span class="pl-s">"""</span>
<span class="pl-s">确定min_data_in_leaf为45，min_child_weight为0.001 ，下面进行bagging_fraction、feature_fraction和bagging_freq的调参</span>
<span class="pl-s">"""</span>
<span class="pl-s1">lgb_params</span> <span class="pl-c1">=</span> {<span class="pl-s">'bagging_fraction'</span>: [<span class="pl-s1">i</span><span class="pl-c1">/</span><span class="pl-c1">10</span> <span class="pl-k">for</span> <span class="pl-s1">i</span> <span class="pl-c1">in</span> <span class="pl-en">range</span>(<span class="pl-c1">5</span>,<span class="pl-c1">10</span>,<span class="pl-c1">1</span>)], 
              <span class="pl-s">'feature_fraction'</span>: [<span class="pl-s1">i</span><span class="pl-c1">/</span><span class="pl-c1">10</span> <span class="pl-k">for</span> <span class="pl-s1">i</span> <span class="pl-c1">in</span> <span class="pl-en">range</span>(<span class="pl-c1">5</span>,<span class="pl-c1">10</span>,<span class="pl-c1">1</span>)],
              <span class="pl-s">'bagging_freq'</span>: <span class="pl-en">range</span>(<span class="pl-c1">0</span>,<span class="pl-c1">81</span>,<span class="pl-c1">10</span>)
             }
<span class="pl-en">get_best_cv_params</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">85</span>, <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-c1">29</span>, <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-c1">7</span>, <span class="pl-s1">min_data_in_leaf</span><span class="pl-c1">=</span><span class="pl-c1">45</span>, 
                   <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-c1">0.001</span>,<span class="pl-s1">bagging_fraction</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">feature_fraction</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">bagging_freq</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, 
                   <span class="pl-s1">min_split_gain</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_lambda</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_alpha</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">param_grid</span><span class="pl-c1">=</span><span class="pl-s1">lgb_params</span>)

<span class="pl-s">"""</span>
<span class="pl-s">确定bagging_fraction为0.4、feature_fraction为0.6、bagging_freq为 ，下面进行reg_lambda、reg_alpha的调参</span>
<span class="pl-s">"""</span>
<span class="pl-s1">lgb_params</span> <span class="pl-c1">=</span> {<span class="pl-s">'reg_lambda'</span>: [<span class="pl-c1">0</span>,<span class="pl-c1">0.001</span>,<span class="pl-c1">0.01</span>,<span class="pl-c1">0.03</span>,<span class="pl-c1">0.08</span>,<span class="pl-c1">0.3</span>,<span class="pl-c1">0.5</span>], <span class="pl-s">'reg_alpha'</span>: [<span class="pl-c1">0</span>,<span class="pl-c1">0.001</span>,<span class="pl-c1">0.01</span>,<span class="pl-c1">0.03</span>,<span class="pl-c1">0.08</span>,<span class="pl-c1">0.3</span>,<span class="pl-c1">0.5</span>]}
<span class="pl-en">get_best_cv_params</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">85</span>, <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-c1">29</span>, <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-c1">7</span>, <span class="pl-s1">min_data_in_leaf</span><span class="pl-c1">=</span><span class="pl-c1">45</span>, 
                   <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-c1">0.001</span>,<span class="pl-s1">bagging_fraction</span><span class="pl-c1">=</span><span class="pl-c1">0.9</span>, <span class="pl-s1">feature_fraction</span><span class="pl-c1">=</span><span class="pl-c1">0.9</span>, <span class="pl-s1">bagging_freq</span><span class="pl-c1">=</span><span class="pl-c1">40</span>, 
                   <span class="pl-s1">min_split_gain</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_lambda</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">reg_alpha</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">param_grid</span><span class="pl-c1">=</span><span class="pl-s1">lgb_params</span>)

<span class="pl-s">"""</span>
<span class="pl-s">确定reg_lambda、reg_alpha都为0，下面进行min_split_gain的调参</span>
<span class="pl-s">"""</span>
<span class="pl-s1">lgb_params</span> <span class="pl-c1">=</span> {<span class="pl-s">'min_split_gain'</span>: [<span class="pl-s1">i</span><span class="pl-c1">/</span><span class="pl-c1">10</span> <span class="pl-k">for</span> <span class="pl-s1">i</span> <span class="pl-c1">in</span> <span class="pl-en">range</span>(<span class="pl-c1">0</span>,<span class="pl-c1">11</span>,<span class="pl-c1">1</span>)]}
<span class="pl-en">get_best_cv_params</span>(<span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">85</span>, <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-c1">29</span>, <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-c1">7</span>, <span class="pl-s1">min_data_in_leaf</span><span class="pl-c1">=</span><span class="pl-c1">45</span>, 
                   <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-c1">0.001</span>,<span class="pl-s1">bagging_fraction</span><span class="pl-c1">=</span><span class="pl-c1">0.9</span>, <span class="pl-s1">feature_fraction</span><span class="pl-c1">=</span><span class="pl-c1">0.9</span>, <span class="pl-s1">bagging_freq</span><span class="pl-c1">=</span><span class="pl-c1">40</span>, 
                   <span class="pl-s1">min_split_gain</span><span class="pl-c1">=</span><span class="pl-c1">None</span>, <span class="pl-s1">reg_lambda</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">reg_alpha</span><span class="pl-c1">=</span><span class="pl-c1">0</span>, <span class="pl-s1">param_grid</span><span class="pl-c1">=</span><span class="pl-s1">lgb_params</span>)</pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-s">"""</span>
<span class="pl-s">参数确定好了以后，我们设置一个比较小的learning_rate 0.005，来确定最终的num_boost_round</span>
<span class="pl-s">"""</span>
<span class="pl-c"># 设置5折交叉验证</span>
<span class="pl-c"># cv_fold = StratifiedKFold(n_splits=5, random_state=0, shuffle=True, )</span>
<span class="pl-s1">final_params</span> <span class="pl-c1">=</span> {
                <span class="pl-s">'boosting_type'</span>: <span class="pl-s">'gbdt'</span>,
                <span class="pl-s">'learning_rate'</span>: <span class="pl-c1">0.01</span>,
                <span class="pl-s">'num_leaves'</span>: <span class="pl-c1">29</span>,
                <span class="pl-s">'max_depth'</span>: <span class="pl-c1">7</span>,
                <span class="pl-s">'min_data_in_leaf'</span>:<span class="pl-c1">45</span>,
                <span class="pl-s">'min_child_weight'</span>:<span class="pl-c1">0.001</span>,
                <span class="pl-s">'bagging_fraction'</span>: <span class="pl-c1">0.9</span>,
                <span class="pl-s">'feature_fraction'</span>: <span class="pl-c1">0.9</span>,
                <span class="pl-s">'bagging_freq'</span>: <span class="pl-c1">40</span>,
                <span class="pl-s">'min_split_gain'</span>: <span class="pl-c1">0</span>,
                <span class="pl-s">'reg_lambda'</span>:<span class="pl-c1">0</span>,
                <span class="pl-s">'reg_alpha'</span>:<span class="pl-c1">0</span>,
                <span class="pl-s">'nthread'</span>: <span class="pl-c1">6</span>
               }

<span class="pl-s1">cv_result</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-en">cv</span>(<span class="pl-s1">train_set</span><span class="pl-c1">=</span><span class="pl-s1">lgb_train</span>,
                   <span class="pl-s1">early_stopping_rounds</span><span class="pl-c1">=</span><span class="pl-c1">20</span>,
                   <span class="pl-s1">num_boost_round</span><span class="pl-c1">=</span><span class="pl-c1">5000</span>,
                   <span class="pl-s1">nfold</span><span class="pl-c1">=</span><span class="pl-c1">5</span>,
                   <span class="pl-s1">stratified</span><span class="pl-c1">=</span><span class="pl-c1">True</span>,
                   <span class="pl-s1">shuffle</span><span class="pl-c1">=</span><span class="pl-c1">True</span>,
                   <span class="pl-s1">params</span><span class="pl-c1">=</span><span class="pl-s1">final_params</span>,
                   <span class="pl-s1">metrics</span><span class="pl-c1">=</span><span class="pl-s">'auc'</span>,
                   <span class="pl-s1">seed</span><span class="pl-c1">=</span><span class="pl-c1">0</span>,
                  )

<span class="pl-en">print</span>(<span class="pl-s">'迭代次数{}'</span>.<span class="pl-en">format</span>(<span class="pl-en">len</span>(<span class="pl-s1">cv_result</span>[<span class="pl-s">'auc-mean'</span>])))
<span class="pl-en">print</span>(<span class="pl-s">'交叉验证的AUC为{}'</span>.<span class="pl-en">format</span>(<span class="pl-en">max</span>(<span class="pl-s1">cv_result</span>[<span class="pl-s">'auc-mean'</span>])))</pre></div>
<p>在实际调整过程中，可先设置一个较大的学习率（上面的例子中0.1），通过Lgb原生的cv函数进行树个数的确定，之后再通过上面的实例代码进行参数的调整优化。</p>
<p>最后针对最优的参数设置一个较小的学习率（例如0.05），同样通过cv函数确定树的个数，确定最终的参数。</p>
<p>需要注意的是，针对大数据集，上面每一层参数的调整都需要耗费较长时间，</p>
</li>
<li>
<p><strong>贝叶斯调参</strong></p>
<p>在使用之前需要先安装包bayesian-optimization，运行如下命令即可：</p>
<pre><code>pip install bayesian-optimization
</code></pre>
<p>贝叶斯调参的主要思想是：给定优化的目标函数(广义的函数，只需指定输入和输出即可，无需知道内部结构以及数学性质)，通过不断地添加样本点来更新目标函数的后验分布(高斯过程,直到后验分布基本贴合于真实分布）。简单的说，就是考虑了上一次参数的信息，从而更好的调整当前的参数。</p>
<p>贝叶斯调参的步骤如下：</p>
<ul>
<li>定义优化函数(rf_cv）</li>
<li>建立模型</li>
<li>定义待优化的参数</li>
<li>得到优化结果，并返回要优化的分数指标</li>
</ul>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">sklearn</span>.<span class="pl-s1">model_selection</span> <span class="pl-k">import</span> <span class="pl-s1">cross_val_score</span>

<span class="pl-s">"""定义优化函数"""</span>
<span class="pl-k">def</span> <span class="pl-en">rf_cv_lgb</span>(<span class="pl-s1">num_leaves</span>, <span class="pl-s1">max_depth</span>, <span class="pl-s1">bagging_fraction</span>, <span class="pl-s1">feature_fraction</span>, <span class="pl-s1">bagging_freq</span>, <span class="pl-s1">min_data_in_leaf</span>, 
              <span class="pl-s1">min_child_weight</span>, <span class="pl-s1">min_split_gain</span>, <span class="pl-s1">reg_lambda</span>, <span class="pl-s1">reg_alpha</span>):
    <span class="pl-c"># 建立模型</span>
    <span class="pl-s1">model_lgb</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-v">LGBMClassifier</span>(<span class="pl-s1">boosting_type</span><span class="pl-c1">=</span><span class="pl-s">'gbdt'</span>, <span class="pl-s1">bjective</span><span class="pl-c1">=</span><span class="pl-s">'binary'</span>, <span class="pl-s1">metric</span><span class="pl-c1">=</span><span class="pl-s">'auc'</span>,
                                   <span class="pl-s1">learning_rate</span><span class="pl-c1">=</span><span class="pl-c1">0.1</span>, <span class="pl-s1">n_estimators</span><span class="pl-c1">=</span><span class="pl-c1">5000</span>,
                                   <span class="pl-s1">num_leaves</span><span class="pl-c1">=</span><span class="pl-en">int</span>(<span class="pl-s1">num_leaves</span>), <span class="pl-s1">max_depth</span><span class="pl-c1">=</span><span class="pl-en">int</span>(<span class="pl-s1">max_depth</span>), 
                                   <span class="pl-s1">bagging_fraction</span><span class="pl-c1">=</span><span class="pl-en">round</span>(<span class="pl-s1">bagging_fraction</span>, <span class="pl-c1">2</span>), <span class="pl-s1">feature_fraction</span><span class="pl-c1">=</span><span class="pl-en">round</span>(<span class="pl-s1">feature_fraction</span>, <span class="pl-c1">2</span>),
                                   <span class="pl-s1">bagging_freq</span><span class="pl-c1">=</span><span class="pl-en">int</span>(<span class="pl-s1">bagging_freq</span>), <span class="pl-s1">min_data_in_leaf</span><span class="pl-c1">=</span><span class="pl-en">int</span>(<span class="pl-s1">min_data_in_leaf</span>),
                                   <span class="pl-s1">min_child_weight</span><span class="pl-c1">=</span><span class="pl-s1">min_child_weight</span>, <span class="pl-s1">min_split_gain</span><span class="pl-c1">=</span><span class="pl-s1">min_split_gain</span>,
                                   <span class="pl-s1">reg_lambda</span><span class="pl-c1">=</span><span class="pl-s1">reg_lambda</span>, <span class="pl-s1">reg_alpha</span><span class="pl-c1">=</span><span class="pl-s1">reg_alpha</span>,
                                   <span class="pl-s1">n_jobs</span><span class="pl-c1">=</span> <span class="pl-c1">8</span>
                                  )
    
    <span class="pl-s1">val</span> <span class="pl-c1">=</span> <span class="pl-en">cross_val_score</span>(<span class="pl-s1">model_lgb</span>, <span class="pl-v">X_train_split</span>, <span class="pl-s1">y_train_split</span>, <span class="pl-s1">cv</span><span class="pl-c1">=</span><span class="pl-c1">5</span>, <span class="pl-s1">scoring</span><span class="pl-c1">=</span><span class="pl-s">'roc_auc'</span>).<span class="pl-en">mean</span>()
    
    <span class="pl-k">return</span> <span class="pl-s1">val</span></pre></div>
<div class="highlight highlight-source-python"><pre><span class="pl-k">from</span> <span class="pl-s1">bayes_opt</span> <span class="pl-k">import</span> <span class="pl-v">BayesianOptimization</span>
<span class="pl-s">"""定义优化参数"""</span>
<span class="pl-s1">bayes_lgb</span> <span class="pl-c1">=</span> <span class="pl-v">BayesianOptimization</span>(
    <span class="pl-s1">rf_cv_lgb</span>, 
    {
        <span class="pl-s">'num_leaves'</span>:(<span class="pl-c1">10</span>, <span class="pl-c1">200</span>),
        <span class="pl-s">'max_depth'</span>:(<span class="pl-c1">3</span>, <span class="pl-c1">20</span>),
        <span class="pl-s">'bagging_fraction'</span>:(<span class="pl-c1">0.5</span>, <span class="pl-c1">1.0</span>),
        <span class="pl-s">'feature_fraction'</span>:(<span class="pl-c1">0.5</span>, <span class="pl-c1">1.0</span>),
        <span class="pl-s">'bagging_freq'</span>:(<span class="pl-c1">0</span>, <span class="pl-c1">100</span>),
        <span class="pl-s">'min_data_in_leaf'</span>:(<span class="pl-c1">10</span>,<span class="pl-c1">100</span>),
        <span class="pl-s">'min_child_weight'</span>:(<span class="pl-c1">0</span>, <span class="pl-c1">10</span>),
        <span class="pl-s">'min_split_gain'</span>:(<span class="pl-c1">0.0</span>, <span class="pl-c1">1.0</span>),
        <span class="pl-s">'reg_alpha'</span>:(<span class="pl-c1">0.0</span>, <span class="pl-c1">10</span>),
        <span class="pl-s">'reg_lambda'</span>:(<span class="pl-c1">0.0</span>, <span class="pl-c1">10</span>),
    }
)

<span class="pl-s">"""开始优化"""</span>
<span class="pl-s1">bayes_lgb</span>.<span class="pl-en">maximize</span>(<span class="pl-s1">n_iter</span><span class="pl-c1">=</span><span class="pl-c1">10</span>)</pre></div>
<pre><code>|   iter    |  target   | baggin... | baggin... | featur... | max_depth | min_ch... | min_da... | min_sp... | num_le... | reg_alpha | reg_la... |
-------------------------------------------------------------------------------------------------------------------------------------------------
| �[0m 1       �[0m | �[0m 0.7263  �[0m | �[0m 0.7196  �[0m | �[0m 80.73   �[0m | �[0m 0.7988  �[0m | �[0m 19.17   �[0m | �[0m 5.751   �[0m | �[0m 40.71   �[0m | �[0m 0.9548  �[0m | �[0m 176.2   �[0m | �[0m 2.939   �[0m | �[0m 7.212   �[0m |
| �[95m 2       �[0m | �[95m 0.7279  �[0m | �[95m 0.8997  �[0m | �[95m 74.72   �[0m | �[95m 0.5904  �[0m | �[95m 7.259   �[0m | �[95m 6.175   �[0m | �[95m 92.03   �[0m | �[95m 0.4027  �[0m | �[95m 51.65   �[0m | �[95m 6.404   �[0m | �[95m 4.781   �[0m |
| �[0m 3       �[0m | �[0m 0.7207  �[0m | �[0m 0.5133  �[0m | �[0m 16.53   �[0m | �[0m 0.9536  �[0m | �[0m 4.974   �[0m | �[0m 2.37    �[0m | �[0m 98.08   �[0m | �[0m 0.7909  �[0m | �[0m 52.12   �[0m | �[0m 4.443   �[0m | �[0m 4.429   �[0m |
| �[0m 4       �[0m | �[0m 0.7276  �[0m | �[0m 0.6265  �[0m | �[0m 53.12   �[0m | �[0m 0.7307  �[0m | �[0m 10.67   �[0m | �[0m 1.824   �[0m | �[0m 18.98   �[0m | �[0m 0.954   �[0m | �[0m 60.47   �[0m | �[0m 6.963   �[0m | �[0m 1.999   �[0m |
| �[0m 5       �[0m | �[0m 0.6963  �[0m | �[0m 0.6509  �[0m | �[0m 11.58   �[0m | �[0m 0.5386  �[0m | �[0m 11.21   �[0m | �[0m 7.85    �[0m | �[0m 11.4    �[0m | �[0m 0.4269  �[0m | �[0m 153.0   �[0m | �[0m 0.5227  �[0m | �[0m 2.257   �[0m |
| �[0m 6       �[0m | �[0m 0.7276  �[0m | �[0m 0.6241  �[0m | �[0m 49.76   �[0m | �[0m 0.6057  �[0m | �[0m 10.34   �[0m | �[0m 1.718   �[0m | �[0m 22.43   �[0m | �[0m 0.8294  �[0m | �[0m 55.68   �[0m | �[0m 6.759   �[0m | �[0m 2.6     �[0m |
| �[95m 7       �[0m | �[95m 0.7283  �[0m | �[95m 0.9815  �[0m | �[95m 96.15   �[0m | �[95m 0.6961  �[0m | �[95m 19.45   �[0m | �[95m 1.627   �[0m | �[95m 37.7    �[0m | �[95m 0.4185  �[0m | �[95m 14.22   �[0m | �[95m 7.057   �[0m | �[95m 9.924   �[0m |
| �[0m 8       �[0m | �[0m 0.7278  �[0m | �[0m 0.7139  �[0m | �[0m 96.83   �[0m | �[0m 0.5063  �[0m | �[0m 3.941   �[0m | �[0m 1.469   �[0m | �[0m 97.28   �[0m | �[0m 0.07553 �[0m | �[0m 196.9   �[0m | �[0m 7.988   �[0m | �[0m 2.159   �[0m |
| �[0m 9       �[0m | �[0m 0.7195  �[0m | �[0m 0.5352  �[0m | �[0m 98.72   �[0m | �[0m 0.9699  �[0m | �[0m 4.445   �[0m | �[0m 1.767   �[0m | �[0m 13.91   �[0m | �[0m 0.1647  �[0m | �[0m 191.5   �[0m | �[0m 4.003   �[0m | �[0m 2.027   �[0m |
| �[0m 10      �[0m | �[0m 0.7281  �[0m | �[0m 0.7281  �[0m | �[0m 73.63   �[0m | �[0m 0.5598  �[0m | �[0m 19.29   �[0m | �[0m 0.5344  �[0m | �[0m 99.66   �[0m | �[0m 0.933   �[0m | �[0m 101.4   �[0m | �[0m 8.836   �[0m | �[0m 0.9222  �[0m |
| �[0m 11      �[0m | �[0m 0.7279  �[0m | �[0m 0.8213  �[0m | �[0m 0.05856 �[0m | �[0m 0.7626  �[0m | �[0m 17.49   �[0m | �[0m 8.447   �[0m | �[0m 10.71   �[0m | �[0m 0.3252  �[0m | �[0m 13.64   �[0m | �[0m 9.319   �[0m | �[0m 0.4747  �[0m |
| �[0m 12      �[0m | �[0m 0.7281  �[0m | �[0m 0.8372  �[0m | �[0m 95.71   �[0m | �[0m 0.9598  �[0m | �[0m 10.32   �[0m | �[0m 8.394   �[0m | �[0m 15.23   �[0m | �[0m 0.4909  �[0m | �[0m 94.48   �[0m | �[0m 9.486   �[0m | �[0m 9.044   �[0m |
| �[0m 13      �[0m | �[0m 0.6993  �[0m | �[0m 0.5183  �[0m | �[0m 99.02   �[0m | �[0m 0.542   �[0m | �[0m 15.5    �[0m | �[0m 8.35    �[0m | �[0m 38.15   �[0m | �[0m 0.4079  �[0m | �[0m 58.01   �[0m | �[0m 0.2668  �[0m | �[0m 1.652   �[0m |
| �[0m 14      �[0m | �[0m 0.7267  �[0m | �[0m 0.7933  �[0m | �[0m 4.459   �[0m | �[0m 0.79    �[0m | �[0m 7.557   �[0m | �[0m 2.43    �[0m | �[0m 27.91   �[0m | �[0m 0.8725  �[0m | �[0m 28.32   �[0m | �[0m 9.967   �[0m | �[0m 9.885   �[0m |
| �[0m 15      �[0m | �[0m 0.6979  �[0m | �[0m 0.9419  �[0m | �[0m 1.22    �[0m | �[0m 0.835   �[0m | �[0m 11.56   �[0m | �[0m 9.962   �[0m | �[0m 93.79   �[0m | �[0m 0.018   �[0m | �[0m 197.6   �[0m | �[0m 9.711   �[0m | �[0m 3.78    �[0m |
=================================================================================================================================================
</code></pre>
<div class="highlight highlight-source-python"><pre><span class="pl-s">"""显示优化结果"""</span>
<span class="pl-s1">bayes_lgb</span>.<span class="pl-s1">max</span></pre></div>
<pre><code>{'target': 0.7282530196283977,
 'params': {'bagging_fraction': 0.9815471914843896,
  'bagging_freq': 96.14757648686668,
  'feature_fraction': 0.6961281791730929,
  'max_depth': 19.45450235568963,
  'min_child_weight': 1.6266132496156782,
  'min_data_in_leaf': 37.697878831472295,
  'min_split_gain': 0.4184947943942168,
  'num_leaves': 14.221122487200399,
  'reg_alpha': 7.056502173310882,
  'reg_lambda': 9.924023764203156}}
</code></pre>
<p>参数优化完成后，我们可以根据优化后的参数建立新的模型，降低学习率并寻找最优模型迭代次数</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s">"""调整一个较小的学习率，并通过cv函数确定当前最优的迭代次数"""</span>
<span class="pl-s1">base_params_lgb</span> <span class="pl-c1">=</span> {
                    <span class="pl-s">'boosting_type'</span>: <span class="pl-s">'gbdt'</span>,
                    <span class="pl-s">'objective'</span>: <span class="pl-s">'binary'</span>,
                    <span class="pl-s">'metric'</span>: <span class="pl-s">'auc'</span>,
                    <span class="pl-s">'learning_rate'</span>: <span class="pl-c1">0.01</span>,
                    <span class="pl-s">'num_leaves'</span>: <span class="pl-c1">14</span>,
                    <span class="pl-s">'max_depth'</span>: <span class="pl-c1">19</span>,
                    <span class="pl-s">'min_data_in_leaf'</span>: <span class="pl-c1">37</span>,
                    <span class="pl-s">'min_child_weight'</span>:<span class="pl-c1">1.6</span>,
                    <span class="pl-s">'bagging_fraction'</span>: <span class="pl-c1">0.98</span>,
                    <span class="pl-s">'feature_fraction'</span>: <span class="pl-c1">0.69</span>,
                    <span class="pl-s">'bagging_freq'</span>: <span class="pl-c1">96</span>,
                    <span class="pl-s">'reg_lambda'</span>: <span class="pl-c1">9</span>,
                    <span class="pl-s">'reg_alpha'</span>: <span class="pl-c1">7</span>,
                    <span class="pl-s">'min_split_gain'</span>: <span class="pl-c1">0.4</span>,
                    <span class="pl-s">'nthread'</span>: <span class="pl-c1">8</span>,
                    <span class="pl-s">'seed'</span>: <span class="pl-c1">2020</span>,
                    <span class="pl-s">'silent'</span>: <span class="pl-c1">True</span>,
                    <span class="pl-s">'verbose'</span>: <span class="pl-c1">-</span><span class="pl-c1">1</span>,
}

<span class="pl-s1">cv_result_lgb</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-en">cv</span>(
    <span class="pl-s1">train_set</span><span class="pl-c1">=</span><span class="pl-s1">train_matrix</span>,
    <span class="pl-s1">early_stopping_rounds</span><span class="pl-c1">=</span><span class="pl-c1">1000</span>, 
    <span class="pl-s1">num_boost_round</span><span class="pl-c1">=</span><span class="pl-c1">20000</span>,
    <span class="pl-s1">nfold</span><span class="pl-c1">=</span><span class="pl-c1">5</span>,
    <span class="pl-s1">stratified</span><span class="pl-c1">=</span><span class="pl-c1">True</span>,
    <span class="pl-s1">shuffle</span><span class="pl-c1">=</span><span class="pl-c1">True</span>,
    <span class="pl-s1">params</span><span class="pl-c1">=</span><span class="pl-s1">base_params_lgb</span>,
    <span class="pl-s1">metrics</span><span class="pl-c1">=</span><span class="pl-s">'auc'</span>,
    <span class="pl-s1">seed</span><span class="pl-c1">=</span><span class="pl-c1">0</span>
)

<span class="pl-en">print</span>(<span class="pl-s">'迭代次数{}'</span>.<span class="pl-en">format</span>(<span class="pl-en">len</span>(<span class="pl-s1">cv_result_lgb</span>[<span class="pl-s">'auc-mean'</span>])))
<span class="pl-en">print</span>(<span class="pl-s">'最终模型的AUC为{}'</span>.<span class="pl-en">format</span>(<span class="pl-en">max</span>(<span class="pl-s1">cv_result_lgb</span>[<span class="pl-s">'auc-mean'</span>])))</pre></div>
<pre><code>迭代次数14269
最终模型的AUC为0.7315032037635779
</code></pre>
<p><strong>模型参数已经确定，建立最终模型并对验证集进行验证</strong></p>
<div class="highlight highlight-source-python"><pre><span class="pl-k">import</span> <span class="pl-s1">lightgbm</span> <span class="pl-k">as</span> <span class="pl-s1">lgb</span>
<span class="pl-s">"""使用lightgbm 5折交叉验证进行建模预测"""</span>
<span class="pl-s1">cv_scores</span> <span class="pl-c1">=</span> []
<span class="pl-k">for</span> <span class="pl-s1">i</span>, (<span class="pl-s1">train_index</span>, <span class="pl-s1">valid_index</span>) <span class="pl-c1">in</span> <span class="pl-en">enumerate</span>(<span class="pl-s1">kf</span>.<span class="pl-en">split</span>(<span class="pl-v">X_train</span>, <span class="pl-s1">y_train</span>)):
    <span class="pl-en">print</span>(<span class="pl-s">'************************************ {} ************************************'</span>.<span class="pl-en">format</span>(<span class="pl-en">str</span>(<span class="pl-s1">i</span><span class="pl-c1">+</span><span class="pl-c1">1</span>)))
    <span class="pl-v">X_train_split</span>, <span class="pl-s1">y_train_split</span>, <span class="pl-v">X_val</span>, <span class="pl-s1">y_val</span> <span class="pl-c1">=</span> <span class="pl-v">X_train</span>.<span class="pl-s1">iloc</span>[<span class="pl-s1">train_index</span>], <span class="pl-s1">y_train</span>[<span class="pl-s1">train_index</span>], <span class="pl-v">X_train</span>.<span class="pl-s1">iloc</span>[<span class="pl-s1">valid_index</span>], <span class="pl-s1">y_train</span>[<span class="pl-s1">valid_index</span>]
    
    <span class="pl-s1">train_matrix</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-v">Dataset</span>(<span class="pl-v">X_train_split</span>, <span class="pl-s1">label</span><span class="pl-c1">=</span><span class="pl-s1">y_train_split</span>)
    <span class="pl-s1">valid_matrix</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-v">Dataset</span>(<span class="pl-v">X_val</span>, <span class="pl-s1">label</span><span class="pl-c1">=</span><span class="pl-s1">y_val</span>)

    <span class="pl-s1">params</span> <span class="pl-c1">=</span> {
                <span class="pl-s">'boosting_type'</span>: <span class="pl-s">'gbdt'</span>,
                <span class="pl-s">'objective'</span>: <span class="pl-s">'binary'</span>,
                <span class="pl-s">'metric'</span>: <span class="pl-s">'auc'</span>,
                <span class="pl-s">'learning_rate'</span>: <span class="pl-c1">0.01</span>,
                <span class="pl-s">'num_leaves'</span>: <span class="pl-c1">14</span>,
                <span class="pl-s">'max_depth'</span>: <span class="pl-c1">19</span>,
                <span class="pl-s">'min_data_in_leaf'</span>: <span class="pl-c1">37</span>,
                <span class="pl-s">'min_child_weight'</span>:<span class="pl-c1">1.6</span>,
                <span class="pl-s">'bagging_fraction'</span>: <span class="pl-c1">0.98</span>,
                <span class="pl-s">'feature_fraction'</span>: <span class="pl-c1">0.69</span>,
                <span class="pl-s">'bagging_freq'</span>: <span class="pl-c1">96</span>,
                <span class="pl-s">'reg_lambda'</span>: <span class="pl-c1">9</span>,
                <span class="pl-s">'reg_alpha'</span>: <span class="pl-c1">7</span>,
                <span class="pl-s">'min_split_gain'</span>: <span class="pl-c1">0.4</span>,
                <span class="pl-s">'nthread'</span>: <span class="pl-c1">8</span>,
                <span class="pl-s">'seed'</span>: <span class="pl-c1">2020</span>,
                <span class="pl-s">'silent'</span>: <span class="pl-c1">True</span>,
    }
    
    <span class="pl-s1">model</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-en">train</span>(<span class="pl-s1">params</span>, <span class="pl-s1">train_set</span><span class="pl-c1">=</span><span class="pl-s1">train_matrix</span>, <span class="pl-s1">num_boost_round</span><span class="pl-c1">=</span><span class="pl-c1">14269</span>, <span class="pl-s1">valid_sets</span><span class="pl-c1">=</span><span class="pl-s1">valid_matrix</span>, <span class="pl-s1">verbose_eval</span><span class="pl-c1">=</span><span class="pl-c1">1000</span>, <span class="pl-s1">early_stopping_rounds</span><span class="pl-c1">=</span><span class="pl-c1">200</span>)
    <span class="pl-s1">val_pred</span> <span class="pl-c1">=</span> <span class="pl-s1">model</span>.<span class="pl-en">predict</span>(<span class="pl-v">X_val</span>, <span class="pl-s1">num_iteration</span><span class="pl-c1">=</span><span class="pl-s1">model</span>.<span class="pl-s1">best_iteration</span>)
    
    <span class="pl-s1">cv_scores</span>.<span class="pl-en">append</span>(<span class="pl-en">roc_auc_score</span>(<span class="pl-s1">y_val</span>, <span class="pl-s1">val_pred</span>))
    <span class="pl-en">print</span>(<span class="pl-s1">cv_scores</span>)

<span class="pl-en">print</span>(<span class="pl-s">"lgb_scotrainre_list:{}"</span>.<span class="pl-en">format</span>(<span class="pl-s1">cv_scores</span>))
<span class="pl-en">print</span>(<span class="pl-s">"lgb_score_mean:{}"</span>.<span class="pl-en">format</span>(<span class="pl-s1">np</span>.<span class="pl-en">mean</span>(<span class="pl-s1">cv_scores</span>)))
<span class="pl-en">print</span>(<span class="pl-s">"lgb_score_std:{}"</span>.<span class="pl-en">format</span>(<span class="pl-s1">np</span>.<span class="pl-en">std</span>(<span class="pl-s1">cv_scores</span>)))</pre></div>
<pre><code>...
lgb_scotrainre_list:[0.7329726464187137, 0.7294292852806246, 0.7341505801564857, 0.7328331383185244, 0.7317405262608612]
lgb_score_mean:0.732225235287042
lgb_score_std:0.0015929470575114753
</code></pre>
<p>通过5折交叉验证可以发现，模型迭代次数在13000次的时候会停之，那么我们在建立新模型时直接设置最大迭代次数，并使用验证集进行模型预测</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s">""""""</span>
<span class="pl-s1">base_params_lgb</span> <span class="pl-c1">=</span> {
                    <span class="pl-s">'boosting_type'</span>: <span class="pl-s">'gbdt'</span>,
                    <span class="pl-s">'objective'</span>: <span class="pl-s">'binary'</span>,
                    <span class="pl-s">'metric'</span>: <span class="pl-s">'auc'</span>,
                    <span class="pl-s">'learning_rate'</span>: <span class="pl-c1">0.01</span>,
                    <span class="pl-s">'num_leaves'</span>: <span class="pl-c1">14</span>,
                    <span class="pl-s">'max_depth'</span>: <span class="pl-c1">19</span>,
                    <span class="pl-s">'min_data_in_leaf'</span>: <span class="pl-c1">37</span>,
                    <span class="pl-s">'min_child_weight'</span>:<span class="pl-c1">1.6</span>,
                    <span class="pl-s">'bagging_fraction'</span>: <span class="pl-c1">0.98</span>,
                    <span class="pl-s">'feature_fraction'</span>: <span class="pl-c1">0.69</span>,
                    <span class="pl-s">'bagging_freq'</span>: <span class="pl-c1">96</span>,
                    <span class="pl-s">'reg_lambda'</span>: <span class="pl-c1">9</span>,
                    <span class="pl-s">'reg_alpha'</span>: <span class="pl-c1">7</span>,
                    <span class="pl-s">'min_split_gain'</span>: <span class="pl-c1">0.4</span>,
                    <span class="pl-s">'nthread'</span>: <span class="pl-c1">8</span>,
                    <span class="pl-s">'seed'</span>: <span class="pl-c1">2020</span>,
                    <span class="pl-s">'silent'</span>: <span class="pl-c1">True</span>,
}

<span class="pl-s">"""使用训练集数据进行模型训练"""</span>
<span class="pl-s1">final_model_lgb</span> <span class="pl-c1">=</span> <span class="pl-s1">lgb</span>.<span class="pl-en">train</span>(<span class="pl-s1">base_params_lgb</span>, <span class="pl-s1">train_set</span><span class="pl-c1">=</span><span class="pl-s1">train_matrix</span>, <span class="pl-s1">valid_sets</span><span class="pl-c1">=</span><span class="pl-s1">valid_matrix</span>, <span class="pl-s1">num_boost_round</span><span class="pl-c1">=</span><span class="pl-c1">13000</span>, <span class="pl-s1">verbose_eval</span><span class="pl-c1">=</span><span class="pl-c1">1000</span>, <span class="pl-s1">early_stopping_rounds</span><span class="pl-c1">=</span><span class="pl-c1">200</span>)

<span class="pl-s">"""预测并计算roc的相关指标"""</span>
<span class="pl-s1">val_pre_lgb</span> <span class="pl-c1">=</span> <span class="pl-s1">final_model_lgb</span>.<span class="pl-en">predict</span>(<span class="pl-v">X_val</span>)
<span class="pl-s1">fpr</span>, <span class="pl-s1">tpr</span>, <span class="pl-s1">threshold</span> <span class="pl-c1">=</span> <span class="pl-s1">metrics</span>.<span class="pl-en">roc_curve</span>(<span class="pl-s1">y_val</span>, <span class="pl-s1">val_pre_lgb</span>)
<span class="pl-s1">roc_auc</span> <span class="pl-c1">=</span> <span class="pl-s1">metrics</span>.<span class="pl-en">auc</span>(<span class="pl-s1">fpr</span>, <span class="pl-s1">tpr</span>)
<span class="pl-en">print</span>(<span class="pl-s">'调参后lightgbm单模型在验证集上的AUC：{}'</span>.<span class="pl-en">format</span>(<span class="pl-s1">roc_auc</span>))
<span class="pl-s">"""画出roc曲线图"""</span>
<span class="pl-s1">plt</span>.<span class="pl-en">figure</span>(<span class="pl-s1">figsize</span><span class="pl-c1">=</span>(<span class="pl-c1">8</span>, <span class="pl-c1">8</span>))
<span class="pl-s1">plt</span>.<span class="pl-en">title</span>(<span class="pl-s">'Validation ROC'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">plot</span>(<span class="pl-s1">fpr</span>, <span class="pl-s1">tpr</span>, <span class="pl-s">'b'</span>, <span class="pl-s1">label</span> <span class="pl-c1">=</span> <span class="pl-s">'Val AUC = %0.4f'</span> <span class="pl-c1">%</span> <span class="pl-s1">roc_auc</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">ylim</span>(<span class="pl-c1">0</span>,<span class="pl-c1">1</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">xlim</span>(<span class="pl-c1">0</span>,<span class="pl-c1">1</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">legend</span>(<span class="pl-s1">loc</span><span class="pl-c1">=</span><span class="pl-s">'best'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">title</span>(<span class="pl-s">'ROC'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">ylabel</span>(<span class="pl-s">'True Positive Rate'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">xlabel</span>(<span class="pl-s">'False Positive Rate'</span>)
<span class="pl-c"># 画出对角线</span>
<span class="pl-s1">plt</span>.<span class="pl-en">plot</span>([<span class="pl-c1">0</span>,<span class="pl-c1">1</span>],[<span class="pl-c1">0</span>,<span class="pl-c1">1</span>],<span class="pl-s">'r--'</span>)
<span class="pl-s1">plt</span>.<span class="pl-en">show</span>()</pre></div>
<pre><code>Training until validation scores don't improve for 200 rounds
[1000]	valid_0's auc: 0.723676
[2000]	valid_0's auc: 0.727282
[3000]	valid_0's auc: 0.728593
[4000]	valid_0's auc: 0.729493
[5000]	valid_0's auc: 0.730087
[6000]	valid_0's auc: 0.730515
[7000]	valid_0's auc: 0.730872
[8000]	valid_0's auc: 0.731121
[9000]	valid_0's auc: 0.731351
[10000]	valid_0's auc: 0.731502
[11000]	valid_0's auc: 0.731707
Early stopping, best iteration is:
[11192]	valid_0's auc: 0.731741
调参后lightgbm单模型在验证集上的AUC：0.7317405262608612
</code></pre>
</li>
</ul>
<p><a target="_blank" rel="noopener noreferrer" href="https://camo.githubusercontent.com/d844850452a55a68d14f4bb8eab409c863118193/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303930353039343530373935312e706e67"><img src="https://camo.githubusercontent.com/d844850452a55a68d14f4bb8eab409c863118193/68747470733a2f2f696d672d626c6f672e6373646e696d672e636e2f32303230303930353039343530373935312e706e67" alt="output_29_1.png" data-canonical-src="https://img-blog.csdnimg.cn/20200905094507951.png" style="max-width:100%;"></a></p>
<p>可以看到相比最早的原始参数，模型的性能还是有提升的</p>
<div class="highlight highlight-source-python"><pre><span class="pl-s">"""保存模型到本地"""</span>
<span class="pl-c"># 保存模型</span>
<span class="pl-k">import</span> <span class="pl-s1">pickle</span>
<span class="pl-s1">pickle</span>.<span class="pl-en">dump</span>(<span class="pl-s1">final_model_lgb</span>, <span class="pl-en">open</span>(<span class="pl-s">'dataset/model_lgb_best.pkl'</span>, <span class="pl-s">'wb'</span>))</pre></div>
<ul>
<li>
<p><strong>模型调参小总结</strong></p>
<ul>
<li>
<p>集成模型内置的cv函数可以较快的进行单一参数的调节，一般可以用来优先确定树模型的迭代次数</p>
</li>
<li>
<p>数据量较大的时候（例如本次项目的数据），网格搜索调参会特别特别慢，不建议尝试</p>
</li>
<li>
<p>集成模型中原生库和sklearn下的库部分参数不一致，需要注意，具体可以参考xgb和lgb的官方API</p>
<blockquote>
<p><a href="https://xgboost.readthedocs.io/en/stable/parameter.html" rel="nofollow">xgb原生库API</a>，<a href="https://xgboost.readthedocs.io/en/stable/python/python_api.html#module-xgboost.sklearn" rel="nofollow">sklearn库下xgbAPI</a></p>
<p><a href="https://lightgbm.readthedocs.io/en/latest/Parameters.html" rel="nofollow">lgb原生库API</a>， <a href="https://lightgbm.readthedocs.io/en/latest/pythonapi/lightgbm.LGBMClassifier.html" rel="nofollow">sklearn库下lgbAPI</a></p>
</blockquote>
</li>
</ul>
</li>
</ul>
<h2><a id="user-content-46-经验总结" class="anchor" aria-hidden="true" href="#46-经验总结"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.775 3.275a.75.75 0 001.06 1.06l1.25-1.25a2 2 0 112.83 2.83l-2.5 2.5a2 2 0 01-2.83 0 .75.75 0 00-1.06 1.06 3.5 3.5 0 004.95 0l2.5-2.5a3.5 3.5 0 00-4.95-4.95l-1.25 1.25zm-4.69 9.64a2 2 0 010-2.83l2.5-2.5a2 2 0 012.83 0 .75.75 0 001.06-1.06 3.5 3.5 0 00-4.95 0l-2.5 2.5a3.5 3.5 0 004.95 4.95l1.25-1.25a.75.75 0 00-1.06-1.06l-1.25 1.25a2 2 0 01-2.83 0z"></path></svg></a>4.6 经验总结</h2>
<p>在本节中，我们主要完成了建模与调参的工作，首先在建模的过程中通过划分数据集、交叉验证等方式对模型的性能进行评估验证，并通过可视化方式绘制模型ROC曲线。</p>
<p>最后我们对模型进行调参，这部分介绍了贪心调参、网格搜索调参、贝叶斯调参共三种调参手段，重点使用贝叶斯调参对本次项目进行简单优化，大家在实际操作的过程中可以参考调参思路进行优化，不必拘泥于以上教程所写的具体实例。</p>
<hr>

</article>
  </div>





  </body>
</html>

