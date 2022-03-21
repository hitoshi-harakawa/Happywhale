# Happywhale
クジラ/イルカの画像識別コンペ
## 2022/2/9開始
- Description(訳: DeepL)
  
私たちは、指紋や顔認識で人を識別していますが、動物にも同じようなアプローチができるのでしょうか？実際、研究者は尾や背びれ、頭など体の部位の形や模様から海洋生物を手作業で追跡しています。写真による識別は、写真IDとして知られ、海洋哺乳類の科学にとって強力なツールです。写真による個体識別は、海洋哺乳類の科学にとって強力なツールであり、個体を長期にわたって追跡し、個体群の状態や傾向を評価することができます。クジラやイルカの写真識別を自動化することで、研究者は画像の識別時間を99％以上短縮することができます。より効率的な識別が可能になれば、これまで手が届かなかった、あるいは不可能だった規模の研究ができるようになるかもしれません。
  
現在、ほとんどの研究機関は、時間がかかり、時には不正確な人間の目による手作業での照合に頼っています。手作業による照合は、写真を見つめて個体同士を比較し、一致するものを見つけ、新しい個体を識別するというもので、何千時間もの時間を費やしています。研究者はクジラの写真を見て楽しむことができますが、手作業による照合は範囲と範囲が限定されます。

このコンペティションで開発されたアルゴリズムは、研究協力と市民科学のウェブプラットフォームであるHappywhaleに実装される予定です。Happywhaleは、質の高い保全科学と教育を通じて、海洋環境に対する世界的な理解と思いやりを高めることをミッションとしています。Happywhaleは、海洋哺乳類に関心を持つすべての人が参加できる革新的なツールを構築することで、一般の人々が科学に参加しやすく、またやりがいを感じられるようにすることを目的としています。また、このプラットフォームは、強力なコラボレーションツールによって、研究コミュニティにも貢献しています。

このコンペティションでは、クジラやイルカのユニークな、しかししばしば微妙なナチュラルマークの特徴によって個々のクジラを照合するモデルを開発することになります。28の研究機関によって構築された複数種のデータセットから、特に背びれと体側面の画像に注目してください。優秀な応募作品は、高速かつ正確な写真IDソリューションを提案します。

成功すれば、変化する世界の海への影響をよりよく理解し、管理するための先進技術の構築に携わることができます。これまでの自動化の試みは、5万頭を超えるクジラのグローバルデータベースを構築し、最もクジラの多い地域で最高時速11マイルで航行するクルーズ船との協定を締結するまでに至りました。海洋生物の同定を自動化するあなたのアイデアは、人間が海洋に与える影響の増大を克服し、保全科学に不可欠なツールを提供することにつながるでしょう。クジラがいるなら、方法はある！
 
- Evaluation(訳: DeepL)

投稿は、MAP@5に従って評価されます。

