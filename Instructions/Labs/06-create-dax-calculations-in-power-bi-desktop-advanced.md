---
lab:
    title: 'Power BI Desktop での DAX 計算の作成、パート 2'
    module: 'モジュール 5 - Power BI で DAX を使用してモデルを作成する'
---


# **Power BI Desktop での DAX 計算の作成、パート 2**

**このラボの推定所要時間: 45 分**

このラボでは、フィルター コンテキスト操作を含む DAX 式を使用してメジャーを作成します。

このラボでは次の作業を行う方法について説明します。

- CALCULATE() 関数を使用してフィルター コンテキストを操作する

- タイム インテリジェンス関数を使用する

### **ラボ ストーリー**

このラボは、データの準備からレポートやダッシュボードとしての発行までの完全なストーリーとして設計された一連のラボのうちの 1 つです。ラボは任意の順序で完了できます。ただし、複数のラボを行う場合は、最初の 10 のラボを次の順序で行うことをお勧めします。

1. Power BI Desktop でのデータの準備

2. Power BI Desktop へのデータの読み込み

3. Power BI Desktop でのデータのモデル化、パート 1

4. Power BI Desktop でのデータのモデル化、パート 2

5. Power BI Desktop での DAX 計算の作成、パート 1

6. **Power BI Desktop での DAX 計算の作成、パート 2**

7. Power BI Desktop でのレポートの設計、パート 1

8. Power BI Desktop でのレポートの設計、パート 2

9. Power BI ダッシュボードを作成する

10. Power BI でのページ分割されたレポートの作成

11. Power BI Desktop におけるデータ分析の実施

## **演習 1: フィルター コンテキストを操作する**

この演習では、フィルター コンテキスト操作を含む DAX 式を使用してメジャーを作成します。

### **タスク 1: はじめに**

このタスクではこのラボ用の環境を設定します。

*重要: 前のラボから継続している (およびそのラボを完了している) 場合は、このタスクを完了しないで、次のタスクから続けてください。*

1. Power BI Desktop を開くには、タスク バーにある Microsoft Power BI Desktop のショートカットをクリックします。

    ![画像 12](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image1.png)

1. 「はじめに」ウィンドウを閉じるには、ウィンドウの左上にある「**X**」をクリックします。

    ![画像 11](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image2.png)

1. スターター Power BI Desktop ファイルを開くには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

1. 「**レポートを開く**」を選択します。

    ![画像 10](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image3.png)

1. 「**レポートを参照**」をクリックします。

    ![画像 9](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image4.png)

1. 「**開く**」ウィンドウで、**D:\DA100\Labs\06-create-dax-calculations-in-power-bi-desktop-advanced\Starter** フォルダーに移動します。

1. **Sales Analysis** ファイルを選択します。

1. 「**開く**」をクリックします。

    ![画像 8](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image5.png)

1. 開いている情報ウィンドウをすべて閉じます。

1. ファイルのコピーを作成するには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

1. 「**名前を付けて保存**」を選択します。

    ![画像 7](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image6.png)

1. 変更を適用するかどうかを確認するメッセージが表示されたら、「**適用**」をクリックします。

    ![画像 6](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image7.png)

1. 「**名前を付けて保存**」ウィンドウで、**D:\DA100\MySolution** フォルダーに移動します。

1. 「**保存**」をクリックします。

    ![画像 2](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image8.png)

### **タスク 2: マトリックス ビジュアルを作成する**

このタスクでは、新しいメジャーのテストをサポートするマトリックス ビジュアルを作成します。

1. Power BI Desktop のレポート ビューで、新しいレポート ページを作成します。

    ![画像　1](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image9.png)

2. 「**ページ 3**」で、マトリックス ビジュアルを追加します。

    ![画像 13](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image10.png)

3. ページ全体に合わせてマトリックス ビジュアルのサイズを変更します。

4. マトリックスのビジュアル フィールドを構成するには、「**フィールド**」 ウィンドウから 「**リージョン**」 をドラッグします **| リージョン** 階層を作成し、ビジュアル内にドロップします。

    *ラボでは、フィールドまたは階層を参照するために省略表記を使用します。次のようになります。 **Region | Regions**。この例では、**Region** はテーブル名、**Regions** は階層名です。*

5. 「**Sales | Sales**」フィールドも追加します。

6. 階層全体を展開するには、マトリックス ビジュアルの右上にある 2 つに分かれた矢印アイコンを 2 回クリックします。

    ![画像 47](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image11.png)

    ***Regions** 階層には **グループ**、**国** および **地域**のレベルがあることを思い出すかもしれません。*

