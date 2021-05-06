---
lab:
    title: 'Power BI Desktop でのデータのモデル化、パート 2'
    module: 'モジュール 4: Power BI でのデータ モデルの設計'
---

# **Power BI Desktop でのデータのモデル化、パート 2**

**このラボの推定所要時間: 45 分**

このラボでは **Salesperson** テーブルと **Sales** テーブルの間に多対多リレーションシップ を作成します。また、営業担当者が確実に自分の担当地域の売上データだけを分析できるように、行レベルのセキュリティも適用します。

このラボでは次の作業を行う方法について説明します。

- 多対多リレーションシップを構成する

### **ラボ ストーリー**

このラボは、データの準備からレポートやダッシュボードとしての発行までの完全なストーリーとして設計された一連のラボのうちの 1 つです。ラボは任意の順序で完了できます。ただし、複数のラボを行う場合は、最初の 10 のラボを次の順序で行うことをお勧めします。

1. Power BI Desktop でのデータの準備

2. Power BI Desktop へのデータの読み込み

3. Power BI Desktop でのデータのモデル化、パート 1

4. **Power BI Desktop でのデータのモデル化、パート 2**

5. Power BI Desktop での DAX 計算の作成、パート 1

6. Power BI Desktop での DAX 計算の作成、パート 2

7. Power BI Desktop でのレポートの設計、パート 1

8. Power BI Desktop でのレポートの設計、パート 2

9. Power BI ダッシュボードを作成する

11. Power BI でのページ分割されたレポートの作成

10. Power BI Desktop におけるデータ分析の実施

## **演習 1: 多対多のリレーションシップを作成する**

この演習では **Salesperson** テーブルと **Sales** テーブルの間に多対多リレーションシップ を作成します。

### **タスク 1: はじめに**

このタスクではこのラボ用の環境を設定します。

*重要: 前のラボから継続している (およびそのラボを完了している) 場合は、このタスクを完了しないで、次のタスクから続けてください。*

1. Power BI Desktop を開くには、タスク バーにある Microsoft Power BI Desktop のショートカットをクリックします。

 	![画像 8](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image1.png)

1. 「はじめに」ウィンドウを閉じるには、ウィンドウの左上にある「**X**」をクリックします。

 	![画像 7](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image2.png)

1. スターター Power BI Desktop ファイルを開くには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

1. 「**レポートを開く**」を選択します。

 	![画像 6](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image3.png)

1. 「**レポートを参照**」をクリックします。

 	![画像 5](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image4.png)

1. 「**開く**」ウィンドウで、**D:\DA100\Labs\04-configure-data-model-in-power-bi-desktop-advanced\Starter** フォルダーに移動します。

1. **Sales Analysis** ファイルを選択します。

1. 「**開く**」をクリックします。

 	![画像 4](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image5.png)

1. 開いている情報ウィンドウをすべて閉じます。

1. ファイルのコピーを作成するには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

1. 「**名前を付けて保存**」を選択します。

 	![画像 3](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image6.png)

1. 変更を適用するかどうかを確認するメッセージが表示されたら、「**適用**」をクリックします。

 	![画像 15](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image7.png)

1. 「**名前を付けて保存**」ウィンドウで、**D:\DA100\MySolution** フォルダーに移動します。

1. 「**保存**」をクリックします。

 	![画像 2](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image8.png)

### **タスク 2: 多対多リレーションシップを作成する**

このタスクでは **Salesperson** テーブルと **Sales** テーブルの間に多対多リレーションシップを作成します。

1. Power BI Desktop のレポート ビューの「**フィールド**」ウィンドウで、次の 2 つのフィールドを確認してテーブル ビジュアルを作成します。

	- Salesperson | Salesperson

	- Sales | Sales

	*ラボでは、フィールドを参照するために省略表記を使用します。次のようになります。**Salesperson | Salesperson**。この例では、**Salesperson** はテーブル名、**Salesperson** はフィールド名です。*

	![画像　1](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image9.png)

	*テーブルには、各営業担当者の売上が表示されます。しかし、営業担当者と営業の間には別のリレーションシップもあります。営業担当者により、担当する地域の数は 1 つ、2 つ、またはそれより多い可能性もあります。また、販売地域には複数の営業担当者を割り当てることができます。*

	*業績管理の観点からは、営業担当者の売上を (割り当てられた担当地域に基づいて) 分析し、販売目標と比較する必要があります。次の演習では、この分析をサポートするリレーションシップを作成します。*

2. Michael Blythe は約 900 万ドルを売り上げていることに注目してください。

3. モデル ビューに切り替えます。

	![画像 10](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image10.png)

4. **SalespersonRegion** テーブルをドラッグして、**Region** と **Salesperson** テーブルの間に配置します。

5. ドラッグ アンド ドロップ手法を使用して、次の 2 つのモデル リレーションシップを作成します。

	- **Salesperson | EmployeeKey** から **SalespersonRegion | EmployeeKey**

	- **Region | SalesTerritoryKey** から **SalespersonRegion | SalesTerritoryKey**

	***SalespersonRegion** テーブルは、ブリッジ テーブルと見なすことができます。*

6. レポート ビューに切り替えて、ビジュアルが更新されていない (Michael Blythe の売上結果が変更されていない) ことを確認します。