![image](https://user-images.githubusercontent.com/68815430/153024368-301db5ba-23c4-474d-9076-9b9e5e58995d.png)

ここで，𝑈は画像数，𝑃(𝑘)はカットオフ𝑘での精度，𝑛は画像あたりの予測数，𝑟𝑒𝑙(𝑘)はランク𝑘のアイテムが関連（正）ラベルならば1に等しい指標関数，それ以外では0である．

いったん正しいラベルがオブザベーションのためにスコアされると、そのラベルはもはやそのオブザベーションに関連するとはみなされず、そのラベルの追加予測は計算でスキップされる。たとえば、正しいラベルがオブザベーションの A であるとき、次の予測はすべて平均精度 1.0 のスコアです。

![image](https://user-images.githubusercontent.com/68815430/153022804-7719f6b1-afee-445b-a4e5-2af813590914.png)

- Submission File
  
テストセット内の各画像に対して、最大5つのindividual_idラベルを予測することができます。テストセットには学習データにはない個体が存在するが、それらはnew_individualとして予測すること。ファイルはヘッダを含み、以下のフォーマットである必要がある。

![image](https://user-images.githubusercontent.com/68815430/153022734-c4a29b8a-83dd-4f05-883d-4fac635bc28c.png)

- Data

前回のHappyWhaleでは、ザトウクジラのフロックの画像から個体を予測する課題でした。このデータセットに含まれるクジラとイルカは、背びれ、背中、頭、脇腹の形状、特徴、マーク（天然のものと後天性のものがある）により識別することができます。種や個体によっては、非常にはっきりした特徴を持つものもあれば、非常にはっきりしないものもあります。さらに、個々の特徴は時間とともに変化することもある。このコンペティションのデータは、28の異なる研究機関から収集された30種、15,000個体以上のユニークな海洋哺乳類の画像を含んでおり、この課題は大幅に拡大されています。その個体は、海洋研究者によって手作業で識別され、individual_idが付与されており、あなたの仕事は、画像中のこれらの個体を正しく識別することです。世界中の海洋哺乳類の理解と保護を大きく前進させる可能性を秘めた、チャレンジングなタスクです。

データの品質に関する重要な注意点です。多くの異なる研究機関から集められたこのデータセットをまとめることは、現実的に多くの課題を提起しました。データ品質の問題を最小化し、漏れを最小限にするために多大な努力が払われた。しかし、間違いなく問題は存在します。しかし、よほどのことがない限り、大会中にデータを更新することはないと考えています。


## 2/9
ゼロから作るDeep Learning 3章完了
- 出力層の活性化関数は、回帰問題では恒等関数、2クラス分類問題ではシグモイド関数、多クラス分類ではソフトマックス関数を用いるのが一般的
- バッチ処理により処理時間を短縮する

画像コンペ取り組み方

https://japan.zdnet.com/article/35140207/2/
![image](https://user-images.githubusercontent.com/68815430/153024040-46bf1118-4665-472f-ab65-b63427006e47.png)

## 2/10
ゼロから作るDeep Learning 4章完了

画像認識における「特徴量」
- 入力データ（画像）から本質的なデータを的確に抽出するよう設計された変換器(SIFT、SURF、HOG） 
- 画像データをベクトルに変換する

全ての変数の偏微分をベクトルとしてまとめたものを勾配という
ニューラルネットワークの学習においては、学習率の値を変更しながら、正しく学習できているかどうか、確認作業を行うのが一般的
学習率は大きすぎても小さすぎてもダメ　-> ハイパーパラメータの設定なので、トライ&エラー

## 2/11
ゼロから作る Deep Learning 5章: 実装要再確認
- ニューラルネットワークを構成する「層（レイヤ）」を一つのclassで実装する
- __init__では、メソッド内の処理に必要な（値を保持する必要のある）変数を設定
- 推論時はSoftmaxレイヤを使用しない（Affineレイヤの出力であるスコアを用いる）、学習時はSoftmaxレイヤを使用する
- 誤差逆伝播法により、勾配をより早く求めることができる

ゼロから作る Deep Learning 6章
- 最適化手法毎にクラスを実装、共通のメソッドを持つようにすると機能のモジュール化が容易に
- 重みの初期値は均一な値に設定してはいけない -> 誤差逆伝播法において全ての重みの値が均一に更新されてしまうため
- モデルに表現力を持たせるため、アクティベーション（活性化関数後の出力データ）に偏りがない方が良い
- Batch Normalizationにより、学習の進行を促進させ、重みの初期値にロバストになる

## 2/12
ゼロから作る Deep Learning 7章
- パディングは出力サイズを大きくするため、ストライドは出力サイズを小さくするために行う

ゼロから作る Deep Learning 8章
- 層を深くすることで、パラメータの削減、学習効率の向上につながる

## 2/13
はじめてのパターン認識 1, 2章
ディープラーニングの数学 1章

### 疑問点
- 画像は1次元のベクトルとして読み込ませるのが良いのか？ -> Affineレイヤはyes、CNNは形状を維持
- biasは初期値0が一般的？　　-> yes
- 式5.13 YのXによる偏微分は重みの転置をかける？

## 2/14
- インスタンス認識をキーワードに実装方法を調べる
- インスタンス認識の論文などチェックしてみる
- プラスでその他のアプローチも調べる

インスタンス認識に関する記事

https://ai.googleblog.com/2020/09/advancing-instance-level-recognition.html

DELG（DEep Local and Global Image Features）
画像の局所特徴量（特定の画像領域に関する記述子/形状情報）と大域特徴量（画像の内容全体を要約したもの）の統一モデル

画像検索

DELG（DEep Local and Global Image Features）コード
https://github.com/tensorflow/models/tree/master/research/delf

![image](https://user-images.githubusercontent.com/68815430/153877924-616f740e-cb78-4991-952f-f2cb8932041d.png)

解説記事
https://deepsquare.jp/2020/09/delg/

tensorflow公式のGitHub
https://github.com/tensorflow/models/tree/master/research/delf

実装記事
https://qiita.com/taiga518/items/24c7abdb763a530b9a67

実装karnel
https://www.kaggle.com/camaskew/host-baseline-example
https://www.kaggle.com/ragnar123/baseline-dnn-with-delg-global-embeddings

## 2/15

Google landmark 検索タスク 1st Solution

https://www.kaggle.com/c/landmark-recognition-2020/discussion/187821
https://github.com/seungkee/google_landmark_retrieval_2020_1st_place_solution
https://arxiv.org/abs/2010.01650

EDA

https://www.kaggle.com/prikshitsingla/happy-whale-kernel

- イルカと鯨の画像と個体ID、種が与えられ、画像から5つの個体IDを予測。評価指標はMAP@5
- train.csvは51,033行、3列（画像名、種別、個体ID）、nullなし
- 種別は30
- イルカより鯨の画像が多い（1:2）
- belugaをwhaleに、globisをwhaleに、kiler_whale -> killer_whale、bottlenose_dospin -> bottlenose_dolphinに統合

## 2/16

EDA_日本語のcode

https://www.kaggle.com/yama09/happy-whales-and-dolphins
https://www.kaggle.com/yama09/happywhale-2022-starter

- ユニーク個体数15,587
- test画像は27,956

ArcFaceのベースライン

https://www.kaggle.com/ks2019/happywhale-arcface-baseline-tpu

## 2/20

scikit-learn, Keras, TensorFlowによる実践機械学習　1章

## 2/23

環境構築
kaggle-api利用

データのダウンロード

## 2/27

https://www.kaggle.com/andrej0marinchenko/happywhale-0-679

kaggle notebook上で実行し、score 0.678

https://haltaro.github.io/2018/07/10/kaggle-api

## 3/1

https://www.kaggle.com/aikhmelnytskyy/happywhale-arcface-baseline-eff7-tpu-768-concat

kaggle notebook上で実行し、score 0.729

ベースモデル: https://www.kaggle.com/ks2019/happywhale-arcface-baseline-tpu

## 3/7

tfrecordsのガイド

http://warmspringwinds.github.io/tensorflow/tf-slim/2016/12/21/tfrecords-guide/

距離学習概要

https://qiita.com/tancoro/items/8d3438cab574a02319cc

## 3/10

TFRecordは「メモリに収まらないような大きいデータを処理できいるようにしたもので、レコード指向のバイナリフォーマット」

## 3/20

arcfaceのモデル解読

## 3/21

kaggle日記
https://github.com/Yuki-Tanaka-33937424/kaggle-Shopee-Price-Match-Guarantee

arcface解説
https://qiita.com/yu4u/items/078054dfb5592cbb80cc

距離学習
https://qiita.com/tancoro/items/8d3438cab574a02319cc

<img width="709" alt="image" src="https://user-images.githubusercontent.com/68815430/159259658-21576b99-cb8c-4f47-b570-ef191c656289.png">

なぜarcface?に対する回答

これはMNISTの数字のように単純な画像分類問題のように見えますが、1つ非常に重要な違いがあります。つまり、テストセットにnew_individualという新しいクラスがあることです。従って、NNはあらゆる新しいクジラを、既存の15587種の学習用クジラから区別することを学習しなければならない。ArcFaceは、最終層のニューロンから得られる埋め込みをクラスタリングすることで、入力画像が出力層のどのニューロンクラスにも属さないことを確信できる方法を提供するのです。
ArcFaceがなければ、どんな画像もトレーニングセットの15587個の個体のうちの1つに分類されてしまいますが、そのときにできることは、それ以下では新しい個体として分類しないという信頼度の下限を設定することです。ArcFaceは、この素朴な選択肢よりも明らかに優れています。ですから、ほとんどの人がArcFaceを使い、新しい鯨の個体の画像をうまく識別することが重要なのです。

参照: https://www.kaggle.com/c/happy-whale-and-dolphin/discussion/313697

effnetのversion変えることでscore上がる？
バックフィンのデータセットを使えばスコア上がる？
下記データセット使えばスコア上がる？
https://www.kaggle.com/code/lextoumbourou/happywhale-tfrecords-with-bounding-boxes/notebook
ConvNeXt + arkfaceでスコア上がる？（pytorch）
https://www.kaggle.com/code/clemchris/pytorch-backfin-convnext-arcface/comments
