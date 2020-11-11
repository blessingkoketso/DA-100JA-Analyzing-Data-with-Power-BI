

### ラボ 02A

Power BI Desktop でのデータ準備

# 概要

**ラボを完了するための所要時間は 45 分です**

このラボでは、Adventure Works 社向けの Power BI Desktop ソリューションの開発を開始します。ソース データへの接続、データのプレビュー、そしてデータ プレビュー手法を使用したソース データの特性と品質を理解する作業が含まれます。

このラボでは、次の方法を学習します。

* Power BI Desktop を開く

* Power BI Desktop オプションの設定

* ソース データへの接続

* ソース データのプレビュー

* データ プレビュー手法を使用したデータへのよりよい理解

# 演習 1 : データの準備

このエクササイズでは、8 つの Power BI Desktop クエリを作成します。6 つのクエリは SQL Server からデータをソースし、2 つは CSV ファイルからデータをソースします。

### タスク 1 : Power BI Desktop ファイルを保存

このタスクではまず Power BI Desktop ファイルを保存します。

1. Power BI Desktop で、「**ファイル**」 リボン タブをクリックして、バックステージ ビューを開きます。

2. 「**保存**」 を選択します。

	![画像 13](Linked_image_Files/PowerBI_Lab02A_image1.png)

3. **名前を付けて保存** ウィンドウで、**D:\DA100\MySolution** フォルダーに移動します。

4. 「**ファイル名**」 ボックスに「**販売分析**」と入力します。

	![画像 14](Linked_image_Files/PowerBI_Lab02A_image2.png)

5. 「**保存**」 をクリックします。

	![画像 17](Linked_image_Files/PowerBI_Lab02A_image3.png)

	*ヒント : 右上にある 「**保存**」 アイコンをクリックしてファイルを保存することもできます*。

	![画像 18](Linked_image_Files/PowerBI_Lab02A_image4.png)

### タスク 2 : Power BI Desktop オプションの設定

このタスクでは、Power BI Desktop オプションを設定します。

1. Power BI Desktop で、「**ファイル**」 リボン タブをクリックして、バックステージ ビューを開きます。

2. 左側の 「**オプションと設定**」 を選択し、「**オプション**」 を選択します。

	![画像 1](Linked_image_Files/PowerBI_Lab02A_image5.png)

3. 左側にある 「**オプション**」 ウィンドウの 「**現在のファイル**」 グループで、「**データロード**」 を選択します。

	![画像 5](Linked_image_Files/PowerBI_Lab02A_image6.png)

	*現在のファイルの 「**データ ロード**」 設定では、モデリング時の既定の動作を決定する設定オプションを使用できます。*

4. 「**リレーションシップ**」 グループで、オンになっている 2 つのオプションをオフにします。

	![画像 7](Linked_image_Files/PowerBI_Lab02A_image7.png)

	*これらの 2 つのオプションは、データ モデルを開発する場合に役立ちますが、ラボ エクスペリエンスをサポートするために無効になっています。**ラボ 03A** でリレーションシップを作成すると、それぞれを追加する理由がわかります*。

5. 「**OK**」 をクリックします。

	![画像 9](Linked_image_Files/PowerBI_Lab02A_image8.png)

6. Power BI Desktop ファイルを保存します。

### タスク 3 : SQL Server からのデータの取得

このタスクでは、SQL Server テーブルに基づいてクエリを作成します。

1. 「**ホーム**」 リボン タブの 「**データ**」 グループ内から、「**SQL Server**」 をクリックします。

	![画像 19](Linked_image_Files/PowerBI_Lab02A_image9.png)

2. 「**SQL Server Database**」 ウィンドウの 「**サーバー**」 ボックスに、「**localhost**」と入力します。

	![画像 21](Linked_image_Files/PowerBI_Lab02A_image10.png)

	*ラボでは、**localhost** を使用して SQL サーバー データベースに接続します。ただし、独自のソリューションを作成する場合は、この方法はお勧めしません。これは、ゲートウェイ データソースが **localhost*** を解決できないためです。

