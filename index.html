<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistem Rapor Madin - SMPN 2 Kalipare</title>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
    <style>
        body { font-family: 'Times New Roman', Times, serif; margin: 0; background-color: #f0f2f5; color: #333; }
        
        /* Panel Kontrol */
        .no-print { 
            max-width: 1000px; margin: 20px auto; background: #fff; 
            padding: 20px; border-radius: 8px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); 
        }
        .control-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 15px; }
        .config-box { background: #f8f9fa; padding: 15px; border-radius: 6px; border: 1px solid #ddd; }
        .config-box label { display: block; font-size: 12px; font-weight: bold; margin-bottom: 5px; }
        .config-box input, .config-box select { width: 100%; padding: 8px; margin-bottom: 10px; border: 1px solid #ccc; border-radius: 4px; box-sizing: border-box; }

        /* Pengaturan Input Margin Berdampingan */
        .margin-inputs { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; }

        .btn-group { display: flex; gap: 8px; margin-top: 10px; flex-wrap: wrap; }
        .btn { padding: 10px 15px; cursor: pointer; border: none; border-radius: 4px; font-weight: bold; color: white; transition: 0.3s; font-size: 13px; }
        .btn-excel { background-color: #1D6F42; }
        .btn-logo { background-color: #6f42c1; }
        .btn-upload { background-color: #007bff; }
        .btn-print { background-color: #444; }

        /* Tampilan Rapor A4 */
        .rapor-page { 
            width: 210mm; min-height: 297mm; margin: 20px auto; 
            background: white; box-sizing: border-box; box-shadow: 0 0 10px rgba(0,0,0,0.1);
            /* Margin Default */
            padding-top: 15mm;
            padding-bottom: 15mm;
            padding-left: 20mm;
            padding-right: 15mm;
            position: relative;
        }

        /* Kop Surat */
        .kop-container { display: flex; align-items: center; border-bottom: 3px double black; padding-bottom: 10px; margin-bottom: 20px; }
        .logo-box { width: 80px; height: 80px; display: flex; align-items: center; justify-content: center; }
        .logo-box img { max-width: 100%; max-height: 100%; object-fit: contain; display: none; }
        .kop-text { flex: 1; text-align: center; padding-right: 80px; }
        .kop-text h3 { margin: 2px 0; font-size: 14pt; text-transform: uppercase; }
        .kop-text h2 { margin: 2px 0; font-size: 16pt; text-transform: uppercase; }
        .kop-text p { margin: 2px 0; font-size: 10pt; font-style: italic; }

        .judul { text-align: center; margin-bottom: 20px; font-size: 14pt; font-weight: bold; text-decoration: underline; }
        .info-table { width: 100%; border: none; margin-bottom: 15px; font-size: 12pt; }
        
        .main-table { width: 100%; border-collapse: collapse; margin-bottom: 15px; }
        .main-table th, .main-table td { border: 1px solid black; padding: 8px; font-size: 10pt; line-height: 1.3; }
        .main-table th { background-color: #f2f2f2; }

        .footer-table { width: 100%; margin-top: 30px; border: none; text-align: center; font-size: 11pt; }
        
        @media print {
            .no-print { display: none; }
            body { background: none; margin: 0; }
            .rapor-page { box-shadow: none; margin: 0; width: 100%; border: none; }
        }
    </style>
</head>
<body>

<div class="no-print">
    <h3 style="margin-top:0">⚙️ Panel Pengaturan Margin Lengkap</h3>
    
    <div class="control-grid">
        <div class="config-box">
            <strong>📏 Atur Semua Sisi Margin (mm)</strong>
            <div class="margin-inputs" style="margin-top:10px">
                <div><label>Atas</label><input type="number" id="mTop" value="15" oninput="updateMargins()"></div>
                <div><label>Bawah</label><input type="number" id="mBottom" value="15" oninput="updateMargins()"></div>
                <div><label>Kiri</label><input type="number" id="mLeft" value="20" oninput="updateMargins()"></div>
                <div><label>Kanan</label><input type="number" id="mRight" value="15" oninput="updateMargins()"></div>
            </div>
        </div>
        
        <div class="config-box">
            <strong>Navigasi & Data</strong>
            <label>Pilih Siswa</label>
            <select id="selectSiswa" onchange="pilihSiswa(this.value)"><option value="">-- Upload file dulu --</option></select>
            <div class="btn-group">
                <button class="btn btn-logo" onclick="document.getElementById('logoIn').click()">Upload Logo</button>
                <button class="btn btn-upload" onclick="document.getElementById('fileIn').click()">Upload Excel</button>
                <button class="btn btn-print" onclick="window.print()">Cetak Rapor</button>
            </div>
            <input type="file" id="logoIn" accept="image/*" style="display:none" onchange="prosesLogo(event)">
            <input type="file" id="fileIn" accept=".xlsx, .xls" style="display:none" onchange="prosesExcel(event)">
        </div>
    </div>
</div>

<div class="rapor-page" id="raporContainer">
    <div class="kop-container">
        <div class="logo-box"><img id="imgLogo" src="" alt="Logo"></div>
        <div class="kop-text">
            <h3>PEMERINTAH KABUPATEN MALANG</h3>
            <h3>DINAS PENDIDIKAN</h3>
            <h2>SMP NEGERI 2 KALIPARE</h2>
            <p>Jl. Raya Banduarjo No. 1099 Sumberpetung Kec. Kalipare Kab. Malang (65166)</p>
        </div>
    </div>

    <div class="judul">LAPORAN HASIL BELAJAR MADRASAH DINIYAH</div>

    <table class="info-table">
        <tr>
            <td width="18%">Nama Siswa</td><td width="2%">:</td>
            <td id="outNama" width="40%" style="font-weight:bold; border-bottom:1px dotted #000">-</td>
            <td>Semester Ganjil</td>
        </tr>
        <tr>
            <td>Kelas</td><td>:</td>
            <td id="outKelas" style="border-bottom:1px dotted #000">-</td>
            <td>Tahun Pelajaran 2025/2026</td>
        </tr>
    </table>

    <table class="main-table">
        <thead>
            <tr>
                <th width="5%">NO</th>
                <th width="25%">MATA PELAJARAN</th>
                <th width="10%">NILAI</th>
                <th>CAPAIAN DESKRIPSI</th>
            </tr>
        </thead>
        <tbody id="tableBody">
            <tr><td align="center">1</td><td>FIQIH</td><td id="n1" align="center"></td><td id="d1"></td></tr>
            <tr><td align="center">2</td><td>AQIDAH AKHLAQ</td><td id="n2" align="center"></td><td id="d2"></td></tr>
            <tr><td align="center">3</td><td>BACA TULIS ALQURAN</td><td id="n3" align="center"></td><td id="d3"></td></tr>
            <tr><td align="center">4</td><td>TAJWID</td><td id="n4" align="center"></td><td id="d4"></td></tr>
            <tr>
                <td colspan="2" align="right"><strong>JUMLAH</strong></td>
                <td id="outTotal" align="center"></td>
                <td id="descTotal" style="font-style: italic; font-size: 9pt;"></td>
            </tr>
            <tr>
                <td colspan="2" align="right"><strong>RATA-RATA</strong></td>
                <td id="outRata" align="center"></td>
                <td id="descRata" style="font-style: italic; font-size: 9pt;"></td>
            </tr>
            <tr>
                <td colspan="2" align="right"><strong>PERINGKAT</strong></td>
                <td id="outRank" align="center" style="font-weight: bold;"></td>
                <td style="background:#eee"></td>
            </tr>
        </tbody>
    </table>

    <div style="display: flex; gap: 15px;">
        <table class="main-table" style="width: 40%;">
            <thead><tr><th>No</th><th>Ketidakhadiran</th><th>JUMLAH</th></tr></thead>
            <tbody>
                <tr><td align="center">1</td><td>Alpha</td><td id="a1" align="center"></td></tr>
                <tr><td align="center">2</td><td>Ijin</td><td id="a2" align="center"></td></tr>
                <tr><td align="center">3</td><td>Sakit</td><td id="a3" align="center"></td></tr>
            </tbody>
        </table>
        <table class="main-table" style="width: 60%;">
            <thead><tr><th>Catatan Wali Kelas</th></tr></thead>
            <tbody><tr><td id="outCatatan" style="height: 90px; vertical-align: top;"></td></tr></tbody>
        </table>
    </div>

    <table class="footer-table">
        <tr>
            <td width="33%">Wali Murid<br><br><br><br>( ......................... )</td>
            <td width="33%">Wali Kelas<br><br><br><br><strong id="outWali">( ......................... )</strong></td>
            <td>Kalipare, 19 Desember 2025<br>Kepala Sekolah<br><br><br><strong><u>ELISABET DWI BUDIATI, S.Pd</u></strong><br>NIP. 197507312002122005</td>
        </tr>
    </table>
</div>

<script>
    let dataSiswaGlobal = [];

    // FUNGSI UPDATE SEMUA MARGIN
    function updateMargins() {
        const t = document.getElementById('mTop').value;
        const b = document.getElementById('mBottom').value;
        const l = document.getElementById('mLeft').value;
        const r = document.getElementById('mRight').value;
        
        const page = document.getElementById('raporContainer');
        page.style.paddingTop = t + "mm";
        page.style.paddingBottom = b + "mm";
        page.style.paddingLeft = l + "mm";
        page.style.paddingRight = r + "mm";
    }

    // FUNGSI TERBILANG
    function terbilang(n) {
        const bilangan = ["", "Satu", "Dua", "Tiga", "Empat", "Lima", "Enam", "Tujuh", "Delapan", "Sembilan", "Sepuluh", "Sebelas"];
        let temp = ""; n = parseFloat(n);
        const angka = Math.floor(n);
        const desimal = Math.round((n - angka) * 100);
        function hitung(v) {
            if (v < 12) return " " + bilangan[v];
            else if (v < 20) return hitung(v - 10) + " Belas";
            else if (v < 100) return hitung(Math.floor(v / 10)) + " Puluh" + hitung(v % 10);
            else if (v < 200) return " Seratus" + hitung(v - 100);
            else if (v < 1000) return hitung(Math.floor(v / 100)) + " Ratus" + hitung(v % 100);
            return "";
        }
        temp = hitung(angka);
        if (desimal > 0) {
            let dStr = desimal.toString();
            temp += " Koma " + (bilangan[dStr[0]] || "Nol") + " " + (bilangan[dStr[1]] || "");
        }
        return temp.trim();
    }

    function generateDeskripsiLengkap(nilai, mapel) {
        if (!nilai) return "-";
        if (nilai >= 90) return `Sangat baik. Menunjukkan penguasaan mendalam pada materi ${mapel}. Perlu mempertahankan konsistensi belajar.`;
        if (nilai >= 80) return `Baik. Sudah mampu menguasai kompetensi ${mapel}, namun ketelitian pada rincian kecil perlu ditingkatkan secara maksimal.`;
        if (nilai >= 70) return `Cukup. Memiliki pemahaman dasar pada ${mapel}, namun kemampuan praktik belum tercapai maksimal.`;
        return `Perlu bimbingan intensif pada materi ${mapel}.`;
    }

    function prosesLogo(event) {
        const reader = new FileReader();
        reader.onload = e => { 
            const img = document.getElementById('imgLogo');
            img.src = e.target.result; img.style.display = 'block'; 
        };
        reader.readAsDataURL(event.target.files[0]);
    }

    function prosesExcel(e) {
        const reader = new FileReader();
        reader.onload = (event) => {
            const workbook = XLSX.read(new Uint8Array(event.target.result), {type: 'array'});
            let json = XLSX.utils.sheet_to_json(workbook.Sheets[workbook.SheetNames[0]]);
            json = json.map(s => {
                const tot = (parseFloat(s.Fiqih) || 0) + (parseFloat(s.Aqidah) || 0) + (parseFloat(s.BTQ) || 0) + (parseFloat(s.Tajwid) || 0);
                return { ...s, total: tot };
            });
            const sorted = [...json].sort((a, b) => b.total - a.total);
            dataSiswaGlobal = json.map(s => ({ ...s, rank: sorted.findIndex(x => x.total === s.total) + 1 }));
            const sel = document.getElementById('selectSiswa');
            sel.innerHTML = dataSiswaGlobal.map((s, i) => `<option value="${i}">${s.Nama_Siswa}</option>`).join('');
            isiData(dataSiswaGlobal[0]);
        };
        reader.readAsArrayBuffer(e.target.files[0]);
    }

    function pilihSiswa(i) { if(i !== "") isiData(dataSiswaGlobal[i]); }

    function isiData(d) {
        document.getElementById('outNama').innerText = d.Nama_Siswa || "-";
        document.getElementById('outKelas').innerText = d.Kelas || "-";
        document.getElementById('outWali').innerText = `( ${d.Wali_Kelas || "..."} )`;
        const n = [d.Fiqih, d.Aqidah, d.BTQ, d.Tajwid];
        const names = ["Fiqih", "Aqidah Akhlaq", "BTQ", "Tajwid"];
        for(let i=0; i<4; i++) {
            const val = parseFloat(n[i]) || 0;
            document.getElementById(`n${i+1}`).innerText = val;
            document.getElementById(`d${i+1}`).innerText = generateDeskripsiLengkap(val, names[i]);
        }
        const rata = (d.total / 4).toFixed(2);
        document.getElementById('outTotal').innerText = d.total;
        document.getElementById('descTotal').innerText = terbilang(d.total);
        document.getElementById('outRata').innerText = rata;
        document.getElementById('descRata').innerText = terbilang(rata);
        document.getElementById('outRank').innerText = `${d.rank} dari ${dataSiswaGlobal.length}`;
        document.getElementById('a1').innerText = (d.Alpha || 0) + " hari";
        document.getElementById('a2').innerText = (d.Ijin || 0) + " hari";
        document.getElementById('a3').innerText = (d.Sakit || 0) + " hari";
        document.getElementById('outCatatan').innerText = d.Catatan || "-";
    }
</script>
</body>
</html>
