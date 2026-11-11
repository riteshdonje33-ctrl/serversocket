let focused = false;

function nameOver() {
    if (!focused) document.body.style.backgroundColor = "lightblue";
}

function nameOut() {
    if (!focused) document.body.style.backgroundColor = "white";
}

function fieldFocus() {
    focused = true;
    document.body.style.backgroundColor = "lightgreen";
}

function fieldBlur() {
    focused = false;
    document.body.style.backgroundColor = "white";
}