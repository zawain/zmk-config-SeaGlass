# SeaGlass ビルドガイド

- [SeaGlass ビルドガイド](#seaglass-ビルドガイド)
  - [1. 準備](#1-準備)
    - [1-1. 同梱品チェック](#1-1-同梱品チェック)
    - [1-2. 組立前にお客様自身で準備いただく部品](#1-2-組立前にお客様自身で準備いただく部品)
    - [1-3. 必要な工具](#1-3-必要な工具)
    - [1-4. 組付け済部品の分解](#1-4-組付け済部品の分解)
  - [2. はんだ付け手順](#2-はんだ付け手順)
    - [2-1. マイコンのはんだ付け](#2-1-マイコンのはんだ付け)
    - [2-2. 右手マウスクリックボタンのはんだ付け](#2-2-右手マウスクリックボタンのはんだ付け)
    - [2-3. 左手ロータリーエンコーダのはんだ付け](#2-3-左手ロータリーエンコーダのはんだ付け)
    - [2-4. 左右共通・電源スイッチはんだ付け](#2-4-左右共通電源スイッチはんだ付け)
    - [2-5. 左右共通・キーソケットはんだ付け](#2-5-左右共通キーソケットはんだ付け)
    - [2-6. トラックボールセンサー接続用ピンヘッダはんだ付け](#2-6-トラックボールセンサー接続用ピンヘッダはんだ付け)
    - [2-7. トラックボールセンサーはんだ付け](#2-7-トラックボールセンサーはんだ付け)
    - [2-8. トラボレンズ固定](#2-8-トラボレンズ固定)
  - [3. 組み立て手順](#3-組み立て手順)
    - [3-1. 右手側組み立て手順](#3-1-右手側組み立て手順)
    - [3-2. 左手側組み立て手順](#3-2-左手側組み立て手順)
  - [4. ファームウェア](#4-ファームウェア)
    - [4-1. テスト用ファームウェアのダウンロード](#4-1-テスト用ファームウェアのダウンロード)
    - [4-2. テスト用ファームウェアの書き込みとペアリング](#4-2-テスト用ファームウェアの書き込みとペアリング)
    - [4-3. Bluetooth切り替え手順](#4-3-bluetooth切り替え手順)
    - [4-4. 動作確認](#4-4-動作確認)
    - [4-5. ZMK Studioの活用](#4-5-zmk-studioの活用)
    - [4-6. ZMKファームウェアのカスタマイズとビルド方法](#4-6-zmkファームウェアのカスタマイズとビルド方法)
  - [5. お疲れさまでした](#5-お疲れさまでした)


![sea](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/sea.jpg)

<a id="1-準備"></a>
## 1. 準備

制作を始める前に、まずは必要なものがすべて揃っていることをご確認ください。

<a id="1-1-同梱品チェック"></a>
### 1-1. 同梱品チェック

| 名前 | 数 | 備考 |
|:-|:-|:-|
| 右手側用カバー | 1個 | 3DP製 |
| 右手側用トッププレート | 1個 | 3DP製 |
| 左手側用カバー | 1個 | 3DP製 |
| 左手側用トッププレート | 1個 | 3DP製 |
| 左右共通底面ケース | 2個 | 3DP製 |
| 右手側基板 | 1枚 | |
| 左手側基板 | 1枚 | |
| トラックボール基板 | 1枚 | |
| セラミック球2mm | 3個 | 右手側用トッププレートに組み込み済 |
| キーキャップ（白） | 30個 | 3DP製 |
| キーキャップ（青） | 10個 | 3DP製 |
| ロータリーエンコーダ用ホイール（青） | 2個 | 3DP製 |
| ロータリーエンコーダホイール用軸（青） | 2個 | 3DP製 |
| 電源スイッチカバー（青） | 2個 | 3DP製 |
| リセットボタン用パーツ | 2個 | 3DP製 |
| ロータリーエンコーダ | 2個 | |
| マウスクリック用スイッチ | 2個 | |
| 電源用スライドスイッチ | 2個 | |
| POM球 14mm | 1個 | |
| ネジM2 4mm | 8本 | |
| マイコン(xiao ble plus) | 2個 | はんだ付け済 |
| 滑り止め用ゴム足 | 8個 | |
| ガスケットマウント用クッション | 8個 | |

![all](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/all.jpg)


同梱品に不足がある場合は、お手数ですがご連絡いただけますと幸いです。\
迅速に対応させていただきます。

<a id="1-2-組立前にお客様自身で準備いただく部品"></a>
### 1-2. 組立前にお客様自身で準備いただく部品

| 名前 | 数 | 備考 |
|:-|:-|:-|
| Choc V2 キースイッチ | 40個 | |
| Lipoバッテリー | 2個 | 推奨バッテリーについては後述します |
| 17mmピッチ対応キーキャップ | 40個 | キーキャップ無しモデルの場合のみ別途ご用意ください |
| マイコン(xiao ble plus) | 2個 | マイコン無しモデルの場合のみ別途ご用意ください |
| 磁石 (直径6mm 厚さ2~3mm) | 8個 | 左右合体させたい方は磁石を別途ご用意ください。百均で購入可能です。|


SeaGlassのバッテリーは以下のバッテリーサイズを基準に設計していますので、こちらの購入をおすすめします。\
これ以外のバッテリーを使用する場合、コネクタの大きさ(JST 1.25mm)と極性に十分注意しお選びください。極性が逆のバッテリーを接続してしまうとマイコンが故障します。

500mAh 602040 2個入

https://www.amazon.co.jp/dp/B0FBWJFCLB/?coliid=I3BOB6AZA0OG7C 

<a id="1-3-必要な工具"></a>
### 1-3. 必要な工具

組み立てには下記の工具が必要です。

| 名前 | 備考 |
|:-|:-|
| はんだごて | 温度調整可能なもの推奨 |
| はんだ | |
| ニッパー | ピンヘッダの切断用 |
| ドライバー | |
| ピンセット | |
| 両面テープ | バッテリー固定用 |

<a id="1-4-組付け済部品の分解"></a>
### 1-4. 組付け済部品の分解

梱包時に組付けられた状態になっている部品がいくつかあります。\
組み立てを行う前に、一度それらを分解してください。半組み立てキット場合の説明を記載していますが、お手元のキットの形態に応じて適宜読み替えてください。

1. 背面のネジを４本外し、底面ケースを取り外します。
2. 基板とトッププレートを取り外します。半組み立てキットの場合マイコンがケースと干渉するため基板を斜めに持ち上げるように取り外してください。
![1-4-1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/1-4-1.jpeg)
3. （左手側のみ）ロータリーエンコーダが刺さっているので取り外します。ホイールパーツを軸から取り外します。軸はロータリーエンコーダに刺さったままにしておいて大丈夫です。
![1-4-2](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/1-4-2.jpeg)
4. （右手側のみ）トラックボール読み取り基板を取り外します。ぐりぐりと引っ張ると抜けます。
![1-4-3](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/1-4-3.jpeg)
5. トッププレートにキーキャップマウント用のパーツがついているので取り外します。
6. キーキャップマウントからキーキャップを取り外します。ドライバーやピンセットなどで裏側から軸を押し出すと外しやすいと思います。キーキャップマウントはもう使わないので処分して大丈夫です。
![1-4-4](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/1-4-4.jpeg)

<a id="2-はんだ付け手順"></a>
## 2. はんだ付け手順

ここからはんだ付け作業に入ります。\
特に断りがない作業は左右どちらの基板でも同じ作業をすると読み取ってください。

<a id="2-1-マイコンのはんだ付け"></a>
### 2-1. マイコンのはんだ付け

Comming soon...\
※ 半組み立てキットではこの工程は対応不要です！

<a id="2-2-右手マウスクリックボタンのはんだ付け"></a>
### 2-2. 右手マウスクリックボタンのはんだ付け

右手側基板にマウスクリックボタンを取り付けます。

1. マウスクリックボタンを基板の表面に置きます。スイッチ部分が上側になるように配置してください。
2. 片側の足をはんだ付けします。パッドまではんだがしっかり流れるよう十分に加熱してください。
![right1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/right1.png)
3. ズレや浮きがないことを確認したら反対側の足もはんだ付けします。
![right2](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/right2.png)
4. 画像のようになればOKです。
![right3](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/right3.png)

<a id="2-3-左手ロータリーエンコーダのはんだ付け"></a>
### 2-3. 左手ロータリーエンコーダのはんだ付け

左手側基板にロータリーエンコーダを取り付けます。

1. ロータリーエンコーダを基板の表面から差し込みます。ホイール部品は邪魔になるので外しておいてください。（軸は刺したままで大丈夫です。）
2. 基板を裏返し、はみ出した足をニッパーでカットしてください。
![left1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/left1.png)
3. ロータリーエンコーダが浮いたり傾かないように注意しながらはんだ付けしてください。
4. 画像のようになればOKです。
![left2](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/left2.png)
![left3](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/left3.png)
5. （テスター頒布版のみ）ロータリーエンコーダがチャタリングを起こす場合は画像のように真ん中のピンと左右のピンをつなぐようにコンデンサを追加することでチャタリングを低減することができます。(応急処置なのではんだ付けが汚くてすみません。)\
   コンデンサは10nFか22nF推奨です。本頒布版では基板に組み込むので本対応は不要です！
![left4](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/left4.jpg)

<a id="2-4-左右共通電源スイッチはんだ付け"></a>
### 2-4. 左右共通・電源スイッチはんだ付け

左右両方の基板に電源スイッチを取り付けます。

1. スライドスイッチを基板の表面から差し込み、マスキングテープなどで固定してください。
2. 基板を裏返し、はみ出した足をニッパーでカットしてください。
![pw1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/pw1.png)
3. スライドスイッチが浮かないように注意しながらはんだ付けします。
![pw2](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/pw2.png)
4. 画像のようになればOKです。
![pw3](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/pw3.png)

<a id="2-5-左右共通キーソケットはんだ付け"></a>
### 2-5. 左右共通・キーソケットはんだ付け

左右両方の基板にキーソケットを取り付けます。左右各20個、合計40個のキーソケットが必要です。

1. キーソケットのフットプリントの片側にはんだを盛ります。
![sc1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/sc1.png)
2. フットプリントの形と合うようにキーソケットを置いてください。
![sc2](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/sc2.png)
3. キーソケットをピンセットなどで抑えながら盛ったはんだを溶かしてください。
![sc3](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/sc3.png)
4. キーソケットが固定できたら、反対側にもはんだ付けを行ってください。

<a id="2-6-トラックボールセンサー接続用ピンヘッダはんだ付け"></a>
### 2-6. トラックボールセンサー接続用ピンヘッダはんだ付け

Comming soon...\
※ 半組み立てキットではこの工程は対応不要です！

<a id="2-7-トラックボールセンサーはんだ付け"></a>
### 2-7. トラックボールセンサーはんだ付け

トラックボール読み取りセンサーを基板に取り付けます。

1. 半組み立てキットの場合、トラックボール基板にピンをはんだ付け済みで、右手側基板のソケットの差し込み済の状態になっています。センサーのはんだ付けのため、メイン基板からトラックボール基板を引き抜いてください。
2. センサーを基板に差し込みます。画像を参考に、向きを間違えないようにしてください。
![tb1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/tb1.png)
1. センサーをマスキングテープなどで固定してください。
2. すべてのピンにはんだ付けをします。はんだを盛りすぎない・長時間熱しすぎないように注意してください。
3. 画像のようになればOKです。
![tb2](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/tb2.png)

<a id="2-8-トラボレンズ固定"></a>
### 2-8. トラボレンズ固定

トラックボールセンサー用レンズを取り付けます。

1. センサーの保護シールを剥がします。
![tb3](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/tb3.png)
2. センサー用レンズを差し込みます。向きを間違えないように注意してください。
![tb4](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/tb4.png)
3. センサー裏面の、レンズのピンがはみ出している箇所に剥がした保護シールを乗せ、その上からはんだごてを軽く当ててピンを溶かし、センサー用レンズを固定してください。
![tb5](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/tb5.png)
4. 画像のようにレンズのピンが平たく潰れていればOKです。
![tb6](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/tb6.png)

以上ではんだ付けは完了です。お疲れさまでした！\
各パーツが正しく取り付けられているか、もう一度ご確認ください。

<a id="3-組み立て手順"></a>
## 3. 組み立て手順

はんだ付けが完了したら、キーボードの組み立てを行います。

<a id="3-1-右手側組み立て手順"></a>
### 3-1. 右手側組み立て手順

1. トッププレートを乗せ、位置がずれないようにキースイッチをいくつかはめ込んでください。
![rt1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt1.png)
2. 画像を参考にクッションシールを貼ってください。一部カットが必要です。
![rt2](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt2.jpg)
3. バッテリーコネクタを差し込んでください。コネクタの相性によってかなり硬いことがありますが、コネクタの向きがあっていれば画像の深さまで差し込むことができます。
![rt3](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt3.png)
4. トラックボール基板を差し込んでください。
![rt4](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt4.png)
5. ボトムプレートの四隅にゴム足を貼り付けてください。ボトムプレートは左右共通です。
![rt5](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt5.png)
6. （任意）左右を磁石で合体させたい方はボトムプレートに磁石をはめ込んでください。底面同士がくっつくように極性をしっかり確認してください。
7. ボトムプレートにリセットスイッチ用パーツを乗せてください。固定はされないので落とさないよう取り扱いに注意してください。
![rt6](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt6.png)
9. ボトムプレートにバッテリーを装着してください。
![rt7](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt7.png)
9. 右手側カバーにPOM球を乗せてください。
![rt8](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt8.png)
10. マイコンのUSBコネクタをトッププレートの穴にあわせるように意識しながら、斜めから挿し込むように基板をセットしてください。
![rt9](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt9.png)
11. リセットスイッチがはずれないよう注意しつつボトムプレートを閉じ、4箇所ネジ止めしてください。このときネジを強く締めすぎるとネジ穴が潰れてしまう可能性があるので、締めすぎには注意してください。
![rt10](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt10.png)
![rt11](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/rt11.png)
12. 電源スイッチを装着してください。
![lt5](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/lt5.png)
13. キーキャップとキースイッチを取り付けたら完成です！

<a id="3-2-左手側組み立て手順"></a>
### 3-2. 左手側組み立て手順

1. 画像のようにロータリーエンコーダに軸とホイールを装着してください。トッププレートを装着した後はロータリーエンコーダのつけ外しができなくなるので組み立ての順番に注意してください。
![lt1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/lt1.png)
2. ホイールの下に滑り込ませるようにトッププレートを装着してください。
![lt2](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/lt2.png)
3. 右手側と同様にクッションシールおよびゴム足貼り付けと、バッテリー・リセットスイッチの装着を行ってください。
4. 右手側と同様に斜め方向からトップカバーを装着してください。ロータリーエンコーダとホイールのはめ込みがある分右手側よりややシビアですが、信じてグッとやればズボッとハマるはずです。
![lt4](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/lt4.png)
5. 右手側と同様にネジを4箇所止め、電源スイッチを装着してください。
6. キーキャップとキースイッチを取り付けたら完成です！

![fin](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/fin.png)
組み立ておつかれさまでした！

<a id="4-ファームウェア"></a>
## 4. ファームウェア

次に、動作確認のためにファームウェアの書き込みを行います。

<a id="4-1-テスト用ファームウェアのダウンロード"></a>
### 4-1. テスト用ファームウェアのダウンロード

以下のリンクからファームウェアをダウンロードしてください。\
[ダウンロード](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/test_firmware.zip)

ダウンロード後zipファイルを展開し、
- `SeaGlass_L rgbled_adapter-seeeduino_xiao_ble-zmk.uf2`
- `SeaGlass_R rgbled_adapter-seeeduino_xiao_ble-zmk.uf2`
- `settings_reset-seeeduino_xiao_ble-zmk.uf2`

という3つのファイルが入っていることを確認してください。

<a id="4-2-テスト用ファームウェアの書き込みとペアリング"></a>
### 4-2. テスト用ファームウェアの書き込みとペアリング

マイコンにファームウェアを書き込みます。テスト用といいつつ通常動作するファームウェアなので、この工程が済むと一旦の完成になります。（キーマップは確認用の暫定的なものです。）\
おそらく今後自分だけのファームウェア設定を模索していくことになると思います。テスト用ではない本番のファームウェアはぜひ皆さんの手で作り上げてください。

1. マイコンをブートローダーモードにします。
   - PCとSeaGlass右手側をUSBケーブルで接続します。
   - リセットボタンを素早く2回押します。SeaGlassのリセットボタンは本体裏面の白いボタンです。
   - PC上で「NO NAME」という名称でドライブが認識されれば成功です。（マイコンのロットなどによっては表示名が異なる場合があります。）
2. 「NO NAME」ドライブに `settings_reset-seeeduino_xiao_ble-zmk.uf2` をドラッグ&ドロップまたはコピー&ペーストで書き込みます。この時、macの場合画像のようなメッセージが出る場合がありますが、「NO NAME」ドライブが自動的に認識されなくなっていたら書き込みに成功しています。\
   `settings_reset-seeeduino_xiao_ble-zmk.uf2` は設定初期化用のファイルなので、基本的に今後は書き込み不要です。
  ![err1](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/err1.png)
3. 再度マイコンをブートローダーモードにし、今度は右手用のファームウェア`SeaGlass_R rgbled_adapter-seeeduino_xiao_ble-zmk.uf2` を同様の手順で書き込みます。この時も同様のメッセージが出ることがありますが、正常です。
4. 左手側も同様の手順で`settings_reset-seeeduino_xiao_ble-zmk.uf2` → `SeaGlass_L rgbled_adapter-seeeduino_xiao_ble-zmk.uf2` の順番で書き込みを行います。
5. 左右の書き込みが完了したらUSBケーブルを取り外し、両方のSeaGlassのスイッチをオン（上側）にし、マイコンのリセットスイッチを左右どちらも一度ずつ押します
6. 電源オンの時やリセットの時にマイコンのLEDが点滅するはずです。以下の意味がありますので、正常に点滅することを確認してください。
   - 最初の点灯（バッテリーの残量）
     - 🟢/🟡/🔴の三段階で点灯。初期ファームウェアでは40%以上は🟢、20%までは🟡、それ以下は🔴が点灯するように設定されています。
     - この閾値はファームウェアを編集することでお好みに設定できます。
   - 2つ目の点灯（ブルートゥースの接続状況）
      - 🔵は接続成功、🟡はペアリング中、🔴は接続失敗を意味します。
      - 左右で少し意味が異なり、左側の点灯は親側（右側）へのペアリング状況を意味し、右側の点灯はPCなどの機器へのペアリング状況を意味します。
  - ですので、ファームウェア書き込み後の正常な点灯は以下のとおりです。
    - 左手側：🟢/🟡/🔴（バッテリーの充電状況次第）→ 🔵（左手側との接続成功）
    - 右手側：🟢/🟡/🔴（バッテリーの充電状況次第）→ 🟡（機器とのペアリング中）
  
  詳細は[zmk-rgbled-widget](https://github.com/caksoylar/zmk-rgbled-widget)のREADMEをご覧ください。
7. 正常に点灯していたらPC側でBluetoothデバイスとして「SeaGlass」が認識されているはずです。そのまま接続を行ってください。

<a id="4-3-bluetooth切り替え手順"></a>
### 4-3. Bluetooth切り替え手順

本キーボードは最大5台のBluetoothデバイスとの接続を切り替えることができます。\
接続先の切り替えはキーマップで設定可能で、テストファームウェアだとレイヤー6のz~bキーに設定されています。


<a id="4-4-動作確認"></a>
### 4-4. 動作確認

Bluetoothの接続後、キーやトラックボールの動作を確認してください。不具合があったら、最も可能性が高いのははんだ付けの不良です。各種はんだ付けに不備が無いかチェックしてみてください。\
どうしても解決しないときはXやboothのメッセージやgithubのissueなど、手段は問いませんのでご連絡をお願いいたします。



<a id="4-5-zmk-studioの活用"></a>
### 4-5. ZMK Studioの活用

SeaGlassはZMK Studioに対応しています。ZMK Studioを使用することでファームウェアを書き換えることなくGUIでキーマップを簡単に編集できます。\
ただしZMK Studio自体まだ開発段階？のようで、設定可能なキーボード設定に一部制限があります。なのでZMK Studioでのカスタマイズのみでは後々物足りなくなる可能性が高いですが、GitHubに慣れていない方などはまずはこちらでいろいろ触ってみるのも手だと思います。

1. [ZMK Studio](https://zmk.studio/)にアクセスします。
2. 接続するキーボードを選択します。
3. 接続が完了すると、現在のキーマップが表示されます。
4. 変更したいキーをクリックし、任意の動作を選択します。
5. 設定が完了したら右上の保存ボタンをクリックして変更を保存します。
   
細かい操作や設定、どういった制限があるのかなどについてはここでは説明しませんので詳しくは[こちら](http://zmk.dev/docs/features/studio)を参照してください。

<a id="4-6-zmkファームウェアのカスタマイズとビルド方法"></a>
### 4-6. ZMKファームウェアのカスタマイズとビルド方法

ZMK Studioで対応していない高度な設定を行いたい場合は、直接ファームウェアをカスタマイズしてビルドする必要があります。ファームウェアのカスタマイズビルドにはGitHubを使用します。\
おおまかなフローは以下のとおりです。（リポジトリ名はSeaGlassに読み替えてください。）\
ここでは各ツールの細かな使い方の説明はしませんので、必要に応じて調べてみてください。
![flow](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/flow.jpg)

1. 本リポジトリをフォークする
  - あなたのGitHubアカウント上に`zmk-config-SeaGlass`リポジトリが表示されていればOKです。
2. 手動またはKeymapEditorでファームウェアを編集する
  - [ZMK Keymap Editor](https://nickcoutsos.github.io/keymap-editor/) とあなたのGitHubアカウントを接続すると、KeymapEditorから直接リポジトリへ変更をプッシュすることができます。
3. ビルドされたファームウェアをダウンロードして書き込む
  - 「GitHub Actions」という機能を使って、コードをリモートリポジトリへプッシュするたびに自動的にファームウェアがビルドされます。
  - Actionsはリポジトリの「Actions」タブから確認できます。初回は手動で有効化が必要です。
  - リポジトリに変更をプッシュすると数分でビルドが完了します。「Actions」タブから最新のワークフローを開き、Artifactsからファームウェアをダウンロードしてください。
    ![build](https://raw.githubusercontent.com/hama-be/zmk-config-SeaGlass/refs/heads/main/docs/img/build.png)
  - ダウンロードしたファームウェアを書き込みます。キーマップの変更の場合は右側だけの書き込みでOKです。


ZMKファームウェアについて、細かくカスタマイズをしたい方は[ZMK公式ドキュメント](https://zmk.dev/docs/)を参照してください。
 
<a id="5-お疲れさまでした"></a>
## 5. お疲れさまでした

これにて組み立ては完了です。お疲れさまでした！\
ぜひ感想や要望などあればハッシュタグ `#SeaGlass_kbd` で発信をお願いいたします🌊