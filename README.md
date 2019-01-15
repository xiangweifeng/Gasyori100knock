# 画像処理100本ノック!!

画像処理の初学者のための問題１００問。

これは画像処理の基本的処理の知識を身に着け、アルゴリズムを理解するための100本ノックです。

ここに載っている問題はOpenCVでAPIが用意されているものが殆どですが、**あえてそれを自分の手で実装**してください。

**まだ作成中なので、随時更新していきます。なので問題の難易度の順番もめちゃくちゃです。**

**なるべくポピュラーなものを採用していますが、ネタ切れであんまり聞かないものもあります笑**

【注意】このページを利用して、または関して生じた事に関しては、私は一切責任を負いません。
すべて**自己責任**でお願い致します。

## Recent
- 最近息切れしてきた
- 2019.1.15 Q.4 大津の二値化 Q.5 HSV　を修正
- **【New!】2019.1.14. Q.58 - 59 ラベリング, Q.60 アルファブレンドを追加**
- **【New!】2019.1.11. Q.54 - 57 テンプレートマッチングを追加**
- **【New!】2019.1.10. Q.27 Bicubic や Q.36-40 JPEGにおける解答を一部修正しました。（画素値がオーバーフローした箇所の修正）、Tutorailにも説明を追加**
- **【New!】2019.1.10. Q.51-53 モルフォロジー勾配 などを追加**
- **2019.1.9. Q.47-50 モルフォロジー処理 などを追加**

## 環境設定

Python-3.6でやって下さい。
(解答はPython-3.6です)

### 1. Minicondaのインストール

https://conda.io/miniconda.html
のサイトからMinicondaをインストールします。

Minicondaがインストールできたら、以下コマンドで仮想環境を作成します。

```bash
$ conda create python=3.6 -n gasyori100
```

作成できたら、以下コマンドで仮想環境を動作します。

```bash
$ source actiavte gasyori100
```

するとこうなります。

```bash
(gasyori100) :~/work_space/Gasyori100knock/ :$ 
```

### 2. パッケージのインストール

以下のコマンドで必要なパッケージをインストールします。


```bash
$ pip install -r requirement.txt
```

### 3. 画像処理チュートリアル

以下のファイルを作成し sample.py という名前で保存し、実行します。

