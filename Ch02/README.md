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

#### 5.`position`實際運用-捲動固定選單
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

#### 6.`position`實際運用-滑動顯示區塊
1. 創建內外層兩個`div`
    ```html
    <div id="banner_block">
        <div id="banner_inside_block">
            滑到我這</br>
            YA！
        </div>
    </div>
    ```
>>>
備註說明：
* 上方的內層`div`有兩行，待會我們會設定`position`和`overflow`讓第一行以下的內容隱藏。
>>>
2. 為外層`div`設定高度、`position`和背景顏色
    ```css
    #banner_block {
        background-color: #cfcfcf;
        height: 200px;
        position: relative;
    }
    ```
>>>
備註說明：
* 使用`relative`是為了讓內層的`div`可以以外層`div`為基準。
>>>
3. 為內層`div`設定寬高、`position`和`overflow`、背景顏色和內容置中等
    ```css
    #banner_inside_block {
        width: 100%;
        height: 20px;
        position: absolute;
        bottom: 0px;
        overflow: hidden;
        background-color: #ffffff59;
        text-align: center;
    }
    ```
>>>
備註說明：
* `position`設定`absolute`讓基準點改變為外層`div`，在移動該位置使他貼緊外層`div`的底部。
* `height`設定為`20px`剛好為一行字的高度。
* `overflow`設定`hidden`讓多出外層`div`的部分（二行以下的內容）可以隱藏起來。
* `background-color`指定的`#ffffff59`後面兩個數字為控制透明度。
    * 透明度的數值越小透明度越高。
>>>
4. 為內層`div`設定偽元素，在滑鼠停留時可以改變高度
    ```css
    #banner_inside_block {
        height: 100%;
    }
    ```
>>>
備註說明：
* 關於偽元素：[https://www.oxxostudio.tw/articles/201706/pseudo-element-1.html](https://www.oxxostudio.tw/articles/201706/pseudo-element-1.html)
>>>
5. 為內層`div`添加`transition`動畫，讓高度由`20px`到`100%`的過程可以有滑動動畫
    ```css
    #banner_inside_block {
        /*省略先前屬性*/
        transition: height 0.5s;
    }

    #banner_inside_block {
        height: 100%;
        transition: height 0.5s;
    }
    ```
>>>
備註說明：
* `transition`帶有兩個參數
    * 第一個為產生變化效果的屬性。
    * 第二個為動畫時間。
>>>

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex06/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex06/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch02/ex06/index.html](https://gqsm.gitlab.io/csslayout/Ch02/ex06/index.html)

#### 7.`position`實際運用-懸浮選單
1. 創建一個`div`並在內層用`ul`及`li`製作選單
    ```html
    <div id="menu_block">
        <ul>
            <li class="menu_list">
                <a href="#">選單1</a>
            </li>
            <li class="menu_list">
                <a href="#">選單2</a>
            </li>
        </ul>
    </div>
    ```
2. 為該`div`設定背景顏色
    ```css
    #menu_block {
        background-color: #000000;
    }
    ```
3. 將選單`ul`設定`float`浮動靠右
    ```css
    #menu_block ul {
        float: right;
    }
    ```
4. 將選單`ul`內部的`li`設定`float`浮動靠左，並設定`padding`、`position`和取消項目符號樣式
    ```css
    .menu_list {
        float: left;
        padding: 15 50 15 0;
        list-style-type: none;
        position: relative;
    }
    ```
>>>
備註說明：
* 這裡選擇使用`padding`是因為他可以使`li`的寬度依內容將寬度撐開。
* `position`設定`relative`是為了讓浮動以該`li`的位置為基準點。
>>>
5. 由於內部的`ul`選單設定`float`，外層`menu_block`的高度將不會被撐開，因此在選單下增加一個`div`並設置`clear`屬性
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
6. 將`li`內部的`a`預設樣式取消，設定字體顏色為白色
    ```css
    .menu_list a {
        color: #ffffff;
        text-decoration: none;
    }
    ```
7. 在`li`中再增加一層使用`ul`和`li`製作的子選單
    ```html
    <li class="menu_list"><a href="#">選單1</a>
        <ul>
            <li class="menu_sub_list"><a href="#">選單1-1</a></li>
            <li class="menu_sub_list"><a href="#">選單1-2</a></li>
            <li class="menu_sub_list"><a href="#">選單1-3</a></li>
        </ul>
    </li>
    ```
8. 將子選單`ul`用`display`設定為隱藏、`position`調整子選單的位置，除此之外調整背景顏色、寬度還有內邊距`padding`。
    ```css
    .menu_list ul {
        position: absolute;
        top:35px;
        left: -30px;
        display: none;
        background-color: #00000050;
        width:100%;
        padding: 10px;
    }  
    ```
9. 使用偽元素，在滑鼠移到`menu_list`父選單時，將子選單的`ul`顯示
    ```css
    .menu_list:hover ul{
        display: block;
    }  
    ```
10. 將子選單的`li`取消項目符號的樣式，並設定寬度和內容置中
    ```css
    .menu_sub_list{
        width: 100%;
        list-style-type: none;
        text-align: center;
    }
    ```

程式碼：[https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex07/index.html](https://gitlab.com/GQSM/csslayout/blob/master/Ch02/ex07/index.html)

頁面：[https://gqsm.gitlab.io/csslayout/Ch02/ex07/index.html](https://gqsm.gitlab.io/csslayout/Ch02/ex07/index.html)
