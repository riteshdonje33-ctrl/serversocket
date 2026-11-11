// function circleArea() {
//     let r = Number(document.getElementById("radius").value);
//     if (r <= 0) {
//         document.getElementById("circleResult").innerHTML = "Enter a valid radius";
//         return;
//     }
//     let area = Math.PI * r * r;
//     document.getElementById("circleResult").innerHTML = "Area = " + area.toFixed(2);
// }

// function triangleArea() {
//     let a = Number(document.getElementById("side1").value);
//     let b = Number(document.getElementById("side2").value);
//     let c = Number(document.getElementById("side3").value);
//     if (a <= 0 || b <= 0 || c <= 0 || a + b <= c || a + c <= b || b + c <= a) {
//         document.getElementById("triangleResult").innerHTML = "Invalid triangle sides";
//         return;
//     }
//     let s = (a + b + c) / 2;
//     let area = Math.sqrt(s * (s - a) * (s - b) * (s - c));
//     document.getElementById("triangleResult").innerHTML = "Area = " + area.toFixed(2);
// }

// function rectangleArea() {
//     let l = Number(document.getElementById("length").value);
//     let b = Number(document.getElementById("breadth").value);
//     if (l <= 0 || b <= 0) {
//         document.getElementById("rectangleResult").innerHTML = "Enter valid values";
//         return;
//     }
//     let area = l * b;
//     document.getElementById("rectangleResult").innerHTML = "Area = " + area.toFixed(2);
// }

// funciton opening + gete line

function circleArea(){
    let r = Number(document.getElementById("radius").value);



    // circle clause
    if (r <= 0){
        document.getElementById("circleResult").innerHTML = "Enter a valid radius";
        return;
    }



    // caluclate + show + close
        let area = Math.PI * r *r;
        document.getElementById("circleResult").innerHTML = "Area =" + area.toFixed(2);

}

// triangle funciton 3 variables get

function triangleArea(){
    let a = Number(document.getElementById("side1").value);
    let b = Number(document.getElementById("side2").value);
    let c = Number(document.getElementById("side3").value);
    
    
    
    
    //  triangle clause
    if (a<= 0 || b <= 0 || c<= 0|| a+b <=c || b+c <=a || a+c <=b){
        document.getElementById("triangleResult").innerHTML = "Invalid Triangle sides";
        return;
    }



    // caluate trianlge
    let s = (a+b+c) / 2;
    let area = Math.sqrt(s *(s-a)*(s-b)*(s-c));

    // triangle result
    document.getElementById("triangleResult").innerHTML = "Area = " + area.toFixed(2);
}
// 8
function rectangleArea(){
    let l = Number(document.getElementById("length").value);
    let b = Number(document.getElementById("breadth").value);

    ///
    if (l<=0 || b <=0 ){
        document.getElementById("rectangleResult").innerHTML = "Invalid sides";
        return;
    }
// 10
    let area = l*b;
    document.getElementById("rectangleResult").innerHTML = "Area = " + area.toFixed(2);
}