3. 「**OK**」 をクリックします。

	![画像 22](Linked_image_Files/PowerBI_Lab02A_image11.png)

4. 既定の認証は、「**現在の資格情報を使用**」 であることに注意してください。

	![画像 23](Linked_image_Files/PowerBI_Lab02A_image12.png)

5. 「**接続**」 をクリックします。

	![画像 25](Linked_image_Files/PowerBI_Lab02A_image13.png)

6. 暗号化のサポートに関するメッセージが表示されたら、「**OK**」 をクリックします。

	![画像 27](Linked_image_Files/PowerBI_Lab02A_image14.png)

7. 「**ナビゲータ**」 ウィンドウの左側で、**AdventureWorksDW2020** データベースを展開します。

	***AdventureWorksDW2020** データベースは、 **AdventureWorksDW2017** サンプル データベースに基づいています。コース ラボの学習目標をサポートするように変更されました*。

	![画像 28](Linked_image_Files/PowerBI_Lab02A_image15.png)

8. 「**DimEmployee**」 テーブルを選択します (ただし、チェックはしません)。

	![画像 29](Linked_image_Files/PowerBI_Lab02A_image16.png)

9. 右側のペインで、テーブルのプレビューに注目します。

	*プレビューでは、列と行のサンプルを決定できます*。

10. クエリを作成するには、次の 6 つのテーブルを確認します。

	* DimEmployee

	* DimEmployeeSalesTerritory

	* DimProduct

	* DimReseller

	* DimSalesTerritory

	* FactResellerSales

11. 選択したテーブルのデータに変換を適用するには、「**データの変換**」 をクリックします。

	*このラボでは、データを変換しません。このラボの目的は、**Power Query Editor** ウィンドウでデータを調査し、プロファイリングすることです*。

	![画像 30](Linked_image_Files/PowerBI_Lab02A_image17.png)

### タスク 4: SQL Server クエリのプレビュー

このタスクでは、SQL Server クエリのデータをプレビューします。まず、データに関する関連情報を学習します。また、列の品質、列の分布、および列プロファイル ツールを使用してデータを理解し、データ品質を評価します。

1. **Power Query エディター** ウィンドウの左側に、**クエリ** ウィンドウがあります。

	![画像 31](Linked_image_Files/PowerBI_Lab02A_image18.png)

	*「**クエリ**」 ウィンドウには、選択した各テーブルに対して 1 つのクエリが含まれています*。

2. 最初のクエリを選択します - **DimEmployee**.

	![画像 33](Linked_image_Files/PowerBI_Lab02A_image19.png)

	***DimEmployee** テーブルには、従業員ごとに 1 行が格納されます。行のサブセットは、開発するモデルに関連する営業担当者を表します*。

3. 左下のステータス バーで、テーブルの統計情報があります。テーブルは 33 列、296 行あります。

	![画像 36](Linked_image_Files/PowerBI_Lab02A_image20.png)

4. データ プレビュー ウィンドウで、水平方向にスクロールしてすべての列を確認します。

5. 最後の 5 つの列に 「**テーブル**」 または 「**値**」 リンクが含まれていることに注意してください。

	*これらの 5 つの列は、データベース内の他のテーブルとのリレーションシップを表します。テーブルを結合するために使用できます。 **ラボ 03A*** のテーブルを結合します。

6. 列の品質を評価するには、「**表示**」 リボン タブの 「**データ プレビュー**」 グループ内から、「**列の品質**」 をオンにします。

	![画像 35](Linked_image_Files/PowerBI_Lab02A_image21.png)

	*列の品質を使用すると、有効な値、エラー値、または空の値の割合を簡単に判断できます*。

7. 「**Position**」 列 (最後の 6 列目) では、行の 94% が空 (null) であることに注意してください。

	![画像 38](Linked_image_Files/PowerBI_Lab02A_image22.png)

8. 列の分布を評価するには、「**表示**」 リボン タブの 「**データ プレビュー**」 グループ内から、「**列の分布**」 をオンにします。

	![画像 40](Linked_image_Files/PowerBI_Lab02A_image23.png)

