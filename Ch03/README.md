## Ch03 flex

---

#### 1.基本用法-排列方式

---

1. 創建外層與內層三個 `div` 做列表
    ```html
    <div id="out_block">
        <div class="item">項目一</div>
        <div class="item">項目二</div>
        <div class="item">項目三</div>
    </div>
    ```
2. 為內層的每個項目 `div` 增加框線
    ```css
    .item {
        border: 1px solid #ff0000;
    }
    ```
3. 將外層 `div` 添加 `display` 的 `flex` 屬性，並設定排列方式
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
* `flex` 為 `display` 的屬性之一，有兩種可調用的屬性：
    *  `flex` ：會自動填滿頁面寬度。
    *  `inline-flex` ：會以內容調整寬度。
*  `flex-direction` 可控制排列方式，有以下幾種設定方式：
    *  `row` ：水平排列。
    *  `row-reverse` ：水平排列並反轉順序。
    *  `column` ：垂直排列。
    *  `column-reverse` ：垂直排列並反轉順序。
*  `flex-wrap` 可控制內層項目是否換行，有以下幾種設定方式：
    *  `wrap` ：超過寬度則將項目換行。
    *  `wrap-reverse` ：超過寬度則將項目換行，並反轉順序。
    *  `nowrap` ：不將項目換行。
*  `flex-flow` 可同時設定排列方式及是否換行，例如：
    *  `row wrap` 水平排列，且超過寬度換行。
>>>