7. ビジュアルを書式設定するには、「**視覚化**」ウィンドウの下にある「**書式設定**」ウィンドウを選択します。

    ![画像 14](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image12.png)

8. 「**検索**」ボックスに、「**階段状**」と入力します。

    ![画像 15](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image13.png)

9. 「**階段状レイアウト**」プロパティを「**オフ**」に設定します。

    ![画像 49](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image14.png)

10. マトリックス ビジュアルに 4 つの列ヘッダーができたことを確認します。

    ![画像 50](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image15.png)

    *Adventure Works では、販売地域はグループ、国、地域に分類されます。米国を除くすべての国には、国にちなんで名付けられた 1 つの地域があります。米国は非常に大きな販売地域であるため、5 つの販売地域に分かれています。*

    *この演習ではいくつかのメジャーを作成し、マトリックス ビジュアルに追加してテストします。*

### **タスク 3: フィルター コンテキストを操作する**

このタスクでは、CALCULATE() 関数を使用してフィルター コンテキストを操作する DAX 式を使用して、いくつかのメジャーを作成します。

1. 次の式に基づいて、**Sales** テーブルにメジャーを追加します。

    *利便性のために、このラボのすべての DAX 定義は、**D:\DA100\Labs\06-create-dax-calculations-in-power-bi-desktop-advanced\Assets\Snippets.txt** ファイルからコピーできます。*


    **DAX**


    ```
    Sales All Region =

    CALCULATE(SUM(Sales[Sales]), REMOVEFILTERS(Region))
    ```


    *CALCULATE() 関数は、フィルター コンテキストを操作するために使用される強力な関数です。最初の引数では、式またはメジャーを受け取ります (メジャーは単に名前付きの式です)。後続の引数では、フィルター コンテキストを変更できます。*

    *REMOVEFILTERS() 関数は、アクティブなフィルターを削除します。引数を受け取らないか、テーブル、列、または複数の列を引数として使用できます。*

    *この数式では、メジャーは、変更されたフィルター コンテキストの **Sales** 列の合計を評価します。これにより、**Region** テーブルの列に適用されているフィルターがすべて削除されます。*

2. 「**Sales All Region**」メジャーをマトリックス ビジュアルに追加します。

    ![画像 52](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image16.png)

3. 「**Sales All Region**」メジャーでは、地域、国 (小計) およびグループ (小計) ごとの地域販売の合計が計算されます。

    *新しいメジャーはまだ有用な結果を提供していません。グループ、国、または地域の販売をこの値で割ると、「総計の割合」と呼ばれる有用な比率が生成されます。*

4. 「**フィールド**」ウィンドウで、「**Sales All Region**」メジャーが選択されていることを確認し (選択すると、背景は濃い灰色になります)、数式バーでメジャー名と数式を次の数式に置き換えます。

    *ヒント: 既存の数式を置き換えるには、まずスニペットをコピーします。次に、数式バーの内側をクリックし、**Ctrl+A** キーを押してすべてのテキストを選択します。次に、**Ctrl キーを押しながら V キー** を押してスニペットを貼り付け、選択したテキストを上書きします。次に、**ENTER** キーを押します。*


    **DAX**


    ```
    Sales % All Region =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region)  
    ‎ )  
    ‎)
    ```


    *更新された数式の内容を正確に反映するように、メジャーの名前が変更されました。DIVIDE() 関数は、**Sales**テーブルに適用されたフィルターを削除する変更されたコンテキストで、「**Sales**」メジャー (フィルター コンテキストによって変更されていない) を「**Sales**」メジャーで除算します。*

5. マトリックス ビジュアルで、メジャーの名前が変更され、グループ、国、および地域ごとに異なる値が表示されるようになったことがわかります。

6. 「**Sales % All Region**」メジャーを、小数点以下 2 桁の割合として書式設定します。

7. マトリックス ビジュアルで、「**Sales % All Region**」メジャー値を確認します。

    ![画像 53](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image17.png)

8. 次の式に基づいて **Sales** テーブルに別のメジャーを追加し、パーセンテージとして書式を設定します。


    **DAX**

    ```
    Sales % Country =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region[Region])  
    ‎ )  
    ‎)
    ```


9. 「**Sales % Country**」メジャーの計算式は、「**Sales % All Region**」メジャーの計算式とは若干異なっていることに注意してください。

    *違いは、分母が **Region** テーブルのすべての列ではなく、**Region**テーブルの **Region** 列のフィルターを削除することによって、フィルター コンテキストを変更することです。これは、グループまたは国の列に適用されているすべてのフィルターが保持されることを意味します。売上高を国の割合として表す結果を達成します。*

