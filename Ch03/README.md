## Ch03 flex

---

#### 1.基本用法-排列方式

---

1. 創建外層與內層三個`div`做列表
    ```html
    <div id="out_block">
        <div class="item">項目一</div>
        <div class="item">項目二</div>
        <div class="item">項目三</div>
    </div>
    ```
2. 為內層的每個項目`div`增加框線
    ```css
    .item {
        border: 1px solid #ff0000;
    }
    ```
3. 將外層`div`添加`display`的`flex`屬性，並設定排列方式
    ```css
    #out_block {
        display: flex;

        /*(1)水平排列且不換行*/
        flex-direction: row;
        flex-wrap: nowrap;

        /*(2)垂直水平排列並反轉內容*/
        flex-direction: column-reverse;

        /*(3)水平排列並反轉內容，且超過寬度時自動換行*/
        width: 50px;
        flex-direction: row-reverse;
        flex-wrap: wrap;

        /*(4)使用flex-flow同時設定水平排列且不換行*/
        flex-flow: row nowrap
    }
    ```
>>>
備註說明：
* 以上例子使用了四種不同的排列設定方式，可試著個別註解查看差異。
* `flex`為`display`的屬性之一，有兩種可調用的屬性：
    * `flex`：會自動填滿頁面寬度。
    * `inline-flex`：會以內容調整寬度。
* `flex-direction`可控制排列方式，有以下幾種設定方式：
    * `row`：水平排列。
    * `row-reverse`：水平排列並反轉順序。
    * `column`：垂直排列。
    * `column-reverse`：垂直排列並反轉順序。
* `flex-wrap`可控制內層項目是否換行，有以下幾種設定方式：
    * `wrap`：超過寬度則將項目換行。
    * `wrap-reverse`：超過寬度則將項目換行，並反轉順序。
    * `nowrap`：不將項目換行。
* `flex-flow`可同時設定排列方式及是否換行，例如：
    * `row wrap`水平排列，且超過寬度換行。
>>>

下方程式碼為上方例子中的第四種排列方式。

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex01/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex01/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch03/ex01/index.html](https://gqsm.gitlab.io/csslayout/Ch03/ex01/index.html)

#### 2.基本用法-對齊方式1-單行對齊

---

1. 創建外層與內層三個`div`，並為他們設定不同高度做為列表
    ```html
    <div id="out_block">
        <div class="item" style="height:20px">項目一</div>
        <div class="item" style="height:100px">項目二</div>
        <div class="item" style="height:60px">項目三</div>
    </div>
    ```
2. 為內層的每個項目`div`增加框線
    ```css
    .item {
        border: 1px solid #ff0000;
    }
    ```
3. 將外層`div`添加`display`的`flex`屬性，並設定對齊方式
    ```css
    #out_block {
        display: flex;

        /*(1)垂直置中，水平分散對齊*/
        align-items: center;
        justify-content: space-around;

        /*(2)垂直置底，水平靠右對齊*/
        align-items: flex-end;
        justify-content: flex-end;

        /*(3)垂直自動填滿高度(需取消item高度設定)，水平置中對齊*/
        align-items: stretch;
        justify-content: center;
    }
    ```
>>>
備註說明：
* 以上例子使用了三種不同的排列設定方式，可試著個別註解查看差異。
* 以`align-items`設定垂直對齊，有以下幾種設定方式：
    * `flex-start`：將所有元素靠上對齊。
    * `center`：將所有元素置中。
    * `flex-end`：將所有元素靠底部對齊。
    * `stretch`：在沒設定`item`高度的情況下，會自動設定調大成外框高度。
* 以`justify-content`設定水平對齊，有以下幾種設定方式：
    * `flex-start`：將所有元素靠左對齊。
    * `center`：將所有元素置中。
    * `flex-end`：將所有元素靠右對齊。
    * `space-between`：平均分配所有元素的間隔距離。
    * `space-around`：平均分配所有元素的寬度。
>>>

下方程式碼為上方例子中的第三種排列方式。

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex02/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex02/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch03/ex02/index.html](https://gqsm.gitlab.io/csslayout/Ch03/ex02/index.html)

#### 3.基本用法-對齊方式2-多行對齊

---

1. 創建外層與內層多個`div`做為列表
    ```html
    <div id="out_block">
            <div class="item">項目一</div>
            <div class="item">項目二</div>
            <div class="item">項目三</div>
            <div class="item">項目四</div>
            <div class="item">項目五</div>
            <div class="item">項目六</div>
    </div>
    ```
2. 為內層的每個項目`div`增加框線
    ```css
    .item {
        border: 1px solid #ff0000;
    }
    ```
3. 為外層`div`設定寬高、邊框、`flex`使用水平排列，並讓子元素自動換行
    ```css
    #out_block {
        display: flex;
        flex-flow: row wrap;
        width: 100px;
        height: 300px;
        border: 1px solid #0000FF;
    }
    ```
4. 為外層`div`再添加多行的對齊方式
    ```css
    #out_block{
        /*省略上方設定屬性*/

        /*(1)置中對齊*/
        align-content: center;

        /*(2)平均分配各行高度*/
        align-content: space-around;
    }
    ```
>>>
備註說明：
* 以上例子使用了三種不同的排列設定方式，可試著個別註解查看差異。
* 以`align-content`設定多行的垂直對齊，有以下幾種設定方式：
    * `flex-start`：將所有元素靠上對齊。
    * `center`：將所有元素置中。
    * `flex-end`：將所有元素靠底部對齊。
    * `space-between`：平均分配各行的間隔距離。
    * `space-around`：平均分配各行的高度。
>>>

下方程式碼為上方例子中的第二種排列方式。

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex03/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex03/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch03/ex03/index.html](https://gqsm.gitlab.io/csslayout/Ch03/ex03/index.html)