9. 「**Position**」 列をもう一度確認し、4 つの別個の値と 1 つの一意の値があることを確認します。

10. **EmployeeKey** (第 1) 列の列の分布を確認します。296 の別個の値と 296 の一意の値があります。

	![画像 43](Linked_image_Files/PowerBI_Lab02A_image24.png)

	*別個の値のカウントと一意の値のカウントが同じ場合、列に一意の値が含まれていることを意味します。モデリングの際、一部のテーブルに一意の列を含めることが重要です。これらは、**ラボ 04A*** で行う一対多のリレーションシップを作成するために使用されます。

11. 「**クエリ**」 ウィンドウで、「**DimEmployeeSalesTerritory**」 クエリを選択します。

	![画像 44](Linked_image_Files/PowerBI_Lab02A_image25.png)

	***DimEmployeeSalesTerritory** テーブルには、各従業員および従業員が管理する販売地域ごとに 1 行が格納されます。このテーブルでは、1 人の従業員に対して多くの地域を関連付けをサポートします。一部の従業員は、1 つ、2 つ、またはそれ以上の地域を管理する可能性があります。このデータをモデル化する場合、**ラボ 05A*** で行う多対多リレーションシップを定義する必要があります。

12. **クエリ** ウィンドウで、**DimProduct** クエリを選択します。

	![画像 46](Linked_image_Files/PowerBI_Lab02A_image26.png)

	***DimProduct** テーブルには、会社が販売する商品ごとに 1 行が含まれています*。

13. 水平方向にスクロールして、最後の列を表示します。

14. **DimProductSubcategory** 列に注目してください。

	*次のラボでこのクエリに変換を追加する場合は、**DimProductSubcategory** 列を使用してテーブルを結合します*。

15. 「**クエリ**」 ウィンドウで、「**DimReseller**」 クエリを選択します。

	![画像 49](Linked_image_Files/PowerBI_Lab02A_image27.png)

	***DimReseller** テーブルには、リセラーごとに 1 行が含まれています。リセラーは、Adventure Works の製品を販売、流通、または価値を追加します*。

16. 列の値を表示するには、「**表示**」 リボン タブの 「**データ プレビュー**」 グループ内から、「**列プロファイル**」 をオンにします。

	![画像 41](Linked_image_Files/PowerBI_Lab02A_image28.png)

17. 「**BusinessType**」 列ヘッダーを選択します。

18. データ プレビュー ウィンドウの下に新しいウィンドウが開きます。

19. 列の統計と値の分布を確認します。

20. データ品質の問題に注意してください: warehouse に対して 2 つのラベルがあります (**Warehouse**、またスペルミスがあります **Ware House**)。

	![画像 51](Linked_image_Files/PowerBI_Lab02A_image29.png)

21. カーソルを 「**Ware House**」 バーの上に置くと、この値を持つ 5 つの行があることに注意してください。

	*次のラボでは、変換を適用して、これらの 5 つの行のラベルを変更します*。

22. 「**クエリ**」 ウィンドウで、「**DimSalesTerritory**」 を選択します。

	![画像 52](Linked_image_Files/PowerBI_Lab02A_image30.png)

	***DimSalesTerritory** テーブルには、**本社** (Corporate HQ) を含む、販売地域ごとに 1 行が含まれています。地域は国に割り当てられ、国はグループに割り当てられます。**ラボ 04A**では、地域、国、またはグループ レベルでの分析をサポートする階層を作成します*。

23. 「**クエリ**」 ウィンドウで、「**FactResellerSales**」 クエリを選択します。

	![画像 54](Linked_image_Files/PowerBI_Lab02A_image31.png)

	***FactResellerSales** テーブルには、販売注文明細行ごとに 1 行が含まれており、販売注文には 1 つまたは複数の明細行項目が含まれています*。

