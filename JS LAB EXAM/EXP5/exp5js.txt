// let timer = null;

// function two(n) {
//     return n < 10 ? "0" + n : n;
// }

// function show(y, mo, d, h, mi, s) {
//     document.getElementById("clock").textContent =
//         two(y) + " Years " + two(mo) + " Months " + two(d) + " Days " +
//         two(h) + " Hours " + two(mi) + " Minutes " + two(s) + " Seconds";
// }

// function tick(end) {
//     let now = new Date();
//     if (end <= now) {
//         clearInterval(timer);
//         timer = null;
//         show(0, 0, 0, 0, 0, 0);
//         document.getElementById("output").textContent = "EXPIRED";
//         return;
//     }
//     let y = end.getFullYear() - now.getFullYear();
//     let mo = end.getMonth() - now.getMonth();
//     let d = end.getDate() - now.getDate();
//     let h = end.getHours() - now.getHours();
//     let mi = end.getMinutes() - now.getMinutes();
//     let s = end.getSeconds() - now.getSeconds();

//     if (s < 0) { s += 60; mi--; }
//     if (mi < 0) { mi += 60; h--; }
//     if (h < 0) { h += 24; d--; }
//     if (d < 0) { d += new Date(end.getFullYear(), end.getMonth(), 0).getDate(); mo--; }
//     if (mo < 0) { mo += 12; y--; }

//     show(y, mo, d, h, mi, s);
// }

// function startTimer() {
//     let input = document.getElementById("endDate").value;
//     let out = document.getElementById("output");
//     if (input === "") {
//         out.textContent = "Please select an end date and time.";
//         return;
//     }
//     let end = new Date(input);
//     if (end <= new Date()) {
//         show(0, 0, 0, 0, 0, 0);
//         out.textContent = "The selected date and time is already over.";
//         return;
//     }
//     clearInterval(timer);
//     out.textContent = "Countdown started for " + end.toLocaleString() +
//         ". Total days remaining: " + Math.floor((end - new Date()) / 86400000);
//     tick(end);
//     timer = setInterval(function () { tick(end); }, 1000);
// }

// function stopTimer() {
//     if (timer === null) {
//         document.getElementById("output").textContent = "No countdown is running right now.";
//         return;
//     }
//     clearInterval(timer);
//     timer = null;
//     document.getElementById("output").textContent = "Countdown stopped by the user.";
// }
// 
let timer = null;
function two(n){
    return n < 10 ? "0" + n:n;
}

// 
function show(y,mo,d,h,mi,s){
    document.getElementById("clock").textContent =
        two(y)+" Years" + two(mo) + "Months" + two(d) + "Days" + 
        two(h)+" Hours" + two(mi) + "Minutes" + two(s) + "Seconds";
}
// 


function tick(end){
    let now = new Date();
    if (end <= now){
        // 
        clearInterval(timer);
        timer = null;
        show(0,0,0,0,0,0);
        document.getElementById("output").textContent = "EXPIRED";
        return;}


        // 

        let y = end.getFullYear() - now.getFullYear();
        let mo = end.getMonth() - now.getMonth();
        let d= end.getDate() - now.getDate();
        let h = end.getHours() - now.getHours();
        let mi = end.getMinutes() - now.getMinutes();
        let s = end.getSeconds() - now.getSeconds();

        // 
        if (s<0) {s += 60;mi--};
        if (mi<0){mi += 60;h--};
        if (h<0 ) {h+=24;d--};

        // 
        if (d<0){d+= new Date(end.getFullYear(),end.getMonth(),0).getDate();mo--;};
        // 

        if (mo <0){ mo +=12;y--;}
        show(y,mo,d,h,mi,s);
    }


function startTimer(){
    let input = document.getElementById("endDate").value;
    let out = document.getElementById("output");


    // 
    if (input === ""){
        out.textContent = "Please select an end date and time .";
        return;
    }

    // 
    let end = new Date(input);
    if (end <= new Date()){
        show(0,0,0,0,0,0);
        out.textContent = "The date and time is over";
        return;
    }
    // 

    clearInterval(timer);
    out.textContent = "Countdown started for " + end.toLocaleString()+
        ". Total days remaining:" + Math.floor((end - new Date())/86400000);
        tick(end);
        timer = setInterval(function(){tick(end);},1000);
}
    // 
function stopTimer(){
        if(timer ===null){
            document.getElementById("output").textContent = "No countdown is running right now";
            return;
        }
        // 

        clearInterval(timer);
        timer = null;
        document.getElementById("output").textContent = "Countdown stopped by the user.";

    }
