<h3>Pilih Kendaraan:</h3>
<div class="logo-slider" id="logoSlider"></div>
.logo-slider {
  display: flex;
  overflow-x: auto;
  gap: 12px;
  padding: 10px 0;
  margin-bottom: 20px;
}

.logo-slider img {
  width: 80px;
  height: 80px;
  object-fit: contain;
  border: 2px solid transparent;
  border-radius: 10px;
  cursor: pointer;
  transition: 0.3s;
}

.logo-slider img:hover {
  border-color: #007bff;
}const kendaraanList = [
  { nama: "Motor", ukuran: "Kecil", logo: "assets/logo/yamaha.png" },
  { nama: "Motor", ukuran: "Besar", logo: "assets/logo/honda.png" },
  { nama: "Mobil", ukuran: "Sedang", logo: "assets/logo/toyota.png" },
  { nama: "Mobil", ukuran: "Besar", logo: "assets/logo/suzuki.png" },
];function tampilkanLogoSlider() {
  const slider = document.getElementById("logoSlider");
  slider.innerHTML = "";

  kendaraanList.forEach(k => {
    const img = document.createElement("img");
    img.src = k.logo;
    img.alt = `${k.nama} ${k.ukuran}`;
    img.onclick = () => {
      jenisKendaraan = k.nama.toLowerCase();
      ukuranKendaraan = k.ukuran.toLowerCase();
      updateRingkasan();
    };
    slider.appendChild(img);
  });
}window.onload = function () {
  tampilkanLogoSlider();
  updateRingkasan();
  tampilkanRiwayat();
};