下方程式碼為上方例子中的第四種排列方式。

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex01/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex01/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch03/ex01/index.html](https://gqsm.gitlab.io/csslayout/Ch03/ex01/index.html)

#### 2.基本用法-對齊方式1-單行對齊

---

1. 創建外層與內層三個 `div` ，並為他們設定不同高度做為列表
    ```html
    <div id="out_block">
        <div class="item" style="height:20px">項目一</div>
        <div class="item" style="height:100px">項目二</div>
        <div class="item" style="height:60px">項目三</div>
    </div>
    ```
2. 為內層的每個項目 `div` 增加框線
    ```css
    .item {
        border: 1px solid #ff0000;
    }
    ```
3. 將外層 `div` 添加 `display` 的 `flex` 屬性，並設定對齊方式
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
* 以 `align-items` 設定垂直對齊，有以下幾種設定方式：
    *  `flex-start` ：將所有元素靠上對齊。
    *  `center` ：將所有元素置中。
    *  `flex-end` ：將所有元素靠底部對齊。
    *  `stretch` ：在沒設定 `item` 高度的情況下，會自動設定調大成外框高度。
* 以 `justify-content` 設定水平對齊，有以下幾種設定方式：
    *  `flex-start` ：將所有元素靠左對齊。
    *  `center` ：將所有元素置中。
    *  `flex-end` ：將所有元素靠右對齊。
    *  `space-between` ：平均分配所有元素的間隔距離。
    *  `space-around` ：平均分配所有元素的寬度。
>>>

下方程式碼為上方例子中的第三種排列方式。

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex02/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex02/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch03/ex02/index.html](https://gqsm.gitlab.io/csslayout/Ch03/ex02/index.html)

#### 3.基本用法-對齊方式2-多行對齊

---

1. 創建外層與內層多個 `div` 做為列表
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
2. 為內層的每個項目 `div` 增加框線
    ```css
    .item {
        border: 1px solid #ff0000;
    }
    ```
3. 為外層 `div` 設定寬高、邊框、 `flex` 使用水平排列，並讓子元素自動換行
    ```css
    #out_block {
        display: flex;
        flex-flow: row wrap;
        width: 100px;
        height: 300px;
        border: 1px solid #0000FF;
    }
    ```
4. 為外層 `div` 再添加多行的對齊方式
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
* 以 `align-content` 設定多行的垂直對齊，有以下幾種設定方式：
    *  `flex-start` ：將所有元素靠上對齊。
    *  `center` ：將所有元素置中。
    *  `flex-end` ：將所有元素靠底部對齊。
    *  `space-between` ：平均分配各行的間隔距離。
    *  `space-around` ：平均分配各行的高度。
>>>

下方程式碼為上方例子中的第二種排列方式。

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex03/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex03/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch03/ex03/index.html](https://gqsm.gitlab.io/csslayout/Ch03/ex03/index.html)

#### 4.基本用法-內層區塊設定

---

1. 創建外層與內層三個 `div` 做列表
    ```html
    <div id="out_block">
        <div class="item">項目一</div>
        <div class="item">項目二</div>
        <div class="item">項目三</div>
    </div>
    ```
2. 替外層 `div` 增加寬高、框線和 `flex` 屬性
    ```css
    #out_block {
        display: flex;
        width: 600px;
        height: 300px;
        border: 1px solid #0000FF;
    }
    ```
3. 為內層的每個項目 `div` 個別設定背景顏色
    ```css
    .item:nth-child(1) {
        background-color: #00ff00;
    }
    .item:nth-child(2) {
        background-color: #0000ff;
    }
    .item:nth-child(3) {
        background-color: #ff0000;
    }
    ```
>>>
備註說明：
1. `:nth-child(i)` 為 `CSS3` 中的新屬性。能夠指定第 `i` 個符合的元素增加 `CSS` 樣式。
>>>
4. 替內層 `div` 用 `flex-basis` 寬度 100px ，並增加 `flex-grow` 屬性。
    ```css
    .item {
        flex-basis :100px;
        flex-grow :1;
    }
    ```
>>>
備註說明：
1. 在 `flex` 的 `div` 下寬度 `width` 與 `flex-basis` 同時存在時會以 `flex-basis` 優先。
2. `flex-grow` 會在元素的寬度無法填滿 `div` 時，按比例填滿剩餘區塊。
>>>
5. 可將 `flex-grow` 個別設置在內層元素上，以查看差別
    ```css
    .item:nth-child(1) {
        background-color: #00ff00;
        flex-grow: 1;
    }
    .item:nth-child(2) {
        background-color: #0000ff;
        flex-grow: 2;
    }
    .item:nth-child(3) {
        background-color: #ff0000;
        flex-grow: 3;
    }
    ```
>>>
備註說明：
1. `flex-grow` 是填滿區塊，相反的屬性是 `flex-shrink` 他會在寬度超過外層區塊時，自動收縮成區塊大小，比例設置的越大，會被縮放得越多。
>>>

下方程式碼為使用與 `flex-grow` 相反的 `flex-shrink` 。

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex04/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex04/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch03/ex04/index.html](https://gqsm.gitlab.io/csslayout/Ch03/ex04/index.html)

#### 5.滑動展開列表

---

1. 創建外層與內層三個 `div` 做列表
    ```html
    <div id="out_block">
        <div class="item">項目一</div>
        <div class="item">項目二</div>
        <div class="item">項目三</div>
    </div>
    ```
2. 替外層 `div` 增加寬高、框線和 `flex` 屬性
    ```css
    #out_block {
        display: flex;
        width: 600px;
        height: 300px;
        border: 1px solid #0000FF;
    }
    ```
3. 為內層的每個項目 `div` 個別設定背景顏色
    ```css
    .item:nth-child(1) {
        background-color: #00ff00;
    }
    .item:nth-child(2) {
        background-color: #0000ff;
    }
    .item:nth-child(3) {
        background-color: #ff0000;
    }
    ```
4. 在內層 `div` 用 `flex` 同時設定 `flex-basis` 寬度及 `flex-grow` 延展比例。
    ```css
    .item {
        flex :1 0 50px;
    }
    ```
>>>
備註說明：
* `flex` 擁有三個值
    * 第一個為 `flex-grow`
    * 第二個為 `flex-shrink`
    * 第三個為 `flex-basis` 
>>>
5. 用 `hover` 設定當滑鼠移到 `item` 上時，將寬度增加至 500px 
    ```css
    .item:hover {
        flex-basis: 500px;
    }
    ```
6. 在寬度變動時，使用 `transition` 添加過場動畫
    ```css
    .item {
        flex: 1 0 50px;
        transition: flex-basis 0.5s;
    }

    .item:hover {
        flex-basis: 500px;
        transition: flex-basis 0.5s;
    }
    ```
>>>
備註說明：
*  `transition` 帶有兩個參數
    * 第一個為產生變化效果的屬性。
    * 第二個為動畫時間。
>>>

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex05/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch03/ex05/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch03/ex05/index.html](https://gqsm.gitlab.io/csslayout/Ch03/ex05/index.html)
