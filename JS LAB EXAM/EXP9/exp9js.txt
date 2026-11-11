function validateForm() {
    let name = document.getElementById("name").value.trim();
    let address = document.getElementById("address").value.trim();
    let city = document.getElementById("city").value.trim();
    let state = document.getElementById("state").value;
    let g = document.querySelector('input[name="gender"]:checked');
    let mobile = document.getElementById("mobile").value.trim();
    let email = document.getElementById("email").value.trim();
    let e = "";

    if (!/^[A-Za-z ]{3,}$/.test(name)) e += "Name must have at least 3 characters, letters and spaces only.\n";
    if (address === "") e += "Address cannot be left blank.\n";
    if (!/^[A-Za-z ]+$/.test(city)) e += "City is required, letters and spaces only.\n";
    if (state === "") e += "Please select your state.\n";
    if (!g) e += "Please select your gender.\n";
    if (!/^[6-9]\d{9}$/.test(mobile)) e += "Mobile number must be 10 digits starting with 6, 7, 8 or 9.\n";
    if (!/^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,4}$/.test(email)) e += "Please enter a valid email id.\n";

    document.getElementById("error").textContent = e;
    if (e === "") {
        document.getElementById("result").textContent =
            "Name: " + name + "\nAddress: " + address + "\nCity: " + city +
            "\nState: " + state + "\nGender: " + g.value +
            "\nMobile: " + mobile + "\nEmail: " + email;
        document.getElementById("form").hidden = true;
        document.getElementById("welcome").hidden = false;
    }
    return false;
}

