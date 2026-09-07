<!DOCTYPE html>
<html lang="id">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kasir Nasya</title>

<style>
*{
    box-sizing:border-box;
}

body{
    margin:0;
    font-family:Arial,sans-serif;
    background:#f5f6fa;
    color:#333;
}

header{
    background:#6c5ce7;
    color:white;
    padding:20px;
    text-align:center;
}

header h1{
    margin:0;
    font-size:28px;
}

header p{
    margin:6px 0 0;
}

.container{
    width:95%;
    max-width:900px;
    margin:20px auto;
}

.card{
    background:white;
    padding:20px;
    margin-bottom:20px;
    border-radius:15px;
    box-shadow:0 4px 12px rgba(0,0,0,.08);
}

h2{
    margin-top:0;
    color:#6c5ce7;
}

.grid{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:15px;
}

label{
    display:block;
    margin-bottom:6px;
    font-weight:bold;
}

input,select{
    width:100%;
    padding:12px;
    border:1px solid #ddd;
    border-radius:8px;
    font-size:15px;
}

button{
    border:none;
    padding:11px 15px;
    border-radius:8px;
    cursor:pointer;
    font-weight:bold;
}

.btn-primary{
    width:100%;
    background:#6c5ce7;
    color:white;
    margin-top:15px;
}

.btn-primary:hover{
    background:#5849c4;
}

.btn-danger{
    background:#ff7675;
    color:white;
}

.btn-success{
    background:#00b894;
    color:white;
}

.btn-secondary{
    background:#dfe6e9;
    color:#333;
}

.statistik{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:10px;
    margin-bottom:20px;
}

.stat{
    background:white;
    padding:18px;
    border-radius:12px;
    text-align:center;
    box-shadow:0 3px 10px rgba(0,0,0,.06);
}

.stat h3{
    margin:0;
    color:#6c5ce7;
    font-size:24px;
}

.stat p{
    margin:5px 0 0;
    color:#777;
}

table{
    width:100%;
    border-collapse:collapse;
}

th,td{
    padding:12px 8px;
    border-bottom:1px solid #eee;
    text-align:left;
}

th{
    color:#6c5ce7;
}

.total-box{
    margin-top:15px;
    background:#f0edff;
    padding:18px;
    border-radius:10px;
}

.total{
    font-size:26px;
    font-weight:bold;
    color:#6c5ce7;
}

.pembayaran{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:15px;
}

.kembalian{
    margin-top:15px;
    padding:15px;
    border-radius:10px;
    background:#e8fff7;
    color:#00866b;
    font-size:18px;
}

.kurang{
    background:#ffeaea;
    color:#d63031;
}

.struk{
    display:none;
    max-width:400px;
    margin:auto;
    background:white;
    padding:20px;
}

.struk h2,
.struk p{
    text-align:center;
}

.struk table{
    font-size:13px;
}

.center{
    text-align:center;
}

@media(max-width:600px){

    .grid,
    .pembayaran{
        grid-template-columns:1fr;
    }

    .statistik{
        grid-template-columns:1fr;
    }

    table{
        font-size:13px;
    }

    th,td{
        padding:8px 4px;
    }
}

@media print{

    body *{
        visibility:hidden;
    }

    .struk,
    .struk *{
        visibility:visible;
    }

    .struk{
        display:block;
        position:absolute;
        left:0;
        top:0;
        width:100%;
    }
}
</style>
</head>

<body>

<header>
    <h1>🛒 KASIR NASYA</h1>
    <p>Sistem Kasir Sederhana</p>
</header>

<div class="container">

<!-- STATISTIK -->
<div class="statistik">

    <div class="stat">
        <h3 id="jumlahProduk">0</h3>
        <p>Jenis Barang</p>
    </div>

    <div class="stat">
        <h3 id="jumlahItem">0</h3>
        <p>Total Item</p>
    </div>

    <div class="stat">
        <h3 id="totalStat">Rp 0</h3>
        <p>Total Belanja</p>
    </div>

</div>

