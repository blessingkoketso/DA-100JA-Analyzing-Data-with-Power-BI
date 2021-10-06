---
lab:
    title: 'Power BI Desktop でのデータの準備'
    module: 'モジュール 2 - Power BI でのデータの取得'
---

# **Power BI Desktop でのデータの準備**

**このラボの推定所要時間: 45 分**

このラボでは、Adventure Works 社向けの Power BI Desktop ソリューションの開発を開始します。これには、ソース データへの接続、データのプレビュー、データ プレビューの技法を使ったソース データの特性と品質の理解が含まれます。

このラボでは次の作業を行う方法について説明します。

- Power BI Desktop を開く

- Power BI Desktop のオプションを設定する

- ソース データへの接続

- ソース データのプレビュー

- データ プレビュー手法を使用したデータへのよりよい理解

### **ラボ ストーリー**

このラボは、データの準備からレポートやダッシュボードとしての発行までの完全なストーリーとして設計された一連のラボのうちの 1 つです。ラボは任意の順序で完了できます。ただし、複数のラボを行う場合は、最初の 10 のラボを次の順序で行うことをお勧めします。

1. **Power BI Desktop でのデータの準備**

2. Power BI Desktop へのデータの読み込み

3. Power BI Desktop でのデータのモデル化、パート 1

4. Power BI Desktop でのデータのモデル化、パート 2

5. Power BI Desktop での DAX 計算の作成、パート 1

6. Power BI Desktop での DAX 計算の作成、パート 2

7. Power BI Desktop でのレポートの設計、パート 1

8. Power BI Desktop でのレポートの設計、パート 2

9. Power BI ダッシュボードを作成する

10. Power BI でのページ分割されたレポートの作成

11. Power BI Desktop におけるデータ分析の実施

12. 行レベルのセキュリティを実行する

## **演習 1: データの準備**

この演習では 8 個の Power BI Desktop クエリを作成します。6 個のクエリは、SQL Server のデータ、2 個は CSV ファイルのデータをそれぞれソースとします。

### **タスク 1: Power BI Desktop ファイルを保存する**

このタスクでは、まず Power BI Desktop ファイルを保存します。

1. Power BI Desktop を開くには、タスク バーにある Microsoft Power BI Desktop のショートカットをクリックします。

 	![画像 2](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image1.png)

1. 「はじめに」ウィンドウを閉じるには、ウィンドウの右上にある「**X**」をクリックします。

 	![画像 3](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image2.png)

1. ファイルを保存するには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

1. **保存** を選択します。

 	![画像 4](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image3.png)

1. 「**名前を付けて保存**」ウィンドウで、**D:\DA100\MySolution** フォルダーに移動します。

1. 「**ファイル名**」ボックスに「**Sales Analysis**」と入力します。

 	![画像 14](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image4.png)

1. 「**保存**」をクリックします。

	![画像 17](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image5.png)

	ヒント: 左上にある「**保存**」アイコンをクリックしてファイルを保存することもできます。

	![画像 18](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image6.png)

### **タスク 2: Power BI Desktop のオプションを設定する**

このタスクでは、Power BI Desktop オプションを設定します。

1. Power BI Desktop で、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

1. 左側の「**オプションと設定**」を選択し、「**オプション**」を選択します。

 	![画像　1](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image7.png)

1. 左側にある「**オプション**」ウィンドウの「**現在のファイル**」グループで、「**データの読み込み**」を選択します。

    ![画像 5](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image8.png)

    現在のファイルの「**データ ロード**」設定では、モデリング時の既定の動作を決定する設定オプションを使用できます。

1. **リレーションシップ** グループで、既にオンになっている 2 つのオプションをオフにします。

	![画像 7](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image9.png)

    これらの 2 つのオプションを有効にすることは、データ モデルを開発する場合に役立ちますが、ラボ エクスペリエンスをサポートするために以前に無効にしています。**Power BI Desktop へのデータの読み込み**ラボでリレーションシップを作成すると、それぞれを追加する理由がわかります。