24. **TotalProductCost** 列の列の品質を確認し、行の 8% が空であることを確認します。 

	![画像 63](Linked_image_Files/PowerBI_Lab02A_image32.png)

	***TotalProductCost** 列の値の欠落は、データ品質の問題です。  この問題に対処するために、次のラボでは、**DimProduct** テーブルに格納されている商品標準コストを使用して、欠落値を埋めるための変換を適用します*。  

### タスク 5: CSV ファイルからデータを取得する

このタスクでは、CSV ファイルに基づいてクエリを作成します。

1. 新しいクエリを追加するには、「**Power Query エディター**」 ウィンドウの 「**ホーム**」 リボン タブにある 「**新しいクエリ**」 グループ内から、「**新しいソース**」 下向き矢印をクリックし、「**テキスト/CSV**」 を選択します。         

	![画像 70](Linked_image_Files/PowerBI_Lab02A_image33.png)

2. 「**開く**」 ウィンドウで、**D:\DA100\Data** フォルダーに移動し、 **ResellerSalesTargets.csv** ファイルを選択します。

3. 「**開く**」 をクリックします。

4. 「**ResellerSalesTargets.csv**」 ウィンドウで、データ プレビューに注目してください。 

5. 「**OK**」 をクリックします。

	![画像 71](Linked_image_Files/PowerBI_Lab02A_image34.png)

6. 「**クエリ**」 ウィンドウで、**ResellerSalesTargets** クエリが追加されていることに注目してください。   

	![画像 72](Linked_image_Files/PowerBI_Lab02A_image35.png)

	***ResellerSalesTargets** CSV ファイルには、1 年ごとの、営業担当者 1 人につき 1 行が含まれます。  各行には、12 か月の月間販売目標 (千単位で表されます) が記録されます。Adventure Works 社の事業年度は 7 月 1 日に始まります*。

7. 空の値を含む列がない点に注意してください。

	*月間販売目標がない場合は、代わりにハイフン文字が格納されます*。

8. 列名の左側にある各列ヘッダーのアイコンを確認します。

	![画像 74](Linked_image_Files/PowerBI_Lab02A_image36.png)

	*アイコンは列のデータ型を表します。**123** は整数、**ABC** はテキストです*。

	*次のラボでは、次の 3 つの列だけで構成される異なる形状の結果を得るために、多くの変換を適用します。**日付**、**従業員キー**、**ターゲット金額***。

### タスク 6: CSV ファイルから追加データを取得する

このタスクでは、別の CSV ファイルに基づいて追加のクエリを作成します。

1. 前のタスクの手順を使用して、**D:\DA100\Data**\**ColorFormats.csv** ファイルに基づいてクエリを作成します。

	![画像 75](Linked_image_Files/PowerBI_Lab02A_image37.png)

	***ColorFormats.csv** ファイルには、商品の色ごとに 1 行が含まれています。各行には、背景色とフォントの色を書式設定するための HEX コードが記録されます。次のラボでは、このデータを **DimProduct** クエリ データと統合します*。

### 仕上げ

このタスクでは、ラボを完了します。

1. 「**表示**」 リボン タブの 「**データ のプレビュー**」 グループ内から、次の 3 つのデータ プレビュー オプションをオフにします。

	* 列の品質

	* 列の分布

	* 列プロファイル

	![画像 76](Linked_image_Files/PowerBI_Lab02A_image38.png)

2. Power BI Desktop ファイルを保存するには、「**ファイル**」 のバックステージ ビューで 「**保存**」 を選択します。

	![画像 77](Linked_image_Files/PowerBI_Lab02A_image39.png)

3. クエリを適用するかどうかを確認するメッセージが表示されたら、「**後で適用する**」 をクリックします。

	![画像 86](Linked_image_Files/PowerBI_Lab02A_image40.png)

	*クエリを適用すると、データ モデルにデータが読み込まれます。最初に適用する必要がある変換が多く存在するので、これを行う準備ができていません*。

4. Power BI Desktop を開いたままにしておきます。

	*次のラボでは、クエリにさまざまな変換を適用してから、クエリを適用してデータ モデル に読み込みます*。
