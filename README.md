[web 1.html](https://github.com/user-attachments/files/25210526/web.1.html)
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Warkop tambar malem</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #a06c02;
            padding: 20px;
        }
        h1 {
            text-align: center;
        }
        .menu, .variant {
            margin: 10px 0;
        }
        button {
            padding: 10px 15px;
            margin: 5px;
            cursor: pointer;
            border: none;
            border-radius: 5px;
            background: hsl(0, 0%, 5%);
            color: white;
        }
        button:hover {
            background: #080808;
        }
        .total {
            margin-top: 20px;
            font-size: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

<h1>☕ Warkop tambar malem</h1>

<div class="menu">
    <button onclick="showVariant('kukuBima')">Kuku Bima</button>
    <button onclick="showVariant('tehManis')">Teh Manis</button>
    <button onclick="showVariant('tehSusu')">Teh Susu</button>
    <button onclick="addItem('Kopi Susu',7000)">Kopi Susu</button>
    <button onclick="addItem('Kopi',5000)">Kopi</button>
</div>

<div class="variant" id="variant"></div>

<div class="total">
    Total Harga: Rp <span id="total">0</span>
</div>

<script>
    let total = 0;

    function addItem(nama, harga) {
        total += harga;
        document.getElementById("total").innerText = total;
        alert(nama + " ditambahkan (Rp " + harga + ")");
    }

    function showVariant(menu) {
        let html = "";

        if (menu === "kukuBima") {
            html = `
                <h3>Pilih Kuku Bima</h3>
                <button onclick="addItem('Kuku Bima Susu Dingin',10000)">Susu Dingin</button>
                <button onclick="addItem('Kuku Bima Susu Panas',8000)">Susu Panas</button>
                <button onclick="addItem('Kuku Bima Dingin',5000)">Dingin</button>
                <button onclick="addItem('Kuku Bima Panas',3000)">Panas</button>
            `;
        }

        if (menu === "tehManis") {
            html = `
                <h3>Pilih Teh Manis</h3>
                <button onclick="addItem('Teh Manis Dingin',5000)">Dingin</button>
                <button onclick="addItem('Teh Manis Panas',3000)">Panas</button>
            `;
        }

        if (menu === "tehSusu") {
            html = `
                <h3>Pilih Teh Susu</h3>
                <button onclick="addItem('Teh Susu Dingin',11000)">Dingin</button>
                <button onclick="addItem('Teh Susu Panas',9000)">Panas</button>
            `;
        }

        document.getElementById("variant").innerHTML = html;
    }
</script>

</body>
</html>