<!-- TAMBAH BARANG -->
<div class="card">

    <h2>📦 Tambah Barang</h2>

    <div class="grid">

        <div>
            <label>Nama Barang</label>
            <input
                type="text"
                id="nama"
                placeholder="Contoh: Mie Instan">
        </div>

        <div>
            <label>Kategori</label>
            <select id="kategori">
                <option value="Makanan">Makanan</option>
                <option value="Minuman">Minuman</option>
                <option value="Sembako">Sembako</option>
                <option value="Lainnya">Lainnya</option>
            </select>
        </div>

        <div>
            <label>Harga</label>
            <input
                type="number"
                id="harga"
                placeholder="Contoh: 5000">
        </div>

        <div>
            <label>Jumlah</label>
            <input
                type="number"
                id="jumlah"
                value="1"
                min="1">
        </div>

    </div>

    <button
        class="btn-primary"
        onclick="tambahBarang()">
        ➕ Tambahkan ke Keranjang
    </button>

</div>

<!-- KERANJANG -->
<div class="card">

    <h2>🛒 Keranjang Belanja</h2>

    <div id="keranjang">

        <p class="center">
            Belum ada barang.
        </p>

    </div>

    <div class="total-box">

        <div>Total Belanja</div>

        <div
            class="total"
            id="total">
            Rp 0
        </div>

    </div>

</div>

<!-- PEMBAYARAN -->
<div class="card">

    <h2>💵 Pembayaran</h2>

    <div class="pembayaran">

        <div>

            <label>Uang Pembayaran</label>

            <input
                type="number"
                id="bayar"
                placeholder="Masukkan uang">

        </div>

        <div>

            <label>Total</label>

            <input
                type="text"
                id="totalBayar"
                value="Rp 0"
                readonly>

        </div>

    </div>

    <button
        class="btn-success"
        style="width:100%;margin-top:15px"
        onclick="hitungKembalian()">

        💰 Hitung Pembayaran

    </button>

    <div id="hasil"></div>

</div>

<!-- TOMBOL TRANSAKSI -->
<div class="card">

    <h2>🧾 Transaksi</h2>

    <div class="grid">

        <button
            class="btn-success"
            onclick="cetakStruk()">

            🖨️ Cetak Struk

        </button>

        <button
            class="btn-secondary"
            onclick="transaksiBaru()">

            🔄 Transaksi Baru

        </button>

    </div>

</div>

</div>

<!-- STRUK -->
<div class="struk" id="struk">

    <h2>🛒 KASIR NASYA</h2>

    <p>Struk Pembayaran</p>

    <hr>

    <p id="tanggal"></p>

    <table>

        <thead>

            <tr>
                <th>Barang</th>
                <th>Qty</th>
                <th>Total</th>
            </tr>

        </thead>

        <tbody id="isiStruk"></tbody>

    </table>

    <hr>

    <p>
        Total:
        <b id="strukTotal">Rp 0</b>
    </p>

    <p>
        Bayar:
        <b id="strukBayar">Rp 0</b>
    </p>

    <p>
        Kembalian:
        <b id="strukKembalian">Rp 0</b>
    </p>

    <hr>

    <p>Terima kasih 😊</p>

</div>

<script>

let keranjang = [];

let totalBelanja = 0;


/* FORMAT RUPIAH */

function rupiah(angka){

    return "Rp " + angka.toLocaleString("id-ID");

}


/* TAMBAH BARANG */

function tambahBarang(){

    let nama =
        document.getElementById("nama").value.trim();

    let kategori =
        document.getElementById("kategori").value;

    let harga =
        parseInt(document.getElementById("harga").value);

    let jumlah =
        parseInt(document.getElementById("jumlah").value);


    if(nama === "" || !harga || !jumlah){

        alert("Silakan lengkapi data barang!");

        return;

    }


    let barangLama =
        keranjang.find(
            item => item.nama.toLowerCase()
            === nama.toLowerCase()
        );


    if(barangLama){

        barangLama.jumlah += jumlah;

        barangLama.subtotal =
            barangLama.harga *
            barangLama.jumlah;

    }else{

        keranjang.push({

            nama:nama,

            kategori:kategori,

            harga:harga,

            jumlah:jumlah,

            subtotal:harga * jumlah

        });

    }


    tampilkanKeranjang();


    document.getElementById("nama").value = "";

    document.getElementById("harga").value = "";

    document.getElementById("jumlah").value = "1";

}


/* TAMPILKAN KERANJANG */