1. 「**OK**」をクリックします。

    ![画像 9](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image10.png)

1. Power BI Desktop ファイルを保存します。

### **タスク 3: SQL Server からデータを取得する**

このタスクでは、SQL Server テーブルに基づいてクエリを作成します。

1. 「**ホーム**」リボン タブの「**データ**」グループ内から、「**SQL Server**」をクリックします。

	![画像 19](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image11.png)

2. 「**SQL Server Database**」ウィンドウの「**サーバー**」ボックスに、「**localhost**」と入力します。

	![画像 21](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image12.png)

	このラボでは、**localhost** を使用して SQL Server データベースに接続します。独自のソリューションを作成する場合は、この方法はお勧めしません。理由は、ゲートウェイ データ ソースが **localhost** を解決できないためです。

3. 「**OK**」をクリックします。

	![画像 22](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image13.png)

4. 「**ナビゲーター**」ウィンドウの左側で、**AdventureWorksDW2020** データベースを展開します。

	**AdventureWorksDW2020** データベースは、 **AdventureWorksDW2017** サンプル データベースに基づいています。コース ラボの学習の目的をサポートするために変更されています。

	![画像 28](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image17.png)

5. **DimEmployee** テーブルを選択します (ただし、チェックはしません)。

	![画像 29](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image18.png)

6. 右側のウィンドウで、テーブル データのプレビューに注目します。

	プレビュー データで、列と行のサンプルを確認できます。

7. クエリを作成するには、次の 6 つのテーブルの横のチェックボックスを選択します。

	- DimEmployee

	- DimEmployeeSalesTerritory

	- DimProduct

	- DimReseller

	- DimSalesTerritory

	- FactResellerSales

8. 選択したテーブルのデータに変換を適用するには、「**データの変換**」をクリックします。

	このラボではデータを変換しません。このラボの目的は、**Power Query エディター** ウィンドウでのデータの探索とプロファイリングに焦点を当てています。

	![画像 30](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image19.png)

### **タスク 4: SQL Server クエリのプレビュー**

このタスクでは、SQL Server クエリのデータをプレビューします。まず、データに関する関連情報を学習します。また、列の品質、列の分布、および列プロファイル ツールを使用してデータを理解し、データ品質を評価します。

1. **Power Query エディター** ウィンドウの左側に、**クエリ** ウィンドウがあります。

	![画像 31](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image20.png)

	**クエリ** ウィンドウには、チェックを付けた各テーブルに対して 1 つのクエリが含まれています。

2. 最初のクエリを選択します - **DimEmployee**。

	![画像 33](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image21.png)

	SQL Server データベースの **DimEmployee** テーブルには、従業員ごとに 1 行が格納されます。このテーブルの行のサブセットは営業担当者を表し、開発するモデルに関連します。

3. 左下のステータス バーで、テーブルの統計情報があります。テーブルは 33 列、296 行あります。

	![画像 36](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image22.png)

4. データ プレビュー ペインで、水平方向にスクロールして、すべての列を確認します。

5. 最後の 5 つの列に 「**テーブル**」 または 「**値**」 リンクが含まれていることに注意してください。

	この 5 列は、データベース内の他のテーブルとのリレーションシップを表しています。これらはテーブルを結合するために使用できます。「**Power BI Desktop へのデータの読み込み**」ラボでテーブルを結合します。

6. 列の品質を評価するには、「**表示**」リボン タブの**データ プレビュー** グループ内から、「**列の品質**」をオンにします。

	![画像 35](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image23.png)

	列の品質機能を使用すると、列にある有効、エラー、または空の値の割合を簡単に判断できます。

7. **Position** 列 (最後の 6 列目) では、行の 94% が空 (null) であることに注意してください。

	![画像 38](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image24.png)

