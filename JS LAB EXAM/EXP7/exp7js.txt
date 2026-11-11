let arr = [], max = 0;

function show(id, text) {
    document.getElementById(id).textContent = text;
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
    show("currentArray", JSON.stringify(arr));
}

function addElement() {
    let text = document.getElementById("element").value.trim();
    if (max === 0) {
        show("createOutput", "Initialize the array first.");
        return;
    }
    if (arr.length >= max) {
        show("createOutput", "Array Overflow! Maximum size reached.");
        return;
    }
    if (text === "") {
        show("createOutput", "Please enter an element.");
        return;
    }
    let value = text;
    if (text[0] === "[" && text.endsWith("]")) {
        try {
            value = JSON.parse(text);
        } catch (e) {
            show("createOutput", "Invalid array format. Example: [1,2,3]");
            return;
        }
    } else if (!isNaN(text)) {
        value = Number(text);
    }
    arr.push(value);
    document.getElementById("element").value = "";
    show("createOutput", "Element added successfully.");
    show("currentArray", JSON.stringify(arr));
}

function checkArray() {
    let text = document.getElementById("indexInput").value.trim();
    let i = Number(text);
    if (max === 0) {
        show("indexOutput", "Initialize the array first.");
    } else if (arr.length === 0) {
        show("indexOutput", "Array is Empty.");
    } else if (text === "" || !Number.isInteger(i) || i < 0) {
        show("indexOutput", "Please enter a valid index.");
    } else if (i >= arr.length) {
        show("indexOutput", "Invalid Index.");
    } else if (Array.isArray(arr[i])) {
        show("indexOutput", "The object at index " + i + " is an Array. Value: " + JSON.stringify(arr[i]));
    } else {
        show("indexOutput", "The object at index " + i + " is NOT an Array. Value: " + arr[i]);
    }
}