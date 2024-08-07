---
layout: default
title: 田邊研究室
---

### 研究室紹介

本研究室は人工知能・計算知能の一分野である進化計算の基礎研究を主に研究対象としています.
特に, ブラックボックス最適化, 多目的最適化, 進化アルゴリズムの振る舞いの実験的解析, 適応的パラメータ制御, 適応度地形解析, 自動アルゴリズム構成, 自動アルゴリズム選択, ベンチマーキング方法論の設計に現在関心があります.
学術研究の目的である知の体系化に貢献するために, 研究成果は積極的に英語論文として公開することを心がけています.
以下では, 本研究室 (2023年現在は田邊一人) の研究成果の一部を簡単に紹介します.

#### 高校生向け研究紹介

私達が作成しました, 横浜国立大学 理工学部 模擬講義動画がYouTubeにて公開されています. 次の動画では, アリの採餌行動から着想を得ましたアリコロニー最適化をTSPを対象問題として説明しています. 

[進化計算アルゴリズムの改良研究　～アリコロニー最適化を例に～](https://www.youtube.com/watch?v=CWLc14GOPpg), [slide](https://ryojitanabe.github.io/pdf/t-ynu-oa_slides.pdf)

アリコロニー最適化のより詳しい説明は, 次の文献を参照ください.

> 筒井茂義: アントコロニー最適化手法. 計測と制御, vol. 47, no. 6, pp. 466-472 [pdf](https://www.jstage.jst.go.jp/article/sicejl/47/6/47_466/_article/-char/ja/)

#### ブラックボックス最適化

ブラックボックス最適化問題では, 目的関数$f$が陽に与えられず, ある解$x$の目的関数値$f(x)$しか探索に利用できません. ブラックボックス最適化問題は解の良し悪しをシミュレーションにより評価する応用問題などに一般的に現れます. 進化計算手法はこのようなブラックボックス最適化に対して有用なアプローチの1つです.

以前, 私は進化計算手法の1つであるdifferential evolution (DE, 差分進化) に取り組んでいました. 当時DEは単純なアルゴリズムという利点はある反面, その性能は乏しいとされていました. それに対して, DEは効果的にアルゴリズムを設計しさえすれば, ブラックボックス最適化に対するstate-of-the-artに特定の条件下で匹敵するという成果が得られました.

*  Ryoji Tanabe: **Revisiting Population Models in Differential Evolution on a Limited Budget of Evaluations**, Proc. Parallel Problem Solving from Nature [(PPSN2020)](https://ppsn2020.liacs.leidenuniv.nl/), [pdf](https://ryojitanabe.github.io/pdf/t-ppsn2020.pdf), [code](https://github.com/ryojitanabe/de_expensiveopt), [poster](https://ryojitanabe.github.io/pdf/t-ppsn2020-poster.pdf)
* Ryoji Tanabe and Alex Fukunaga: **Improving the Search Performance of SHADE Using Linear Population Size Reduction**, Proc. IEEE Congress on Evolutionary Computation [(CEC2014)](http://www.ieee-wcci2014.org/), [(pdf)](https://ryojitanabe.github.io/pdf/tf-cec2014.pdf)
* Ryoji Tanabe and Alex Fukunaga: **Success-History Based Parameter Adaptation for Differential Evolution**, Proc. IEEE Congress on Evolutionary Computation [(CEC2013)](http://www.cec2013.org/), [(pdf)](http://metahack.org/CEC2013-SHADE.pdf)

#### 進化型多目的最適化

- Colabでのデモ
  - [進化型多目的最適化](https://colab.research.google.com/drive/1rVQA2QCF49DXt_88hcIoZXQIv-4Q-UUe?usp=sharing)
  - [指標](https://colab.research.google.com/drive/1VmmLNhnSFrZSXkMaeziQXh82Mtz4Uv8N?usp=sharing)

多目的最適化では, 互いにトレードオフな関係にある$m$個の目的関数$f_1, ..., f_m$を同時に最小化します. しかし, $f_1, ..., f_m$全てを最小化する完全最適解は一般的には存在しないため, 意思決定者が選好するパレート最適解の獲得が多目的最適化の目標となります.

進化計算を多目的最適化に拡張した進化型多目的最適化は, 目的空間にてパレートフロントを近似する解集合の獲得に使われます. 得られた解集合の中から, 意思決定者は自身が選好する解を選択します. 代表的な進化型多目的最適化アルゴリズムとして, NSGA-II, IBEA, MOEA/Dなどがあります.
私は新しい進化型多目的最適化アルゴリズムの設計, アルゴリズムの振る舞いの解析, 多目的最適化の指標の解析などに取り組んでいます.

*  Ryoji Tanabe, Youhei Akimoto, Ken Kobayashi, Hiroshi Umeki, Shinichi Shirakawa, Naoki Hamada: **A Two-phase Framework with a Bezier Simplex-based Interpolation Method for Computationally Expensive Multi-objective Optimization**, Proc. ACM Genetic and Evolutionary Computation Conference [(GECCO2022)](https://gecco-2022.sigevo.org), [pdf](https://arxiv.org/abs/2203.15292), [code](https://github.com/ryojitanabe/tpb), [slides](pdf/takush-gecco22-slides.pdf)
* Ryoji Tanabe and Hisao Ishibuchi: **An Analysis of Quality Indicators Using Approximated Optimal Distributions in a Three-dimensional Objective Space**, [IEEE Transactions on Evolutionary Computation](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=4235), [pdf](https://arxiv.org/abs/2009.12788), [link](https://ieeexplore.ieee.org/document/8957371)

#### 選好に基づく進化型多目的最適化

- [Colabでのデモ](https://colab.research.google.com/drive/12fkUpw43STew1osV-WZbMf2_v49J6Fb0?usp=sharing)

意思決定者の例えば「値段が1234円, 性能が567馬力の解が欲しい」というような選好情報が利用できれば, 進化型多目的最適化アルゴリズムの探索に組み込むことができます. 選好に基づく進化型多目的最適化は進化型多目的最適化を拡張した枠組みです. 一般的にパレートフロント全体を近似するよりも, その部分集合を近似する方が探索に費やすコストが低く抑えられます.

私はこのテーマに最近取り組み始めたばかりですが, いくつか興味深い成果が得られています. 例えば, 次の論文では選好に基づく進化型多目的最適化アルゴリズムをどのように性能評価するべきかを解析しています.

* Ryoji Tanabe, Ke Li: **Quality Indicators for Preference-based Evolutionary Multi-objective Optimization Using a Reference Point: A Review and Analysis**, [pdf](https://arxiv.org/abs/2301.12148), [code](https://github.com/ryojitanabe/prefqi)

#### 適応度地形解析

対象問題がどのような性質を有するのかを明らかにできれば, その性質に適した最適化アルゴリズムを設計・選択することができます.
また, ある特定の最適化アルゴリズムがなぜうまく動作する, またはしないのかを知る手がかりとなります.
適応度地形解析 (fitness landscape analysis) では, 対象問題の探索空間の1つ以上の性質を定量化します.
ここでいう性質とは問題領域に依存しますが, 例えばブラックボックス最適化の場合は多峰性, 大域的多峰性, 変数分離不可能性, 悪スケール性などです.
進化計算コミュニティでは古くから適応度地形解析の研究がされています.

Exploratory landscape analysis (ELA) はブラックボックス最適化において最も有用な適応度地形解析手法の1つです.
ELAでは小さなサイズの解集合を元に, 人間には理解できない低レベルの数値的特徴量集合を生成します.
生成された特徴量集合は, 性質を分類する分類モデルの学習に使用されます.
例えば, 対象問題の多峰性は「ない」, 「弱い」, 「強い」などの3つに分類できます.
その他にも, 特徴量集合は自動アルゴリズム選択にも使用されます.
ELAは10次元程度の規模の問題 (設計変数が10個程度の問題) において有用性が報告されていますが, それ以上の次元には適用された事例がほとんどありません.
次の論文では, 高次元ブラックボックス最適化では計算コストが問題となりELAの一部特徴量の計算が困難であることを明らかにしました.
また, この問題を解決するために, 次元削減を使用してELAの計算コストを抑える枠組みを提案しました.

*  Ryoji Tanabe: **Towards Exploratory Landscape Analysis for Large-scale Optimization: A Dimensionality Reduction Framework**, Proc. ACM Genetic and Evolutionary Computation Conference [(GECCO2021)](https://gecco-2021.sigevo.org/HomePage), [pdf](https://arxiv.org/abs/2104.10301), [supplement](pdf/gecco21-supp.pdf), [code](https://github.com/ryojitanabe/ela_drframework), [feature data](https://drive.google.com/drive/folders/1MRiiirvi-bJmaO56h3xlZrGITR4oERIP), [slides](pdf/t-gecco2021-slides.pdf), [YouTube](https://www.youtube.com/watch?v=QlVjhVAJs6Y)

制御パラメータを自己適応的に調整する進化アルゴリズムが研究されていますが, そのパラメータ適応の振る舞いを理解するのは容易ではありません. 次の論文では「適応的パラメータ空間」という概念を提案し, 適応型差分進化手法の振る舞いを解析しました:

*  Ryoji Tanabe: **Analyzing Adaptive Parameter Landscapes in Parameter Adaptation Methods for Differential Evolution**, Proc. ACM Genetic and Evolutionary Computation Conference [(GECCO2020)](http://gecco-2020.sigevo.org/), [pdf](https://arxiv.org/abs/2009.12531), [supplemental-pdf](pdf/t-gecco2020-supp.pdf), [code](https://github.com/ryojitanabe/APL), [slide](pdf/t-gecco2020-slide.pdf)

#### ベンチマーキング

一般的に, 強い仮定をおかずに進化アルゴリズムの性能を理論的に評価することは困難です.
これは進化アルゴリズムが有する確率的, 反復的, 集団的などの要素のためです.
そのため, 多くの場合は進化アルゴリズムの性能は実験的に評価されます.
しかし, 様々な要素を加味する必要があるため, 意味がありかつ信頼できる実験結果を得るのもまた困難です.
ベンチマーキングの研究分野では, 既存の実験方法の問題点を明らかにし, より良い実験方法を考えます.

次の論文では, 特徴量に基づくオフライン型自動アルゴリズム選択システムの既存のベンチマーキング方法の問題点を指摘するとともに, 改善案を提示しています.

* Ryoji Tanabe: **Benchmarking Feature-based Algorithm Selection Systems for Black-box Numerical Optimization**, [IEEE Transactions on Evolutionary Computation](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=4235), 2022. [pdf](https://arxiv.org/abs/2109.08377), [link](https://ieeexplore.ieee.org/document/9762332), [code](https://github.com/ryojitanabe/as_bbo)

次の論文では, 適応型進化アルゴリズム (差分進化) において, 適応機能の性能のみを評価する方法を提案しています:

* Ryoji Tanabe and Alex Fukunaga: **Reviewing and Benchmarking Parameter Control Methods in Differential Evolution**, [IEEE Transactions on Cybernetics](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=6221036), 2020. [link](https://ieeexplore.ieee.org/document/8626758), [pdf](https://arxiv.org/abs/2010.01035), [supplemental-pdf](pdf/tf-tcyb2018-supp.pdf)
*  Ryoji Tanabe and Alex Fukunaga: **TPAM: A Simulation-Based Model for Quantitatively Analyzing Parameter Adaptation Methods**, Proc. ACM Genetic and Evolutionary Computation Conference [(GECCO2017)](http://gecco-2017.sigevo.org/), [(pdf)](https://arxiv.org/abs/2010.01877), [(supplemental-pdf)](pdf/tf-gecco2017-supp.pdf), [(slide)](pdf/tf-gecco2017-slide.pdf)

次の論文では, state-of-the-artな進化型多目的最適化アルゴリズムの性能が無限アーカイブを使用することでどのように変化するのかを解析しています:

* Ryoji Tanabe, Hisao Ishibuchi, and Akira Oyama: **Benchmarking Multi- and Many-objective Evolutionary Algorithms under Two Optimization Scenarios**, IEEE Access [(link-to-pdf)](http://ieeexplore.ieee.org/document/8031325/), [(supplemental-website)](https://sites.google.com/site/benchmarkingmoeas/)

#### 自動アルゴリズム選択

ブラックボックス最適化の問題領域に対象を絞っても, これまでに数多くの最適化アルゴリズムが提案されています.
しかし, 一般的に最良な最適化アルゴリズムは問題依存です.
そのため, ユーザは自身の対象問題に対して最も適しているであろう1つの最適化アルゴリズムを試行錯誤を通して選ばなければなりません.
このアルゴリズム選択問題は, 最適化アルゴリズムの実応用の妨げとなります.
自動アルゴリズム選択は, 名前の通り適した最適化アルゴリズムを自動で選択する研究テーマです.
自動アルゴリズム選択はアルゴリズム選択問題の有効な解決策です.
一般的に自動アルゴリズム選択では, 機械学習により最適化アルゴリズムの性能を予測する回帰モデル, またはアルゴリズムの良し悪しを予想する分類モデルを構築します.

次の論文では, ブラックボックス最適化の特徴量に基づくオフラインアルゴリズム選択システムを実験的に解析しています:

* Ryoji Tanabe: **Benchmarking Feature-based Algorithm Selection Systems for Black-box Numerical Optimization**, [IEEE Transactions on Evolutionary Computation](https://ieeexplore.ieee.org/xpl/RecentIssue.jsp?punumber=4235), 2022. [pdf](https://arxiv.org/abs/2109.08377), [link](https://ieeexplore.ieee.org/document/9762332), [code](https://github.com/ryojitanabe/as_bbo)
