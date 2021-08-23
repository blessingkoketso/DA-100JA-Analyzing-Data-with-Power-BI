---
lab:
    title: 'Power BI Desktop におけるデータ分析の実施'
    module: 'モジュール 10 - 高度な分析を実行する'
---


# **Power BI Desktop におけるデータ分析の実施**

**このラボの推定所要時間: 45 分**

このラボでは、**販売調査** レポートを作成します。

このラボでは次の作業を行う方法について説明します。

- アニメーション化した散布図の作成

- ビジュアルを使用した値の予測

- 分解ツリー ビジュアルの操作

- 主要なインフルエンサー ビジュアルの操作

### **ラボ ストーリー**

このラボは、データの準備からレポートやダッシュボードとしての発行までの完全なストーリーとして設計された一連のラボのうちの 1 つです。ラボは任意の順序で完了できます。ただし、複数のラボを行う場合は、最初の 10 のラボを次の順序で行うことをお勧めします。

1. Power BI Desktop でのデータの準備

2. Power BI Desktop へのデータの読み込み

3. Power BI Desktop でのデータのモデル化、パート 1

4. Power BI Desktop でのデータのモデル化、パート 2

5. Power BI Desktop での DAX 計算の作成、パート 1

6. Power BI Desktop での DAX 計算の作成、パート 2

7. Power BI Desktop でのレポートの設計、パート 1

8. Power BI Desktop でのレポートの設計、パート 2

9. Power BI ダッシュボードを作成する

10. Power BI でのページ分割されたレポートの作成

11. **Power BI Desktop におけるデータ分析の実施**

## **演習 1: レポートの作成**

この演習では、**販売調査** レポートを作成します。

### **タスク 1: 開始する – サインイン**

このタスクでは、Power BI にサインインしてこのラボ用の環境を設定します。

*重要: 前の実習で Power BI にすでにサインインしている場合は、次のタスクから続行してください。*

1. Microsoft Edge を開くには、タスク バーの Microsoft Edge プログラムのショートカットをクリックします。

 	![画像 7](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image1.png)

1. Microsoft Edge ブラウザー ウィンドウで **https://powerbi.com** に移動します。

 	*ヒント: Microsoft Edge のお気に入りバーで Power BI サービスのお気に入りを使用することもできます。*

1. 「**サインイン**」 (右上隅) をクリックします。

 	![画像 5](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image2.png)

1. 提供されたアカウント詳細を入力します。

1. パスワードを更新するように求められたら、指定されたパスワードを再入力し、新しいパスワードを入力して確認します。

 	*重要: 新しいパスワードを必ず記録してください。*

1. サインイン プロセスを完了します。

1. Microsoft Edge からサインインを維持するかどうかを確認するメッセージが表示されたら、「**はい**」をクリックします。

1. Microsoft Edge ブラウザー ウィンドウの Power BI サービスの「**ナビゲーション**」ウィンドウで、「**マイ ワークスペース**」を展開します。

 	![画像 4](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image3.png)

1. Microsoft Edge ブラウザー ウィンドウを開いたままにします。

### **タスク 2: 開始する – データセットの作成**

このタスクでは、データセットを作成してこのラボ用の環境を設定します。

*重要: **Power BI ダッシュボードの作成**ラボでデータセットをすでに発行している場合は、次のタスクから続行してください。*

1. Microsoft Edge ブラウザー ウィンドウの Power BI サービスの「**ナビゲーション**」ウィンドウで、「**マイ ワークスペース**」を展開します。

	![画像 8](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image4.png)

2. 「**ファイル**」タイルで、「**取得**」をクリックします。

	![画像 10](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image5.png)

3. 「**ローカル ファイル**」タイルをクリックします。

	![画像 11](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image6.png)

4. 「**開く**」ウィンドウで、**D:\DA100\Labs\09-create-power-bi-dashboard\Solution** フォルダーに移動します。

5. **Sales Analysis.pbix** ファイルを選択し、「**開く**」をクリックします。