7. モデル ビューに戻り、**Salesperson** テーブルのリレーションシップ フィルターの方向 (矢印) に従います。

	***Salesperson** テーブルが **Sales** テーブルにフィルターを適用すると考えてください。また、**SalespersonRegion** テーブルにフィルターが適用されますが、**Region** テーブルには引き続き反映されていません (矢印が間違った方向を指しています)。*

	![画像 380](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image11.png)

8. **Region** テーブルと **SalespersonRegion** テーブルの間のリレーションシップを編集するには、リレーションシップをダブルクリックします。

9. 「**リレーションシップの編集**」 ウィンドウの 「**クロス フィルタの方向**」ドロップダウン リストで、「**両方**」 を選択します。

10. 「**両方向にセキュリティ フィルタを適用する**」 チェックボックスをオンにします。

	*この設定により、行レベルのセキュリティが適用されるときに双方向のフィルター処理が適用されます。次の演習では、セキュリティ ロールを構成します。*

	![画像 381](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image12.png)

11. 「**OK**」をクリックします。

	![画像 335](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image13.png)

12. リレーションシップの矢印の向きが両方になっていることにご注意ください。

	![画像 382](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image14.png)

13. レポート ビューに切り替えると、販売の値が依然として変更されていないことがわかります。

	*この問題は、**Salesperson** テーブルと **Sales** テーブルの間にフィルターを反映させるパスが 2 つあるという事実に関連しています。このあいまいさは、「テーブルの数が最も少ない」という評価観点に基づいて内部的に解決されます。明確にするために、このようなあいまいさを持つモデルを設計しないでください。この問題は、このラボの後半で部分的に解決され、**Power BI Desktop での DAX 計算の作成、パート 1** のラボを完了するまでに解決されます。*

14. モデル ビューに切り替えます。

15. ブリッジ テーブルを介してフィルターの伝達を強制するには、**Salesperson** テーブルと **Sales** テーブルのリレーションシップを編集 (ダブルクリック) します。

16. 「**リレーションシップの編集**」ウィンドウで、「**このリレーションシップをアクティブにする**」チェックボックスをオフにします。

	![画像 383](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image15.png)

17. 「**OK**」をクリックします。

	![画像 5696](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image16.png)

	*フィルターの伝達が、アクティブなパスのみに従うようになりました。*

18. 図で、非アクティブなリレーションシップは破線で表されていることにご注意ください。

	![画像 5697](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image17.png)

19. レポートビューに切り替えると、Michael Blythe の売り上げが 2,200 万ドル近くになっていることが分かるでしょう。

	![画像 5698](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image18.png)

20. また、各営業担当者の売上がテーブル合計を上回る場合もあります。

	*地域別の販売実績を二重、三重などにカウントするため、多対多のリレーションシップが一般的に観察されます。2 番目の営業担当者である Brian Welcker について考えてみましょう。彼の売上金額は合計売上金額と同じです。Brian Welcker は営業担当部長であるため、これは正しい結果です。Brian Welcker の売上は全地域の売上で測定されます。*

	*多対多リレーションシップは現在機能していますが、営業担当者による販売を分析することはできません (リレーションシップは非アクティブであるため)。**Power BI Desktop での DAX 計算の作成、パート 1** ラボで (彼らの地域の) パフォーマンス分析のために営業担当者を表す計算テーブルを導入すると、リレーションシップを再有効化できます。*

21. モデリング ビューに切り替え、ダイアグラム上で **Salesperson** テーブルを選択します。

22. 「**プロパティ**」ウィンドウの「**名前**」ボックスで 、テキストを **Salesperson (Performance)** に置き換えます。

	*名前を変更したテーブルには、その目的が反映されます。つまり、このテーブルを使用して、営業担当者が割り当てられた販売地域の売上に基づいて営業担当者の業績をレポートおよび分析します。*

### **タスク 3: Targets テーブルを関連付ける**

このタスクでは **Targets** テーブルにリレーションシップを作成します。

1. **Salesperson (Performance)** からリレーションシップを作成する **| EmployeeID** 列と **Targets | EmployeeID** 列。

2. レポート ビューで、テーブル ビジュアルに **Targets | Target** フィールドを追加します。

3. テーブル ビジュアルのサイズを変更し、すべての列が表示されるようにします。

	![画像 5699](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image19.png)

	*売上と目標を視覚化することが可能になりましたが、2 つの点において注意が必要です。第 1 に、期間に対するフィルターがないため、目標には将来の目標金額も含まれます。第 2 に、目標は加算できないため、合計が表示されないようにする必要があります。これらは、ビジュアルの書式設定を使用して無効にするか、計算ロジックを使用して削除できます。**Power BI Desktop での DAX 計算の作成、パート 2** ラボでは、目標メジャーを作成する 2 つ目のアプローチに従い、複数の営業担当者がフィルタリングされた場合に BLANK を返すようにします。*

### **タスク 4: 仕上げ**

このタスクではラボを完了します。

1. Power BI Desktop ファイルを保存します。

2. クエリを適用するかどうかを確認するメッセージが表示されたら、「**後で適用**」をクリックします。

3. 次のラボを開始する場合は、Power BI Desktop を開いたままにしておきます。

	***Power BI Desktop での DAX 計算の作成、パート 2** ラボでは、DAX を使用した計算によってデータ モデルを拡張します。*
