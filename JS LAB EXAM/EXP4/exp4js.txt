// function detectCase(s) {
//     let up = s !== s.toLowerCase();
//     let low = s !== s.toUpperCase();
//     return up && low ? "uppercase and lowercase" : up ? "uppercase only" : low ? "lowercase only" : "no alphabetic characters";
// }

// function runComparison() {
//     let first = document.getElementById("textA").value;
//     let second = document.getElementById("textB").value;
//     let error = document.getElementById("errorMessage");
//     let result = document.getElementById("resultBox");

//     error.textContent = "";
//     result.innerHTML = "";

//     if (first.trim() === "" || second.trim() === "") {
//         error.textContent = "Please enter both strings.";
//         return;
//     }

//     let order = first.localeCompare(second);
//     let orderText = order === 0 ? "Both strings are alphabetically identical."
//         : order < 0 ? "The first string comes before the second string."
//         : "The first string comes after the second string.";

//     let caseText;
//     if (first === second) {
//         caseText = "Both strings are completely identical.";
//     } else if (first.toLowerCase() === second.toLowerCase()) {
//         caseText = "Same letters, but casing is different. First string: " + detectCase(first) + ". Second string: " + detectCase(second) + ".";
//     } else {
//         caseText = "The strings contain different values.";
//     }

//     result.innerHTML =
//         "<p>Length: " + (first.length === second.length ? "same" : "different") + " (" + first.length + " and " + second.length + " characters)</p>" +
//         "<p>Loose equality (==): " + (first == second ? "equal" : "not equal") + "</p>" +
//         "<p>Strict equality (===): " + (first === second ? "equal" : "not equal") + "</p>" +
//         "<p>localeCompare(): " + orderText + "</p>" +
//         "<p>Case analysis: " + caseText + "</p>";
// }

// 
// function detectCase(s){
//     let up = s !== s.toLowerCase();
//     let low = s !== s.toUpperCase();

//     // 
//     return up && low ? "uppercase and lowercase" : up ? "uppercase only" : low ? "lowercase only" : "no alphabetic characters";
// }


// function runComparison(){
//     let first = document.getElementById("textA").value;
//     let second = document.getElementById("textB").value;
//     let error = document.getElementById("errorMessage").value;
//     let result = document.getElementById("resultBox").value;

//     // 
//     error.textContent = "";
//     result.innerHTML = "";

//     // 

//     if(first.trim() === "" || second.trim() === ""){
//         error.textContent = "Please enter both strings";
//         return;
//     }
//     // 

//     let order = first.localeCompare(second);
//     let orderText = order === 0 ? "Both strings are alphabetically identical."
//     : order < 0 ? "The first string comes before second."
//     : "the first string comes after second.";
//     let caseText;


//     // 
//     if (first === second){
//         caseText = "Both strings are identical";
//     } else if (first.toLowerCase() === second.toLowerCase()){
//         // 

//         caseText = "same letters,but caseing different First string:" +
//         detectCase(first) + ". Second string: " + detectCase(second) + ".";

//     } else {
//         caseText = "The strings contain different values.";
//     }
// result.innerHTML =
//         "<p>Length: " + (first.length === second.length ? "same" : "different") + " (" + first.length + " and " + second.length + " characters)</p>" +
//         "<p>Loose equality (==): " + (first == second ? "equal" : "not equal") + "</p>" +
//         "<p>Strict equality (===): " + (first === second ? "equal" : "not equal") + "</p>" +
//         "<p>localeCompare(): " + orderText + "</p>" +
//         "<p>Case analysis: " + caseText + "</p>";
// }

function detectCase(s) {
    let up = s !== s.toLowerCase();
    let low = s !== s.toUpperCase();

    return up && low ? "uppercase and lowercase"
        : up ? "uppercase only"
        : low ? "lowercase only"
        : "no alphabetic characters";
}

function runComparison() {
    let first = document.getElementById("textA").value;
    let second = document.getElementById("textB").value;

    // Corrected: removed .value
    let error = document.getElementById("errorMessage");
    let result = document.getElementById("resultBox");

    error.textContent = "";
    result.innerHTML = "";

    if (first.trim() === "" || second.trim() === "") {
        error.textContent = "Please enter both strings";
        return;
    }

    let order = first.localeCompare(second);

    let orderText = order === 0
        ? "Both strings are alphabetically identical."
        : order < 0
        ? "The first string comes before the second."
        : "The first string comes after the second.";

    // Corrected: caseText (not casetext)
    let caseText;

    if (first === second) {
        caseText = "Both strings are identical";

    } else if (first.toLowerCase() === second.toLowerCase()) {

        caseText = "Same letters, but casing is different. First string: "
            + detectCase(first) + ". Second string: "
            + detectCase(second) + ".";

    } else {
        caseText = "The strings contain different values.";
    }

    result.innerHTML =
        "<p>Length: " +
        (first.length === second.length ? "same" : "different") +
        " (" + first.length + " and " + second.length + " characters)</p>" +

        "<p>Loose equality (==): " +
        (first == second ? "equal" : "not equal") + "</p>" +

        "<p>Strict equality (===): " +
        (first === second ? "equal" : "not equal") + "</p>" +

        "<p>localeCompare(): " + orderText + "</p>" +

        "<p>Case analysis: " + caseText + "</p>";
}