6. データセットを置き換えるメッセージが表示されたら、「**置換**」をクリックします。

### **タスク 3: レポートを作成する**

このタスクでは、**Sales Exploration** レポートを作成します。

1. Power BI Desktop を開くには、タスク バーにある Microsoft Power BI Desktop のショートカットをクリックします。

	*重要: Power BI Desktop をすでに開いている場合は (以前のラボから)、そのインスタンスを閉じます。*

	![画像 14](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image7.png)

2. 「はじめに」ウィンドウを閉じるには、ウィンドウの左上にある「**X**」をクリックします。

	![画像 13](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image8.png)

3. Power BI Desktop が Power BI サービスにサインインしていない場合は、右上の「**サインイン**」をクリックします。

	![画像 16](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image9.png)

4. Power BI サービスへのサインインに使用したものと同じアカウントを使用して、サインイン プロセスを完了します。

5. ファイルを保存するには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

6. **保存** を選択します。

	![画像 12](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image10.png)

7. 「**名前を付けて保存**」ウィンドウで、**D:\DA100\MySolution** フォルダーに移動します。

8. 「**ファイル名**」ボックスに「**Sales Exploration**」と入力します。

	![画像　1](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image11.png)

9. 「**Sales Analysis**」データセットへのライブ接続を作成するには、「**ホーム**」リボン タブの「**データ**」グループ内から「**Power BI データセット**」をクリックします。

	![画像 15](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image12.png)

10. 「**レポートを作成するデータセットの選択**」ウィンドウで、「**Sales Analysis**」データセットを選択します。

11. 「**作成**」をクリックします。

	![画像 17](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image13.png)

12. Power BI Desktop ファイルを保存します。

	*これから 4 つのレポート ページを作成し、各ページで異なるビジュアルを使用してデータを分析および調査します。*

## **演習 2: 散布図の作成**

この演習では、アニメーション化できる散布図を作成します。

### **タスク 1: アニメーション化した散布図を作成する**

このタスクでは、アニメーション化できる散布図を作成します。

1. **ページ 1** の名前を「**散布図**」に変更します。

	![画像 67](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image14.png)

2. レポート ページに**散布図**ビジュアルを追加してから、ページ全体に表示されるように再配置およびサイズ変更します。

	![画像 18](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image15.png)

	![画像 75](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image16.png)

3. 次のフィールドをビジュアル ウェル/領域に追加します。

	ラボでは、フィールドを参照するために省略表記を使用します。次のようになります。**Reseller | Business Type**。この例では、**Reseller** はテーブル名、**Business Type** はフィールド名です。

	- 凡例: **Reseller | Business Type**

	- X 軸: **Sales | Sales** 

	- Y 軸: **Sales | Profit Margin**

	- サイズ: **Sales | Quantity**

	- 再生軸: **Date | Quarter**

	![画像 39](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image17.png)

	***再生軸**ウェル/領域にフィールドを追加すると、チャートをアニメーション化できます。*

4. 「**フィルター**」ウィンドウで、「**Product | Category**」フィールドを「**このページをフィルター**」ウェル/領域にドラッグします。

5. フィルター カードで、「**バイク**」でフィルター処理します。

	![画像 40](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image18.png)

6. グラフをアニメーション化するには、左下の「**再生**」をクリックします。

	![画像 41](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image19.png)

7. **2018 年度第 1 四半期**から **2020 年度第 4 四半期**までのアニメーション サイクル全体を見てください。

	*散布図では、メジャーの値を同時に把握できます。ここでは、注文の Quantity (量)、Sales (売上) の収益、および Profit Margin (利益率) の値です。*

	*各バブルは、リセラーのビジネス タイプを表します。バブル サイズの変化は、注文量の増減を反映しています。水平方向の動きは売上収益の増減を表し、垂直方向の動きは収益性の増減を表します。*

8. アニメーションが停止したら、バブルの 1 つをクリックして、時間の経過に従ってトラッキングを表示します。