8. 列の分布を評価するには、「**表示**」リボン タブの**データ プレビュー** グループ内から、「**列の分布**」をオンにします。

	![画像 40](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image25.png)

9. **Position** 列をもう一度確認し、4 つの別個の値と 1 つの一意の値があることを確認します。

10. **EmployeeKey** (第 1) 列の列の分布を確認します。296 の別個の値と 296 の一意の値があります。

	![画像 43](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image26.png)

	個別のカウントと一意のカウントが同じ場合は、列に一意の値が含まれていることを意味します。モデリングの際、一部のモデル テーブルに一意の列を含めることが重要です。これらの一意の列を使用して、1対多のリレーションシップを作成できます。これは、「**Power BI Desktop でのデータのモデル化、パート 1**」ラボで行います。

11. **クエリ** ウィンドウで、**DimEmployeeSalesTerritory** クエリを選択します。

	![画像 44](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image27.png)

	**DimEmployeeSalesTerritory** テーブルには、従業員ごとに 1 行と、その従業員が管理する販売区域の地域が格納されています。テーブルでは、1 人の従業員に多数のリージョンを関連付けることができます。一部の従業員は、1 つ、2 つ、またはそれ以上の地域を管理しています。このデータをモデル化する場合、多対多のリレーションシップを定義する必要があります。これは、「**Power BI Desktop でのデータのモデル化、パート 2**」ラボで行います。

12. **クエリ** ウィンドウで、**DimProduct** クエリを選択します。

	![画像 46](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image28.png)

	**DimProduct** テーブルには、会社が販売した商品ごとに 1 行が含まれています。

13. 水平方向にスクロールして、最後の列を表示します。

14. **DimProductSubcategory** 列に注目してください。

	「**Power BI Desktop へのデータの読み込み**」ラボでこのクエリに変換を追加する場合は、**DimProductSubcategory** 列を使用してテーブルを結合します。

15. **クエリ** ウィンドウで、**DimReseller** クエリを選択します。

	![画像 49](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image29.png)

	**DimReseller** テーブルには、リセラーごとに 1 行が含まれています。リセラーは、Adventure Works 製品の販売、流通、または付加価値の提供を行っています。

16. 列の値を表示するには、「**表示**」リボン タブの「**データ プレビュー**」グループ内から、「**列プロファイル**」をオンにします。

	![画像 41](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image30.png)

17. **BusinessType** 列ヘッダーを選択します。

18. データ プレビュー ウィンドウの下に新しいウィンドウがあります。

19. データ プレビュー ウィンドウで、列の統計および値の分布を確認します。

20. データ品質の問題に注意してください: warehouse に対して 2 つのラベルがあります (**Warehouse**、およびスペルミスがある **Ware House**)。

	![画像 51](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image31.png)

21. カーソルを **Ware House** バーの上に置くと、この値を持つ 5 つの行があることに注意してください。

    **Power BI Desktop へのデータの読み込み**ラボでは、これらの 5 つの行に変換を適用してラベルを再適用します。

22. **クエリ** ウィンドウで、**DimSalesTerritory** を選択します。

	![画像 52](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image32.png)

	**DimSalesTerritory** テーブルには、**Corporate HQ** (本社) を含む、販売地域ごとに 1 行が含まれています。地域は国に割り当てられ、国はグループに割り当てられています。**Power BI Desktop でのデータのモデル化、パート 1** ラボでは、地域、国、またはグループ レベルでの分析をサポートする階層を作成します。

23. **クエリ** ウィンドウで、**FactResellerSales** クエリを選択します。

	![画像 54](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image33.png)

	**FactResellerSales** テーブルには、販売注文明細行ごとに 1 行が含まれており、販売注文には 1 つまたは複数の明細行項目が含まれています。

