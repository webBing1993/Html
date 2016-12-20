    //轮播图模块
    var todayScroll = document.getElementById("today_scroll");
    var todayUl= todayScroll.children[0];
    var items = todayUl.children;
    var arrow = todayScroll.children[1];
    var arrowL = arrow.children[0];
    var arrowR = arrow.children[1];
    var target = 0,leader = 0;

    todayScroll.onmouseover = function () {
        arrow.style.display = "block";
    };
    todayScroll.onmouseout = function () {
        arrow.style.display = "none";
    };

    arrowL.onclick = function () {
        target += 252;
    };
    arrowR.onclick = function () {
        target -= 252;
    };
    setInterval(function () {
        if(target < -2015){
            target = 0;
        }else if(target > 0){
            target = -1764;
        }
        leader = leader + (target - leader) / 10;
        todayUl.style.left = leader + "px";
    },1);