9. カーソルを任意のバブルの上に置くと、その時点でのリセラー タイプのメジャー値を説明するヒントが表示されます。

10. 「**フィルター**」 ペインで、「**服**」 でフィルター処理するだけで、結果が非常に異なっていることがわかります。

11. Power BI Desktop ファイルを保存します。

## **演習 3: 予測の作成**

この演習では、予測を作成して、売上収益の将来の可能性を判断します。

### **タスク 1: 予測を作成する**

このタスクでは、予測を作成して、売上収益の将来の可能性を判断します。

1. 新しいページを追加し、ページの名前を「**予測**」に変更します。

	![画像 66](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image20.png)

2. レポート ページに**折れ線グラフ** ビジュアルを追加してから、ページ全体に表示されるように配置してサイズを変更します。

	![画像 19](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image21.png)

	![画像 74](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image22.png)

  

3. 次のフィールドをビジュアル ウェル/領域に追加します。

	- 軸: **Date | 日付**

	- 値: **Sales | Sales** 

	![画像 46](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image23.png)

4. 「**フィルター**」ウィンドウで、「**Date | Year**」フィールドを「**このページをフィルター**」ウェル/領域に追加します。

5. フィルター カードで、**2019 年度**および **2020 年度** に表示されます。

	![画像 47](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image24.png)

	*タイム ラインで予測する場合は、正確で安定した予測を生成するために、少なくとも 2 サイクル (年) のデータが必要になります。*

  

6. 「**Product | Category**」フィールドも「**このページのフィルター**」ウェル/領域に追加し、「**バイク**」でフィルター処理します。

	![画像 48](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image25.png)

7. 予測を追加するには、「**視覚化**」ウィンドウの下で、「**分析**」ウィンドウを選択します。

	![画像 20](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image26.png)

8. 「**予測**」セクションを展開します。

	![画像 50](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image27.png)

	*「**予測**」セクションが使用できない場合は、ビジュアルが正しく構成されていない可能性があります。予測は、2 つの条件が満たされている場合にのみ使用できます: 軸には date 型のフィールドが 1 つあり、値フィールドは 1 つだけです。*

9. 「**追加**」をクリックします。

	![画像 51](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image28.png)

10. 次の予測プロパティを構成します。

	- 予測の長さ: 1 か月

	- 信頼区間: 80%

	- 季節性: 365

11. 「**適用**」をクリックします。

	![画像 52](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image29.png)

12. 折れ線ビジュアルで、予測が履歴データを超過して 1 か月延長されていることに注目してください。

	*灰色の領域は、信頼度を表します。信頼度が広いほど、安定性が低くなるため、予想はより精度が低くなります。*

	*サイクルの長さ (この例では、年) がわかっている場合は、季節性ポイントを入力する必要があります。週 (7)、または月 (30) の場合もあります。*

13. 「**フィルター**」ウィンドウで、「**Clothing**」のみでフィルター処理すると、結果が異なることに注意してください。

14. Power BI Desktop ファイルを保存します。

## **演習 4: 分解ツリーの操作**

この演習では、分解ツリーを作成して、リセラーの地域と利益率の関係を調べます。

### **タスク 1: 分解ツリーを操作する**

このタスクでは、分解ツリーを作成して、リセラーの地域と利益率の関係を調べます。

1. 新しいページを追加し、ページの名前を「**Decomposition Tree**」に変更します。

	![画像 65](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image30.png)

2. 「**挿入**」リボンの「**AI ビジュアル**」グループ内から、「**Decomposition Tree**」をクリックします。

	*ヒント: AI ビジュアルは、「**視覚化**」ウィンドウでも使用できます。*

	![画像 54](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image31.png)

3. ページ全体に表示されるようにビジュアルを配置し、サイズを変更します。

	![画像 73](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image32.png)

4. 次のフィールドをビジュアル ウェル/領域に追加します。

	- 分析: **Sales | Profit Margin**

	- 説明: **Reseller | Geography** (階層全体)

	![画像 57](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image33.png)

