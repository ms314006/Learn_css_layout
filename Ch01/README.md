## Ch01 flex

---

#### 1.文繞圖

---

1. 創建外層與內層兩個`div`
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
2. 為外層`div`增加寬高及背景顏色
```css
#out_block{
    width:100%;
    height:200px;
    background-color:#061d5e;
}
```
3. 為內層`div`設定`float`
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

程式碼：[]()
頁面：[]()


#### 2.水平排列列表

---

1. 在外層`div`內創建幾個用`div`裝著的重複的列表
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
2. 為內層`div`設定`float:left`靠左排列
```css
#list_block .list {
    width: 100px;
    height: 100px;
    float: left;
    margin: 15px;
}
```
3. 為每個`list1`設定不同背景顏色
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

程式碼：[]()
頁面：[]()

3. 