24. **TotalProductCost** 列の列の品質を確認し、行の 8% が空であることを確認します。

	![画像 63](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image34.png)

	**TotalProductCost** 列の値の欠落は、データ品質の問題です。この問題に対処するために、**Power BI Desktop でのデータの読み込み**ラボでは、関連する **DimProduct** テーブルに格納されている製品の標準原価を使用して、欠落した値を埋めるための変換を適用します。

### **タスク 5: CSV ファイルからデータを取得する**

このタスクでは、CSV ファイルに基づいてクエリを作成します。

1. 新しいクエリを追加するには、「**Power Query エディター**」ウィンドウの「**ホーム**」リボン タブにある「**新しいクエリ**」グループ内から、「**新しいソース**」下向き矢印をクリックし、**テキスト/CSV** を選択します。

	![画像 70](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image35.png)

2. 「**開く**」ウィンドウで、**D:\DA100\Resources** フォルダーに移動し、**ResellerSalesTargets.csv** ファイルを選択します。

3. 「**開く**」をクリックします。

4. **ResellerSalesTargets.csv** ウィンドウで、プレビュー データを確認します。

5. 「**OK**」をクリックします。

	![画像 71](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image36.png)

  
‎ 

6. 「**クエリ**」ウィンドウで、**ResellerSalesTargets** クエリが追加されていることに注目してください。

	![画像 72](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image37.png)

	**ResellerSalesTargets** CSV ファイルには、1 年ごとの、営業担当者 1 人につき 1 行が含まれます。各行に、12 個の月間売上目標 (1,000 単位で表示) が記録されています。Adventure Works 社の事業年度は 7 月 1 日に始まることに注意してください。

7. 空の値を含む列がない点に注目してください。

	月間売上目標がない場合は、代わりにハイフン文字が格納されています。

8. 列名の左側にある各列ヘッダーのアイコンを確認します。

	![画像 74](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image38.png)

	アイコンは、列のデータ型を表します。**123** は整数で、**ABC** はテキストです。

	多くの変換を適用して、3 つの列だけで構成される異なる形の結果を得るようにします。**Power BI Desktop へのデータの読み込み**ラボで **Date**、**EmployeeKey**、**TargetAmount** の各列を使用します。

### **タスク 6: CSV ファイルから追加データを取得する**

このタスクでは、別の CSV ファイルに基づいて追加のクエリを作成します。

1. 前のタスクの手順を使用して、**D:\DA100\Resources\ColorFormats.csv** ファイルに基づいてクエリを作成します。

	![画像 75](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image39.png)

	**ColorFormats** CSV ファイルには、商品の色ごとに 1 行が含まれています。各行には、背景色とフォントの色を書式設定するための HEX コードが記録されます。**Power BI Desktop へのデータの読み込み**ラボでは、このデータを **DimProduct** クエリ データと統合します。

### **タスク 7: 仕上げ**

このタスクではラボを完了します。

1. 「**表示**」リボン タブの「**データ プレビュー**」グループ内から、次の 3 つのデータ プレビュー オプションをオフにします。

	- 列の品質

	- 列の分布

	- 列プロファイル

	![画像 76](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image40.png)

2. Power BI Desktop ファイルを保存するには、「**Power Query エディター**」ウィンドウの **ファイル** バックステージ ビューで「**保存**」を選択します。

	![画像 77](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image41.png)

3. クエリを適用するかどうかを確認するメッセージが表示されたら、「**後で適用する**」をクリックします。

	![画像 86](Linked_image_Files/01-prepare-data-with-power-query-in-power-bi-desktop_image42.png)

	クエリを適用すると、データがデータ モデルに読み込まれます。その前に、多くの変換を適用しなければならないため、これを行う準備はまだできていません。

4. 次のラボを開始する場合は、Power BI Desktop を開いたままにしておきます。

	**Power BI Desktop へのデータの読み込み**ラボでは、クエリにさまざまな変換を適用し、クエリを適用してデータ モデルに読み込みます。