10. マトリックス ビジュアルに「**Sales % Country**」メジャーを追加します。

11. 米国の地域のみが 100% ではない値を生成することがわかります。

    ![画像 54](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image18.png)

    *米国だけに複数の地域があることを思い出すかもしれません。他の国はすべて 1 つの地域を構成しているので、すべて 100% である理由を説明できます。*

12. このメジャーを視覚的に読みやすくするには、 この改善された式で「**Sales % Country**」メジャーを上書きします。


    **DAX**


    ```
    Sales % Country =  
    ‎IF(  
    ‎ ISINSCOPE(Region[Region]),  
    ‎ DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(Region[Region])  
    ‎ )  
    ‎ )  
    ‎)
    ```


    *IF() 関数内に埋め込まれた ISINSCOPE() 関数は、Region 列がレベル階層のレベルであるかどうかをテストするために使用されます。true の場合、DIVIDE() 関数が評価されます。false の部分がないため、Region 列がスコープ内にない場合は空白が返されます。*

13. 「**Sales % Country**」 メジャーでは、リージョンがスコープ内にある場合にのみ値を返すことがわかります。

    ![画像 55](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image19.png)

14. 次の式に基づいて **Sales** テーブルに別のメジャーを追加し、パーセンテージとして書式を設定します。


    **DAX**


    ```
    Sales % Group =  
    ‎DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(  
    ‎ Region[Region],  
    ‎ Region[Country]  
    ‎ )  
    ‎ )  
    ‎)
    ```


    *グループの割合としての売上を得るために、2 つのフィルターを適用して、2 つの列に対するフィルターを効果的に削除できます。*

15. **Sales % Group** メジャーをマトリックス ビジュアルに追加します。

16. このメジャーの視覚的な可読性を向上させるには、この改良された式で **ales % Group** メジャーを上書きします。


    **DAX**


    ```
    Sales % Group =  
    ‎IF(  
    ‎ ISINSCOPE(Region[Region])  
    ‎ || ISINSCOPE(Region[Country]),  
    ‎ DIVIDE(  
    ‎ SUM(Sales[Sales]),  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ REMOVEFILTERS(  
    ‎ Region[Region],  
    ‎ Region[Country]  
    ‎ )  
    ‎ )  
    ‎ )  
    ‎)
    ```


17. 「**Sales % Group**」メジャーでは、地域または国がスコープ内にある場合にのみ値が返されます。

18. モデル ビューで、3 つの新しいメジャーを「**比率**」という名前の表示フォルダーに配置します。

    ![画像 56](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image20.png)

19. Power BI Desktop ファイルを保存します。

    ***Sales** テーブルに追加されたメジャー は、階層ナビゲーションを実現するためにフィルター コンテキストを変更しました。小計の計算を実現するためのパターンでは、フィルター コンテキストから一部の列を削除する必要があり、総計を得るためにはすべての列を削除する必要があることを確認してください。*

## **演習 2: タイム インテリジェンスを使用する**

この演習では、年度累計 (YTD) メジャーと売上の前年比 (YoY) 成長メジャーを作成します。

### **タスク 1: YTD メジャーを作成する**

このタスクでは、売上の YTD メジャーを作成します。

1. レポート ビューの「**ページ 2**」で、行にグループ化された年と月を含むさまざまなメジャーを表示するマトリックス ビジュアルに注目します。

2. 次の式に基づいて、**Sales** テーブルにメジャーを追加し、小数点以下の桁数が 0 に設定されます。


    **DAX**


    ```
    Sales YTD =  
    ‎TOTALYTD(SUM(Sales[Sales]), 'Date'[Date], "6-30")
    ```


    *TOTALYTD() 関数は、指定した日付列に対する式 (この場合は **Sales** 列の合計) を評価します。日付列は、**Power BI Desktop での DAX 計算の作成、パート 1** ラボで行ったように、日付テーブルとしてマークされた Date テーブルに属している必要があります。*

    *この関数には、年度の最後の日付を表す、省略可能な 3 番目の引数を指定することもできます。この日付を指定しない場合は、12 月 31 日が年度の最後の日付になります。Adventure Works では、6 月が年度の最後の月なので、「6-30」 が使用されます。*

3. マトリックス ビジュアルに「**Sales**」フィールドと「**Sales YTD**」メジャーを追加します。

