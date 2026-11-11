// function show(id, message) {
//     document.getElementById(id).textContent = message;
// }

// function reverseText() {
//     let text = document.getElementById("reverseInput").value;
//     if (text.trim() === "") {
//         show("reverseOutput", "Please enter a string.");
//     } else {
//         show("reverseOutput", "Reversed: " + text.split("").reverse().join(""));
//     }
// }

// function replaceCharacter(all) {
//     let text = document.getElementById("originalText").value;
//     let target = document.getElementById("searchChar").value;
//     let replacement = document.getElementById("replacement").value;
//     if (text.trim() === "" || target.length !== 1) {
//         show("replaceOutput", "Enter a string and exactly one character to find.");
//     } else if (!text.includes(target)) {
//         show("replaceOutput", '"' + target + '" was not found in the string.');
//     } else {
//         let result = all ? text.split(target).join(replacement) : text.replace(target, replacement);
//         show("replaceOutput", "Result: " + result);
//     }
// }

// function testPalindrome() {
//     let original = document.getElementById("palindromeInput").value;
//     let cleaned = original.toLowerCase().replace(/[^a-z0-9]/g, "");
//     if (cleaned === "") {
//         show("palindromeOutput", "Please enter a valid string.");
//     } else if (cleaned === cleaned.split("").reverse().join("")) {
//         show("palindromeOutput", '"' + original + '" is a Palindrome!');
//     } else {
//         show("palindromeOutput", '"' + original + '" is NOT a Palindrome!');
//     }
// }


function show(id,message){
    document.getElementById(id).textContent = message;
}

// 
function reverseText(){
    let text = document.getElementById("reverseInput").value;
    if (text.trim()=== ""){

        // 
        show("reverseOutput","Please enter a string");

    }else{
        show("reverseOutput","Reversed:" + text.split("").reverse().join(""));
    }
}

// 
function replaceCharacter(all){
    let text = document.getElementById("originalText").value;
    let target = document.getElementById("searchChar").value;
    let replacement = document.getElementById("replacement").value;
    // 

    if (text.trim() === "" || target.length !== 1){
        show("replaceOutput","Enter a string and exact one character to find.");
    } else if (!text.includes(target)){
    // 

        show("replaceOutput",'"' + target + '"was not found in string');
    } else {
        // 
        let result = all ? text.split(target).join(replacement) : text.replace(target,replacement);
        show("replaceOutput", "Result:" + result);

        // 
    }
}

// 
function testPalindrome(){
    let original = document.getElementById("palindromeInput").value;
    let cleaned = original.toLowerCase().replace(/[^a-z0-9]/g,"");

    // 
    if (cleaned === ""){
        show("palindromeOutput","Please enter a valid string.");
    }
    //  
    else if (cleaned = cleaned.split("").reverse().join("")){
        show("palindromeOutput",'"' + original + '"is a Palindrome!');
    } else{
        // 
        show("palindromeOuptut",'"' + original + '"is not a Palindrome');
    }
}