// function createTable(type) {
//     let number = Number(document.getElementById(type + "Number").value);
//     let limit = Number(document.getElementById(type + "Limit").value);
//     let error = document.getElementById(type + "Error");
//     let result = document.getElementById(type + "Result");

//     error.textContent = "";
//     result.textContent = "";

//     if (!Number.isInteger(number) || number === 0) {
//         error.textContent = "Enter a valid non-zero integer.";
//         return;
//     }
//     if (!Number.isInteger(limit) || limit < 1) {
//         error.textContent = "Limit must be a positive integer.";
//         return;
//     }

//     let table = "";

//     if (type === "for") {
//         for (let i = 1; i <= limit; i++) {
//             table += number + " × " + i + " = " + (number * i) + "\n";
//         }
//     } else if (type === "while") {
//         let i = 1;
//         while (i <= limit) {
//             table += number + " × " + i + " = " + (number * i) + "\n";
//             i++;
//         }
//     } else if (type === "do") {
//         let i = 1;
//         do {
//             table += number + " × " + i + " = " + (number * i) + "\n";
//             i++;
//         } while (i <= limit);
//     }

//     result.textContent = table;
// }

// function and  2 get input

function createTable(type){
    let number = Number(document.getElementById(type + "Number").value);
    let limit = Number(document.getElementById(type+ "Limit").value);

    // error and results

    let error = document.getElementById(type + "Error");
    let result = document.getElementById(type + "Result");

    // clear previous two lines
    error.textContent = "";
    result.textContent = "";

    // clause of number
    if (!Number.isInteger(number) || number === 0) {
        error.textContent = "Enter the valid non-zero int."
        return;
    }

    // limit guard

    if (!Number.isInteger(limit) || limit < 1){
        error.textContent = "Limit must be positive integer . ";
        return;
    }

    // For + loop

    let table = "";

    if (type === "for"){
        for(let i = 1; i <= limit ;i++){
            table = table + number + "x" + i + " = " + (number * i) + "\n";
        }
    //next
    } else if( type === "while"){
        let i = 1;
        while(i<= limit){
            // next
             table = table + number + "x" + i + " = " + (number * i) + "\n";
             i++;
        } 
///
        }
        else if(type === "do"){
            let i = 1;
            do {
                //
                 table = table + number + "x" + i + " = " + (number * i) + "\n";
                 i++;
            }while (i<=limit);
    }
    result.textContent = table;
}