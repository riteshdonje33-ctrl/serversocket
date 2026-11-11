let arr = [], max = 0;

function show(id, text) {
    document.getElementById(id).textContent = text;
}

function showArray() {
    show("currentArray", "[" + arr.join(", ") + "]");
}

function find(name, text) {
    if (text === "" || isNaN(text)) return -1;
    let n = Number(text);
    if (document.querySelector('input[name="' + name + '"]:checked').value === "value") {
        return arr.indexOf(n);
    }
    return Number.isInteger(n) && n >= 0 && n < arr.length ? n : -1;
}

function initializeArray() {
    let n = Number(document.getElementById("size").value);
    if (!Number.isInteger(n) || n < 1) {
        show("createOutput", "Please enter a positive integer for the array size.");
        return;
    }
    max = n;
    arr = [];
    show("createOutput", "Array initialized. Add elements one by one.");
    showArray();
}

function addElement() {
    let text = document.getElementById("element").value.trim();
    if (max === 0) {
        show("createOutput", "Initialize the array first.");
    } else if (text === "" || isNaN(text)) {
        show("createOutput", "Please enter a valid number.");
    } else if (arr.length >= max) {
        show("createOutput", "Array Overflow! Maximum size reached.");
    } else {
        arr.push(Number(text));
        show("createOutput", "Element added successfully.");
        showArray();
    }
}

function removeElement() {
    let i = find("removeType", document.getElementById("removeInput").value.trim());
    if (arr.length === 0) {
        show("removeOutput", "Array is Empty.");
    } else if (i === -1) {
        show("removeOutput", "Element not found or invalid index.");
    } else {
        show("removeOutput", "Element " + arr[i] + " removed from index " + i + ".");
        arr.splice(i, 1);
        showArray();
    }
}

function searchElement() {
    let i = find("searchType", document.getElementById("searchInput").value.trim());
    if (arr.length === 0) {
        show("searchOutput", "Array is Empty.");
    } else if (i === -1) {
        show("searchOutput", "Element not found or invalid index.");
    } else {
        show("searchOutput", "Element " + arr[i] + " found at index " + i + ".");
    }
}

function flushArray() {
    arr = [];
    max = 0;
    show("createOutput", "");
    show("removeOutput", "");
    show("searchOutput", "");
    show("flushOutput", "Array has been emptied successfully.");
    showArray();
}