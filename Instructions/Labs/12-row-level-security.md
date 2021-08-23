---
lab:
    title: '行レベルのセキュリティを実行する'
    module: 'モジュール 13 - 行レベルのセキュリティ'
---


# **行レベルのセキュリティを実行する**

**このラボの推定所要時間: 45 分**

このラボでは **Salesperson** テーブルと **Sales** テーブルの間に多対多リレーションシップを作成します。また、営業担当者が確実に自分の担当地域の売上データだけを分析できるように、行レベルのセキュリティも適用します。

このラボでは次の作業を行う方法について説明します。

- 多対多リレーションシップを構成する

- 行レベルのセキュリティを実行する

### **ラボ ストーリー**

このラボは、データの準備からレポートやダッシュボードとしての発行までの完全なストーリーとして設計された一連のラボのうちの 1 つです。ラボは任意の順序で完了できます。ただし、複数のラボを行う場合は、最初の 10 のラボを次の順序で行うことをお勧めします。

1. Power BI Desktop でのデータの準備

2. Power BI Desktop へのデータの読み込み

3. Power BI Desktop でのデータのモデル化、パート 1

4. Power BI Desktop でのデータのモデル化、パート 2

5. Power BI Desktop で DAX 計算を作成する (パート 1)

6. Power BI Desktop で DAX 計算を作成する (パート 2)

7. Power BI Desktop でのレポートの設計、パート 1

8. Power BI Desktop でのレポートの設計、パート 2

9. Power BI ダッシュボードを作成する

10. Power BI Desktop におけるデータ分析の実施

11. Power BI でのページ分割されたレポートの作成

12. **行レベルのセキュリティを実行する**

## **演習 1: 行レベルのセキュリティを実行する**

この演習では、営業担当者が割り当てられた地域での売上のみを表示できるように、行レベルのセキュリティを適用します。

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

1. 「**開く**」ウィンドウで、**D:\DA100\Labs\row-level-security\Starter** フォルダーに移動します。

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

### **タスク 2: 行レベルのセキュリティを実行する**

このタスクでは、行レベルのセキュリティを適用して、営業担当者が割り当てられた地域での売上のみを表示できるようにします。

1. データ ビューに切り替えます。

	![画像 5701](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image20.png)

2. **フィールド** ウィンドウで、**Salesperson (Performance)** テーブルを選択します。

3. データを確認し、Michael Blythe (EmployeeKey 281) の UPN 値が **michael-blythe@adventureworks.com** であることを確認します。

	*Michael Blythe は 3 つの販売地域である米国北東部、米国中部、米国南東部に割り当てられていることを思い出してください。*

4. レポート ビューに切り替えます。

5. 「**モデリング**」リボン タブの「**セキュリティ**」グループの内から、「**ロールの管理**」をクリックします。

	![画像 5700](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image21.png)

6. 「**ロールの管理**」ウィンドウで、「**作成**」をクリックします。

	![画像 5702](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image22.png)

7. ボックスで、選択したテキストをロールの名前: **Salespeople** に置き換えてから、**Enter** キーを押します。

	![画像 5703](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image23.png)

8. フィルターを割り当てるには、**Salesperson (Performance)** テーブルの省略記号 (..) 文字をクリックし、「**フィルターの追加**」** | [UPN]** を選択します。

	![画像 5704](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image24.png)

9. 「**テーブル フィルター DAX 式**」ボックスで、**"Value"** を **USERPRINCIPALNAME()** に置き換えて式を変更します。

	![画像 11](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image25.png)

	*USERPRINCIPALNAME() は、認証されたユーザーの名前を返す Data Analysis Expressions (DAX) 関数です。つまり、**Salesperson (Performance)** テーブルは、モデルに対してクエリを実行するユーザーのユーザー プリンシパル名 (UPN) でフィルター処理されます。*

10. 「**保存**」をクリックします。

	![画像 5706](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image26.png)

11. セキュリティ ロールをテストするには、「**モデリング**」リボン タブの「**セキュリティ**」グループ内から、「**表示方法**」をクリックします。

	![画像 5708](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image27.png)

12. 「**ロールとして表示**」ウィンドウで、「**その他のユーザー**」項目をオンにし、対応するボックスに「**michael-blythe@adventureworks.com**」と入力します。

13. 「**営業担当者**」ロールを確認します。

	![画像 5709](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image28.png)

	*この構成では「**営業担当者**」ロールが使用され、Michael Blythe の名前を使用してなりすまします。*

14. 「**OK**」をクリックします。

	![画像 5710](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image29.png)

15. レポート ページの上に黄色のバナーが表示され、テスト セキュリティ コンテキストが説明されています。

	![画像 13](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image30.png)

16. テーブル ビジュアルでは、営業担当者の **Michael Blythe** のみがリストされていることに注目してください。

	![画像 5713](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image31.png)

17. テストを中止するには、黄色のバナーの右側にある「**表示を中止**」をクリックします。

	![画像 5712](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image32.png)

	*Power BI Desktop ファイルが Power BI サービスに発行されると、セキュリティ プリンシパルを「**営業担当者**」ロールにマップする発行後のタスクを完了する必要があります。これはこのラボでは行いません。*

18. ロールを削除するには、「**モデリング**」リボン タブの「**セキュリティ**」グループ内から、「**ロールの管理**」をクリックします。

	![画像 16](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image33.png)

19. 「**ロールの管理**」ウィンドウで、「**削除**」をクリックします。

	![画像 17](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image34.png)

20. 削除の確認を求められたら、「**はい、削除します**」をクリックします。

21. 「**保存**」をクリックします。

	![画像 18](Linked_image_Files/04-configure-data-model-in-power-bi-desktop-advanced_image35.png)

### **タスク 2: 仕上げ**

このタスクではラボを完了します。

1. Power BI Desktop ファイルを保存します。