5. 「**フィルター**」ウィンドウで、「**Date | Year**」フィールドを「**このページのフィルター**」ウェルに設定し、フィルターを「**FY2020**」に設定します。

	![画像 59](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image34.png)

6. 分解ツリー ビジュアルで、ツリーのルートが**Profit Margin** -0.94% で

	![画像 21](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image35.png)

7. プラス アイコンをクリックし、コンテキスト メニューで「**高値**」を選択します。

	![画像 61](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image36.png)

8. 分解ツリーには、利益率の高い順に並べられたリセラーが表示されていることに注意してください。

9. レベルを削除するには、ビジュアル上部の 「**Reseller**」 ラベルの横にある 「**X**」 をクリックします。

	![画像 62](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image37.png)

10. プラス アイコンをもう一度クリックし、**Country-Region**のレベルに展開します。

11. **United States**  **State-Province**レベルに展開します。

12. ビジュアルの下部にある**State-Province**の下向き矢印を使用し、収益性の低い州までスクロールします。

13. **New York**州の収益性がマイナスであることに注目してください。

14. **New York**から**Reseller** レベルに展開します。

15. 根本原因を簡単に分離できることに注目してください。

	![画像 22](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image38.png)

	***United States**は **FY2020** に利益を生み出していません。**New York**は、正の収益を達成していない州の 1 つです。これは、4 つのリセラーの支払いが商品の標準原価を下回っているためです。*

16. Power BI Desktop ファイルを保存します。

## **演習 5: キー インフルエンサーの操作**

この演習では、主要なインフルエンサー AI ビジュアルを使用して、リセラーのビジネス タイプと地域の収益性に何が影響するかを判断します。

### **タスク 1: 主要なインフルエンサーを操作する**

このタスクでは、主要なインフルエンサー AI ビジュアルを使用して、リセラーのビジネス タイプと地域の収益性に何が影響するかを判断します。

1. 新しいページを追加してから、そのページの名前を「**主要なインフルエンサー**」に変更します。

	![画像 64](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image39.png)

2. 「**挿入**」リボンの「**AI ビジュアル**」グループ内から、「**主要なインフルエンサー**」をクリックします。

	*ヒント: AI ビジュアルは、「**視覚化**」ウィンドウでも使用できます。*

	![画像 71](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image40.png)

3. ページ全体に表示されるようにビジュアルを配置し、サイズを変更します。

	![画像 72](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image41.png)

4. 次のフィールドをビジュアル ウェルに追加します。

	- 分析: **Sales | Profit Margin**

	- 説明: **Reseller | Business Type** と **Reseller | Geography** (階層全体)

	- 展開方法: **Sales | Quantity**

	![画像 3](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image42.png)

5. ビジュアルの左上に、「**主要なインフルエンサー**」がフォーカスされており、利益率を増加させる要因が何かを理解するために特定の影響が設定されていることにに注目してください。

	![画像 76](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image43.png)

6. 結果を確認すると、「**ボテル**」の都市が増加する可能性が高いということが分かります。

7. 目標を変更して、利益率の低下に影響を与える影響を判断します。

	![画像 77](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image44.png)

8. 結果を確認します。

9. セグメントを検出するには、左上の「**上位セグメント**」を選択します。

	![画像 78](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image45.png)

10. Profit Margin が高くなりそうな場合に、セグメントを判断することがターゲットであることに注目してください。

11. ビジュアルにセグメントが (円で) 表示されたら、セグメントの 1 つをクリックして、そのセグメントに関する情報を表示します。

12. セグメントの結果を確認します。

### **タスク 2: 仕上げ**

このタスクではラボを完了します。

1. 「**散布図**」ページを選択します。

2. Power BI Desktop ファイルを保存します。

3. ワークスペースにファイルを発行するには、「**ホーム**」リボン タブの「**共有**」グループ内から「**発行**」をクリックします。

	![画像 23](Linked_image_Files/10-perform-data-analysis-in-power-bi-desktop_image46.png)

4.  Power BI Desktop を閉じます。