4. 年内の売上の値が累積されていることがわかります。

    ![画像 59](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image21.png)

    *TOTALYTD() 関数によって、フィルター操作 (具体的には、時間フィルター操作) が実行されます。たとえば、2017 年 9 月 (会計年度の 3 番目の月) の YTD の売上を計算するには、「**日付**」 テーブルのすべてのフィルターが削除され、年の初め (2017 年 7 月 1 日) から開始する日付の新しいフィルターに置き換えられ、コンテキスト内の日付期間 (2017 年 9 月 30 日) まで延長されます。*

    *一般的な時間フィルター操作をサポートするために、DAX では多くのタイム インテリジェンス関数が利用できることに注意してください。*

### **タスク 2: 「YoY Growth」メジャーを作成する**

このタスクでは、売上の YoY 成長メジャーを作成します。

1. 次の式に基づいて、**Sales** テーブルにメジャーを追加します。


    **DAX**


    ```
    Sales YoY Growth =  
    ‎VAR SalesPriorYear =  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ PARALLELPERIOD(  
    ‎ 'Date'[Date],  
    ‎ -12,  
    ‎ MONTH  
    ‎ )  
    ‎ )  
    ‎RETURN  
    ‎ SalesPriorYear
    ```


    *「**Sales YoY Growth**」メジャーの式は、変数を宣言します。変数を使用すると、数式のロジックを簡略化できる場合があります。また、数式内で式を複数回評価する必要がある場合に効率性が向上します (YoY 成長のロジックではこれが該当します)。変数は一意の名前で宣言され、メジャー式は **RETURN** キーワードの後に出力される必要があります。*

    *「**SalesPriorYear**」変数には、PARALLELPERIOD() 関数を使用してフィルター コンテキストの各日付から 12 か月前に移動する変更されたコンテキストの **Sales** 列の合計を計算する式が割り当てられます。*

2. 「**Sales YoY Growth**」メジャーをマトリックス ビジュアルに追加します。

3. 新しいメジャーは、最初の 12 か月間は空白を返します (会計年度の 2017 年以前には売上が記録されていないため)。

4. **2018 年 7 月**の「**Sales YoY Growth**」メジャー値が **2017 年 7 月**の「**Sales**」値であることに注意してください。

    ![画像 61](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image22.png)

    *これで数式の 「難しい部分」 をテストできたので、成長の結果を計算する最終的な数式で、メジャーを上書きすることができます。*

5. メジャーを完了するために、「**Sales YoY Growth**」メジャーをこの数式で上書きし、小数点以下 2 桁の割合として書式設定します。


    **DAX**


    ```
    Sales YoY Growth =  
    ‎VAR SalesPriorYear =  
    ‎ CALCULATE(  
    ‎ SUM(Sales[Sales]),  
    ‎ PARALLELPERIOD(  
    ‎ 'Date'[Date],  
    ‎ -12,  
    ‎ MONTH  
    ‎ )  
    ‎ )  
    ‎RETURN  
    ‎ DIVIDE(  
    ‎ (SUM(Sales[Sales]) - SalesPriorYear),  
    ‎ SalesPriorYear  
    ‎ )
    ```


6. 式の **RETURN** 句では、変数が 2 回参照されていることに注意してください。

7. **2018 年 7 月**の YoY の成長率が **392.83%** であることを確認します。

    ![画像 62](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image23.png)

    *つまり、2018 年 7 月の売上高 (2,411,559 ドル) は、前年同期の売上高 (489,328 ドル) から 400% 近く (ほぼ4倍) 改善したことになります。*

8. モデル ビューで、2 つの新しいメジャーを「**Time Intelligence**」という名前の表示フォルダに配置します。

    ![画像 63](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image24.png)

### **タスク 3: 仕上げ**

このタスクではラボを完了します。

1. レポート作成用にソリューションをクリーン アップするには、左下の「**ページ 2**」タブを右クリックし、ページの「**削除**」を選択します。

    ![画像 17](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image25.png)

2. ページを削除するかどうかを確認するメッセージが表示されたら、「**削除**」をクリックします。

    ![画像 18](Linked_image_Files/06-create-dax-calculations-in-power-bi-desktop-advanced_image26.png)

3. 「**ページ 3**」も削除します。

4. 残りのページで、ページをクリアするには、テーブル ビジュアルを選択し、**Delete** キーを押します。

5. Power BI Desktop ファイルを保存します。

6. 次のラボを開始する場合は、Power BI Desktop を開いたままにしておきます。

    ***Power BI Desktop でのレポートの設計、パート 1** ラボでは、データ モデルに基づいてレポートを作成します。*