```python
import cv2

img = cv2.imread("assets/imori.jpg")
cv2.imshow("imori", img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

```bash
$ python sample.py
```

これで以下の画像が表示されれば成功です！
何かボタンを押せば消えます。


![](assets/sample.png)

次に画像処理に関するnumpyの扱い方のために**Tutorial**フォルダを見てみて下さい。（もう知ってるという人はスキップして下さい。）

これからは問題を解いていってください。それぞれのフォルダに問題内容が入っています。
問では assets/imori.jpg を使用して下さい。
各フォルダのREADMEに問題が書いてあります。

- チュートリアル >> Tutorial
- 問題1-10  >> Quetion_01_10
- 問題11-20 >> Question_11_20
- 問題21-30 >> Question_21_30
- 問題31-40 >> Question_31_40
- 問題41-50 >> Question_41_50
- 問題51-60 >> Question_51_60
- 問題61-70 >> Question_61_70
- 問題71-80 >> Quesiton_71_80
- 問題81-90 >> Question_81_90
- 問題91-100 >> Question_91_100


## 注意

- 本稿は画像処理の基礎的な知識・理論を学ぶための教材です。
- 解答ではなるべくコードを簡易化するために、main( )などを使用してしません。
- numpyを使用しますが、numpyに関する基本知識は載せません。各自調べて下さい。


## 問題

**未**になっている問題は解答未作成

### [問題1 - 10](https://github.com/yoyoyo-yo/Gasyori100knock/tree/master/Question_01_10)

|番号|問題||番号|問題|
|:---:|:---:|:---:|:---:|:---:|
|1|チャネル入れ替え| |6|減色処理 | |
|2|グレースケール化 | |7|平均プーリング |
|3|二値化 | |8|Maxプーリング | |
|4|大津の二値化 | |9|ガウシアンフィルタ |
|5|HSV変換 | |10|メディアンフィルタ |

### [問題11 - 20](https://github.com/yoyoyo-yo/Gasyori100knock/tree/master/Question_11_20)

|番号|問題||番号|問題|
|:---:|:---:|:---:|:---:|:---:|
|11|平滑化フィルタ | |16|Prewittフィルタ | 
|12|モーションフィルタ | |17|Laplacianフィルタ |
|13|MAX-MINフィルタ | |18|Embossフィルタ |
|14|微分フィルタ | |19|LoGフィルタ | 
|15|Sobelフィルタ | |20|ヒストグラム表示  | 

### [問題21 - 30](https://github.com/yoyoyo-yo/Gasyori100knock/tree/master/Question_21_30)

|番号|問題||番号|問題|
|:---:|:---:|:---:|:---:|:---:|
|21|ヒストグラム正規化 | |26|Bi-linear補間|
|22|ヒストグラム操作 | |27|Bi-cubic補間|
| 23|ヒストグラム平坦化 | |28|アフィン変換(平行移動)|
| 24|ガンマ補正| |29|アフィン変換(拡大縮小)|
|25|最近傍補間| |30|アフィン変換(回転)|

### [問題31 - 40](https://github.com/yoyoyo-yo/Gasyori100knock/tree/master/Question_31_40)

|番号|問題||番号|問題|
|:---:|:---:|:---:|:---:|:---:|
|31|アフィン変換(スキュー)| | 36&#9734;| JPEG圧縮 (Step.1)離散コサイン変換 |
|32**未**|フーリエ変換 | |37| PSNR|
|33**未**|フーリエ変換 ローパスフィルタ| |38&#9734;| JPEG圧縮 (Step.2)DCT+量子化|
|34**未**|フーリエ変換 ハイパスフィルタ| |39| JPEG圧縮 (Step.3)YCbCr表色系|
|35**未**|フーリエ変換 バンドパスフィルタ| | 40&#9734;| JPEG圧縮 (Step.4)YCbCr+DCT+量子化 |

### [問題41 - 50](https://github.com/yoyoyo-yo/Gasyori100knock/tree/master/Question_41_50)

|番号|問題||番号|問題|
|:---:|:---:|:---:|:---:|:---:|
| 41 | Cannyエッジ検出 (Step.1) エッジ強度 | | 46| Hough変換・直線検出 (Step.3) Hough逆変換 |
| 42 | Cannyエッジ検出 (Step.2) 細線化 | | 47 |モルフォロジー処理(膨張) |
| 43 | Cannyエッジ検出 (Step.3) ヒステリシス閾処理 | | 48 |モルフォロジー処理(収縮) |
| 44| Hough変換・直線検出 (Step.1) Hough変換 | | 49 |オープニング処理 |
| 45| Hough変換・直線検出 (Step.2) NMS | | 50 |クロージング処理 |

### [問題51 - 60](https://github.com/yoyoyo-yo/Gasyori100knock/tree/master/Question_51_60)

|番号|問題||番号|問題|
|:---:|:---:|:---:|:---:|:---:|
| 51 |モルフォロジー勾配 | | 56 |テンプレートマッチング NCC |
| 52 |トップハット変換 | | 57 |テンプレートマッチング ZNCC |
| 53 |ブラックハット変換 | | 58 |ラベリング 4近傍 |
| 54 |テンプレートマッチング SSD | | 59 |ラベリング 8近傍 |
| 55 |テンプレートマッチング SAD | | 60 |アルファブレンド |





|番号|問題|備考||番号|問題|備考|
|:---:|:---|:---:|:---:|:---:|:---|:---:|
|1|チャネル入れ替え|  ||21|ヒストグラム正規化 |
|2|グレースケール化 | ||22|ヒストグラム操作 |
|3|二値化 | || 23|ヒストグラム平坦化 |
|4|大津の二値化 | || 24|ガンマ補正|
|5|HSV変換 | ||25|最近傍補間|
|6|減色処理 | ||26|Bi-linear補間|
|7|平均プーリング | ||27|Bi-cubic補間|
|8|Maxプーリング | ||28|アフィン変換(平行移動)|
|9|ガウシアンフィルタ | ||29|アフィン変換(拡大縮小)|
|10|メディアンフィルタ | ||30|アフィン変換(回転)|
|11|平滑化フィルタ | ||31|アフィン変換(スキュー)|
|12|モーションフィルタ | ||32**未**|フーリエ変換 ||
|13|MAX-MINフィルタ | ||33**未**|フーリエ変換 ローパスフィルタ|
|14|微分フィルタ | ||34**未**|フーリエ変換 ハイパスフィルタ|
|15|Sobelフィルタ | ||35**未**|フーリエ変換 バンドパスフィルタ|
|16|Prewittフィルタ | || 36| JPEG圧縮 (Step.1)離散コサイン変換 |
|17|Laplacianフィルタ | ||37| PSNR|
|18|Embossフィルタ | ||38| JPEG圧縮 (Step.2)DCT+量子化|
|19|LoGフィルタ | ||39| JPEG圧縮 (Step.3)YCbCr表色系|
|20|ヒストグラム表示 ||| 40| JPEG圧縮 (Step.4)YCbCr+DCT+量子化 |


|番号|問題|備考||番号|問題|備考|
|:---:|:---|:---:|:---:|:---:|:---|:---:|
| 41 | Cannyエッジ検出 (Step.1) エッジ強度 |
| 42| Cannyエッジ検出 (Step.2) 細線化 |
| 43| Cannyエッジ検出 (Step.3) ヒステリシス閾処理 |
| 44 | Hough変換・直線検出 (Step.1) Hough変換 |
| 45| Hough変換・直線検出 (Step.2) NMS |
| 46| Hough変換・直線検出 (Step.3) Hough逆変換 |
| 47 |モルフォロジー処理(膨張) |
| 48 |モルフォロジー処理(収縮) |
| 49 |オープニング処理 |
| 50 |クロージング処理 |
| 51 |モルフォロジー勾配 |
| 52 |トップハット変換 |
| 53 |ブラックハット変換 |
| 54 |テンプレートマッチング SSD |
| 55 |テンプレートマッチング SAD |
| 56 |テンプレートマッチング NCC |
| 57 |テンプレートマッチング ZNCC |
| 58 |ラベリング 4近傍 |
| 59 |ラベリング 8近傍 |
| 60 |アルファブレンド |






## TODO

Hough, Gabor, HOG, TempleteMatching

