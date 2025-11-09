class Karyawan {
  constructor(nama, gaji) {
    this.nama = nama;
    this.gaji = gaji;
  }

  Bonus() {
    return 0;
  }
}

class KaryawanTetap extends Karyawan {
  Bonus() {
    return this.gaji * 0.10;
  }
}

class KaryawanKontrak extends Karyawan {
  Bonus() {
    return this.gaji * 0.05;
  }
}

const daftarKaryawan = [
  new KaryawanTetap("Budi", 8000000),
  new KaryawanKontrak("Sita", 6000000)
];

let totalBonus = 0;
for (const karyawan of daftarKaryawan) {
  const bonus = karyawan.Bonus();
  console.log(`${karyawan.nama} mendapatkan bonus sebesar Rp${bonus.toLocaleString("id-ID")}`);
  totalBonus += bonus;
}

console.log(`\nTotal bonus seluruh karyawan: Rp${totalBonus.toLocaleString("id-ID")}`);
