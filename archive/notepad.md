```js
function allclear(){
    if(lockdown == 0){
        alert("Alert not in progress.");
    }else{
        var safe = prompt("Confirm area clear of drones. If clear, please enter CLEAR");
        if(safe == "CLEAR"){
            document.getElementById("ts1").style.backgroundColor = "";
            document.getElementById("ts2").style.backgroundColor = "";
            document.getElementById("ts3").style.backgroundColor = "";
            document.getElementById("ts4").style.backgroundColor = "";
            document.getElementById("ts5").style.backgroundColor = "";
            document.getElementById("ts6").style.backgroundColor = "";
            document.getElementById("ts7").style.backgroundColor = "";
            document.getElementById("ts8").style.backgroundColor = "";
            document.getElementById("ts9").style.backgroundColor = "";
            document.getElementById("ts10").style.backgroundColor = "";
            document.getElementById("bimg1").src = "images/birds-from-below.jpg";
            document.getElementById("bimg2").src = "images/drone-from-below.jpg";
            document.getElementById("logo").src = "images/bird_logo.png";
            lockdown = 0;
        }else{
            alert("AREA NOT CONFIRMED CLEAR. PLEASE CONFIRM TO CLEAR ALERT.")
        }
    }
}
```