function tampilkanKeranjang(){

    let area =
        document.getElementById("keranjang");


    area.innerHTML = "";

    totalBelanja = 0;

    let jumlahItem = 0;


    if(keranjang.length === 0){

        area.innerHTML =
            '<p class="center">Belum ada barang.</p>';

    }


    keranjang.forEach(function(item,index){

        totalBelanja += item.subtotal;

        jumlahItem += item.jumlah;


        area.innerHTML += `

        <div style="
            border-bottom:1px solid #eee;
            padding:12px 0;
        ">

            <b>${item.nama}</b>

            <br>

            <small>
                ${item.kategori}
            </small>

            <br>

            ${item.jumlah} x
            ${rupiah(item.harga)}

            <br>

            <b>
                ${rupiah(item.subtotal)}
            </b>

            <br>

            <button
                class="btn-danger"
                onclick="hapusBarang(${index})">

                🗑️ Hapus

            </button>

        </div>

        `;

    });


    document.getElementById("total").innerText =
        rupiah(totalBelanja);


    document.getElementById("totalBayar").value =
        rupiah(totalBelanja);


    document.getElementById("jumlahProduk").innerText =
        keranjang.length;


    document.getElementById("jumlahItem").innerText =
        jumlahItem;


    document.getElementById("totalStat").innerText =
        rupiah(totalBelanja);

}


/* HAPUS BARANG */

function hapusBarang(index){

    keranjang.splice(index,1);

    tampilkanKeranjang();

}


/* HITUNG KEMBALIAN */

function hitungKembalian(){

    if(keranjang.length === 0){

        alert("Keranjang masih kosong!");

        return;

    }


    let bayar =
        parseInt(
            document.getElementById("bayar").value
        );


    if(!bayar){

        alert("Masukkan uang pembayaran!");

        return;

    }


    let kembalian =
        bayar - totalBelanja;


    let hasil =
        document.getElementById("hasil");


    if(kembalian < 0){

        hasil.innerHTML = `

        <div class="kembalian kurang">

            ❌ Uang pembayaran kurang.

            <br><br>

            Kekurangan:
            <b>${rupiah(Math.abs(kembalian))}</b>

        </div>

        `;

    }else{

        hasil.innerHTML = `

        <div class="kembalian">

            ✅ Pembayaran Berhasil!

            <br><br>

            Total:
            <b>${rupiah(totalBelanja)}</b>

            <br>

            Bayar:
            <b>${rupiah(bayar)}</b>

            <br>

            Kembalian:
            <b>${rupiah(kembalian)}</b>

        </div>

        `;

    }

}


/* CETAK STRUK */

function cetakStruk(){

    if(keranjang.length === 0){

        alert("Belum ada transaksi!");

        return;

    }


    let bayar =
        parseInt(
            document.getElementById("bayar").value
        );


    if(!bayar || bayar < totalBelanja){

        alert("Selesaikan pembayaran terlebih dahulu!");

        return;

    }


    let isi =
        document.getElementById("isiStruk");


    isi.innerHTML = "";


    keranjang.forEach(function(item){

        isi.innerHTML += `

        <tr>

            <td>${item.nama}</td>

            <td>${item.jumlah}</td>

            <td>${rupiah(item.subtotal)}</td>

        </tr>

        `;

    });


    let kembalian =
        bayar - totalBelanja;


    document.getElementById("strukTotal").innerText =
        rupiah(totalBelanja);


    document.getElementById("strukBayar").innerText =
        rupiah(bayar);


    document.getElementById("strukKembalian").innerText =
        rupiah(kembalian);


    document.getElementById("tanggal").innerText =
        new Date().toLocaleString("id-ID");


    window.print();

}


/* TRANSAKSI BARU */

function transaksiBaru(){

    if(keranjang.length > 0){

        let yakin =
            confirm(
                "Hapus transaksi dan mulai baru?"
            );

        if(!yakin){

            return;

        }

    }


    keranjang = [];

    totalBelanja = 0;


    document.getElementById("bayar").value = "";

    document.getElementById("hasil").innerHTML = "";


    tampilkanKeranjang();

}


/* TAMPILKAN DATA AWAL */

tampilkanKeranjang();

</script>

</body>
</html>
