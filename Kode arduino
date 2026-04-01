// Definisi Pin untuk masing-masing sisi: {Pin Merah, Pin Kuning, Pin Hijau}
const int pinUtara[3]   = {13, 12, 11};
const int pinTimur[3]   = {10, 9, 8};
const int pinSelatan[3] = {7, 6, 5};
const int pinBarat[3]   = {4, 3, 2};

void setup() {
  // Mengatur semua pin lampu sebagai OUTPUT
  for (int i = 0; i < 3; i++) {
    pinMode(pinUtara[i], OUTPUT);
    pinMode(pinTimur[i], OUTPUT);
    pinMode(pinSelatan[i], OUTPUT);
    pinMode(pinBarat[i], OUTPUT);
  }
  
  // Kondisi Default: Semua lampu merah menyala sebelum sistem berputar
  kondisiAwalSemuaMerah();
}

void loop() {
  // Looping bergiliran searah jarum jam
  aktifkanSimpang(pinUtara);   // 1. Utara
  aktifkanSimpang(pinTimur);   // 2. Timur
  aktifkanSimpang(pinSelatan); // 3. Selatan
  aktifkanSimpang(pinBarat);   // 4. Barat
}

// Fungsi untuk mengatur kondisi default (Semua Merah ON, sisanya OFF)
void kondisiAwalSemuaMerah() {
  // Sisi Utara
  digitalWrite(pinUtara[0], HIGH); // Merah ON
  digitalWrite(pinUtara[1], LOW);  // Kuning OFF
  digitalWrite(pinUtara[2], LOW);  // Hijau OFF
  
  // Sisi Timur
  digitalWrite(pinTimur[0], HIGH); 
  digitalWrite(pinTimur[1], LOW);  
  digitalWrite(pinTimur[2], LOW);  
  
  // Sisi Selatan
  digitalWrite(pinSelatan[0], HIGH); 
  digitalWrite(pinSelatan[1], LOW);  
  digitalWrite(pinSelatan[2], LOW);  
  
  // Sisi Barat
  digitalWrite(pinBarat[0], HIGH); 
  digitalWrite(pinBarat[1], LOW);  
  digitalWrite(pinBarat[2], LOW);  
}

// Fungsi modular untuk mengaktifkan satu simpang
void aktifkanSimpang(const int pinSisi[]) {
  int pinMerah = pinSisi[0];
  int pinKuning = pinSisi[1];
  int pinHijau = pinSisi[2];

  // 1. Matikan lampu Merah, nyalakan lampu Hijau
  digitalWrite(pinMerah, LOW);
  digitalWrite(pinHijau, HIGH);
  delay(5000); // Lampu Hijau menyala selama 5 detik

  // 2. Matikan lampu Hijau, mulai transisi ke Kuning
  digitalWrite(pinHijau, LOW);

  // 3. Efek lampu Kuning kedip 3 kali
  for (int i = 0; i < 3; i++) {
    digitalWrite(pinKuning, HIGH);
    delay(300); // Menyala 0.3 detik
    digitalWrite(pinKuning, LOW);
    delay(300); // Mati 0.3 detik
  }

  // 4. Lampu Kuning menyala stabil selama 2 detik
  digitalWrite(pinKuning, HIGH);
  delay(2000);
  digitalWrite(pinKuning, LOW);

  // 5. Kembali ke kondisi default (Lampu Merah menyala kembali)
  digitalWrite(pinMerah, HIGH);
}
