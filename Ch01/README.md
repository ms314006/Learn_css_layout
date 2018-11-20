## Ch01 float

---

#### 1.文繞圖

---

1. 創建外層與內層兩個 `div`
    ```html
    <div id="out_block">
        <div id="in_block_left">
            float:left
        </div>
        <div id="in_block_right">
            float:right
        </div>
        <!--增加文字-->
    </div>
    ```
2. 為外層 `div` 增加寬高及背景顏色
    ```css
    #out_block{
        width:100%;
       height:200px;
        background-color:#061d5e;
    }
    ```
3. 為內層 `div` 設定 `float`
    ```css
    #in_block_left{
        width:100px;
        height:100px;
        float: left;
        margin:15px;
        background-color:#ffffff; 
    }

    #in_block_right{
        width:100px;
        height:100px;
        float: right;
        margin:15px;
        background-color:#ffffff; 
    }
    ```

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex01/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex01/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch01/ex01/index.html](https://gqsm.gitlab.io/csslayout/Ch01/ex01/index.html)


#### 2.水平排列列表

---

1. 在外層 `div` 內創建幾個用 `div` 裝著的重複的列表
    ```html
    <div id="list_block">
        <div class="list list1">
        </div>
        <div class="list list2">
        </div>
        <div class="list list3">
        </div>
    </div>
    ```
2. 為內層 `div` 設定 `float:left` 靠左排列
    ```css
    #list_block .list {
        width: 100px;
        height: 100px;
        float: left;
        margin: 15px;
    }
    ```
3. 為每個 `list1` 設定不同背景顏色
    ```css
    .list1 {
        background-color: #0025fa;
    }
    .list2 {
        background-color: #09b909;
    }
    .list3 {
        background-color: #fa0015;
    }
    ```

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex02/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex02/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch01/ex02/index.html](https://gqsm.gitlab.io/csslayout/Ch01/ex02/index.html)

#### 3.選單

---

1. 建立一個 `nav` 區塊，並使用 `ul` 及 `li` 製作列表
    ```html
    <nav>
        <a hred="#">選單</a>
        <ul>
            <li><a href="#">首頁</a></li>
            <li><a href="#">關於我們</a></li>
            <li><a href="#">歷史沿革</a></li>
            <li><a href="#">聯絡我們</a></li>
        </ul>
    </nav>
    ```
2. 把選單內部的 `li` 使用 `float` 向左浮動，並用 `margin` 取左邊間隔及取消標記符號
    ```css
    nav ul li{
        float:left;
        margin-right:20px;
        list-style-type:none;
    }
    ```
3. 選單外部的 `ul` 使用 `float` 向右浮動
    ```css
    nav ul{
        float:right;
    }
    ```
4. 將所有 `a` 標籤的底線拿掉
    ```css
    a{
        text-decoration:none;
    }
    ```

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex03/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex03/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch01/ex03/index.html](https://gqsm.gitlab.io/csslayout/Ch01/ex03/index.html)

## 下方為因設置 `float` 導致外層 `div` 跑版可使用之解決方式，可依需求做使用

---

#### 4.搭配 `overflow` 的 `hidden` 使用
1. 創建外層和內層的 `div`
    ```html
    <div id="out_block">
        <div id="in_block">
        </div>
    </div>
    ```
2. 將外層 `div` 設定背景顏色、 `overflow` 及內間距
    ```css
    #out_block{
        background-color:#000000;
        padding:10px;
        overflow:hidden;
    }
    ```
3. 將內層 `div` 設定 `float` 和寬高及白色背景
    ```css
    #in_block{
        float:left;
        width:100px;
        height:100px;
        background-color:#ffffff;
    }
    ```
>>>
備註說明：
* `overflow` 的 `hidden` 值可以讓外層 `div` 依照內層 `div` 調整高度，即使他有 `float` 屬性。
* 可試著將 `overflow` 屬性拿掉看差別。
>>>

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex04/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex04/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch01/ex04/index.html](https://gqsm.gitlab.io/csslayout/Ch01/ex04/index.html)

#### 5.搭配 `clear` 的 `both` 使用
1. 創建外層和兩個內層 `div`
    ```html
    <div id="out_block">
        <div id="in_block"></div>
        <div id="clearfix"></div>
    </div>
    ```
2. 為外層 `div` 增加背景顏色和 `padding`
    ```css
    #out_block{
        padding:15px;
        background-color:#000000;
    }
    ```
3. 為第一個 `div` 增加背景顏色、寬高及 `float`
    ```css
    #in_block{
        float:left;
        width:100px;
        height:100px;
        background-color:#ffffff;
    }
    ```
4. 為第二個 `div` 增加背景顏色、寬高及 `clear`
    ```css
    #clearfix{
        clear:both;
        width:400px;
        height:500px;
        background-color:#ff0000;
    }
    ```

>>>
備註說明：
* `clear` 的 `both` 可讓該 `div` 不受其他 `float` 的 `div` 影響。
* 可試著將 `clear` 屬性拿掉看差別。
>>>

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex05/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex05/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch01/ex05/index.html](https://gqsm.gitlab.io/csslayout/Ch01/ex05/index.html)

#### 6. 搭配 `display` 的 `table` 使用
1. 創建內外層 `div`
    ```html
    <div id="out_block">
        <div id="in_block">
        </div>
    </div>
    ```
2. 為內層 `div` 設定 `float` 和寬高、背景顏色
    ```css
    #in_block{
        float:left;
        width:100px;
        height:100px;
        background-color:#ffffff;
    }
    ```
3. 為外層 `div` 設定 `display` 、背景顏色及內邊距
    ```css
    #out_block{
        display:table;
        padding:10px;
        background-color:#000000;
    }
    ```
>>>
備註說明
* 藉由 `display` 屬性的 `table` 值可讓外層的 `div` 依據內層 `float` 的 `div` 大小調整寬高。
* `display` 的 `flow-root` 也能做到，但只能把高度撐開，寬度不受影響。
>>>

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex06/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch01/ex06/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch01/ex06/index.html](https://gqsm.gitlab.io/csslayout/Ch01/ex06/index.html)
