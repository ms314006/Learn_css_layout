## Ch02 position

---

#### 1.`position`的基本用法-`relative`篇

---

1. 創建兩個外層與一個內層`div`
    ```html
    <div id="out_block_top">
        <div id="in_block">
        </div>
    </div>
    <div id="out_block_bottom">
    </div>
    ```
2. 為外層的上方`div`增加寬高及背景顏色
    ```css
    #out_block_top{
        width:200px;
        height:200px;
        background-color:#061d5e;
    }
    ```
3. 為內層`div`設定`position`為`relative`，再以`top`及`left`屬性控制距離上左多少，並增加寬高及背景顏色
    ```css
    #in_block{
        position:relative;
        top:20px;
        left:20px;
        width:200px;
        height:200px;
        background-color:#061d5e;
    }
    ```
    >>>
    備註說明：
    * `position`的預設屬性是`static`，在此屬性下無法控制位置。
    * 可將值給`top`、`left`、`bottom`、`right`設定間隔距離，
    * 間隔以頁面的左上角為基準點。
    >>>
4. 設定外層下方`div`的`position`屬性，並將他移動位置，設定寬高背景顏色
    ```css
    #out_block_bottom{
        position:relative;
        bottom:20px;
        right:20px;
        width:200px;
        height:200px;
        background-color:#061d5e;
    }
    ```

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex01/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex01/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch02/ex01/index.html](https://gqsm.gitlab.io/csslayout/Ch02/ex01/index.html)


#### 2.`position`的基本用法-`absolute`篇

---

1. 創建內外兩個`div`
    ```html
    <div id="out_block">
        <div id="in_block">
        </div>
    </div>
    ```
2. 將外層`div`的`position`設定`relative`，並將他移動位置，設定寬高背景顏色
    ```css
    #out_block{
        position:relative;
        top:100px;
        left:150px;
        width:300px;
        height:300px;
        background-color:#000000;
    }
    ```
3. 將內層`div`的`position`設定`absolute`，並將他移動位置，設定寬高背景顏色
    ```css
    #in_block{
        position:absolute;
        top:50px;
        left:100px;
        width:100px;
        height:100px;
        background-color:#ffffff;
    }
    ```

>>>
備註說明：
* 當`position`設定`absolute`時，移動的基準點會變為外層`div`的左上角。
>>>

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex02/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex02/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch02/ex02/index.html](https://gqsm.gitlab.io/csslayout/Ch02/ex02/index.html)

#### 3.`position`的基本用法-`fixed`篇
1. 創建內外層兩個`div`
    ```html
    <div id="out_block">
        <div id="in_block">
        </div>
    </div>
    ```
2. 為外層`div`設定寬高及背景顏色
    ```css
    #out_block {
        width: 300px;
        height: 2000px;
        background-color: #000000;
    }
    ```
3. 為內層`div`設定`position`為`fixed`，並將他移動位置，設定寬高背景顏色
    ```css
    #in_block {
        position: fixed;
        top: 50px;
        left: 100px;
        width: 100px;
        height: 100px;
        background-color: #ffffff;
    }
    ```
>>>
備註說明：
* 將`position`設定`fixed`可將它固定在畫面上，當捲軸移動頁面時也會跟著調整`top`的距離。
>>>

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex03/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex03/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch02/ex03/index.html](https://gqsm.gitlab.io/csslayout/Ch02/ex03/index.html)

#### 4.`position`的基本用法-`sticky`篇
1. 創建外層和兩個內層`div`
    ```html
    <div id="out_block">
        <div id="in_block_top">
        </div>
        <div id="in_block_bottom">
        </div>
    </div>
    ```
2. 為外層`div`設定寬高及背景顏色
    ```css
    #out_block {
        width: 100%;
        height: 2000px;
    }
    ```
3. 為內層上方`div`設定`position`為`sticky`，設定距離上方 0 、高和背景顏色
    ```css
    #in_block_top {
        position: sticky;
        top: 0px;
        height: 100px;
        background-color: #000000;
    }
    ```
    >>>
    備註說明：
    * 當`position`設定為`sticky`時，`width`會預設為父元素的寬度。
    >>>

4. 為內層下方的`div`設定寬高及背景顏色
    ```css
    #in_block_bottom {
        width: 100%;
        height: 300px;
        background-color: #ff0000;
    }
    ```
>>>
備註說明：
* 將`position`設定`sticky`的效果和`fixed`相仿，不同的是`sticky`會佔有版面空間，而`fixed`不會。
* 可試著將上方的`sticky`改回`fixed`觀察差異處。
>>>

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex04/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex04/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch02/ex04/index.html](https://gqsm.gitlab.io/csslayout/Ch02/ex04/index.html)

#### 5. `position`實際運用-捲動固定選單
1. 創建外層及兩個內層`div`
    ```html
    <div id="out_block">
        <div id="menu_block">   
        </div>
        <div id="list_block">
        </div>
    </div>
    ```
2. 設置外層`div`的高度
    ```css
    #out_block {
        height: 2000px;
    }
    ```
3. 在`menu_block`的`div`中使用`ul`及`ui`設置選單
    ```html
    <div id="menu_block">
        <ul>
            <li class="menu_list"><a href="#">選單1</a></li>
            <li class="menu_list"><a href="#">選單2</a></li>
        </ul>
    </div>
    ```
4. 為`menu_block`的`div`增加`position`屬性、內間距和背景顏色
    ```css
    #menu_block {
        position: sticky;
        top: 0px;
        padding: 15px;
        background-color: #000000;
    }
    ```
5. 為`menu_block`內的`ul`選單向右浮動
    ```css
    #menu_block ul{
        float: right;
    }
    ```
6. 將`ul`中的`li`向左浮動呈現並排，並設定每個選項外邊距及移除掉列表樣式
    ```css
    .menu_list {
        float: left;
        margin-right: 20px;
        list-style-type: none;
    }
    ```
7. 取消列表`li`中`a`的連結樣式，並設定字體顏色為白色
    ```css
    .menu_list a{
        color: #ffffff;
        text-decoration: none;
    }
    ```
8. 由於內部的`ul`選單設定`float`，外層`menu_block`的高度將不會被撐開，因此在選單下增加一個`div`並設置`clear`屬性
    ```html
    <div id="menu_block">
        <ul>
            <li class="menu_list"><a href="#">選單1</a></li>
            <li class="menu_list"><a href="#">選單2</a></li>
        </ul>
        <div class="clearfix"></div>
    </div>
    ```

    ```css
    #clearfix {
        clear: both;
    }
    ```
9. 為`list_block`的`div`設定寬度，並使用外邊距讓他在`out_block`內可以置中
    ```css
    #list_block {
        width: 690px;
        margin: auto;
    }
    ```
10. 在`list_block`添加幾個`div`區塊作為列表
    ```html
    <div id="list_block">
        <div class="list">
            區塊一
        </div>
        <div class="list">
            區塊二
        </div>
        <div class="list">
            區塊三
        </div>
    </div>
    ```
11. 為每一個`list`設置`float`向左浮動，並增加外邊距、背景顏色和設置寬高
    ```css
    .list {
        float: left;
        width: 200px;
        height: 200px;
        margin: 15px;
        background-color: #ff0000;
    }
    ```

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex05/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex05/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch02/ex05/index.html](https://gqsm.gitlab.io/csslayout/Ch02/ex05/index.html)