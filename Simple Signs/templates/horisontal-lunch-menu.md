# horisontal-lunch-menu.html

``` html
<style>
    ul li {
        border-bottom: 1px dotted;
        list-style-type: none;
        margin-bottom: 25px;
        padding-bottom: 10px;
    }

    #main {
        color: #fcf8fa;
        background: #4b4dc2;
        width: 1024px;
        height: 600px;
        padding-top: 30px;
    }

    #header {
        font-family: 'Impact';
        font-size: 80px;
        text-transform: uppercase;
        text-align: center;
        border-bottom: 1px solid;
        padding-bottom: 20px;
        letter-spacing: 15px;
    }
</style>

<div id="main">

    <div id="header">lunch menu</div>

    <div style="
        width: 50%;
        float: left;
        font-family: 'Malayalam OTS';
        font-size: 50px;
    ">
        <ul>
            <li>Soup of the Day $13</li>
            <li>Calamari $18</li>
            <li>Stuffed Mushroom Caps $20</li>
            <li>Fresh Salad $32</li>
        </ul>

    </div>

    <div style="
        width: 40%;
        float: right;
        padding-right: 45px;
        padding-top: 55px;
    ">
        <img style="border-radius: 3px;" src="local:///lunch-menu.png" alt="">

    </div>

</div>

```
