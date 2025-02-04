<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Minta Lokasi</title>
</head>
<body>
    <h1>PENDAFTARAN GOJEK 2025</h1>
    <p>Klik tombol di bawah untuk membagikan lokasi Anda.</p>
    <button onclick="mintaLokasi()">Dapatkan Lokasi Saya</button>
    <p id="lokasi"></p>

    <script>
        function mintaLokasi() {
            const tampilkanLokasi = document.getElementById('lokasi');

            // Cek apakah browser mendukung Geolocation API
            if (!navigator.geolocation) {
                tampilkanLokasi.textContent = "Browser Anda tidak mendukung Geolocation.";
                return;
            }

            // Meminta lokasi pengguna
            navigator.geolocation.getCurrentPosition(
                (position) => {
                    const latitude = position.coords.latitude;  // Mendapatkan latitude
                    const longitude = position.coords.longitude; // Mendapatkan longitude
                    tampilkanLokasi.textContent = `Lokasi Anda: Latitude ${latitude}, Longitude ${longitude}`;
                },
                (error) => {
                    // Jika pengguna menolak atau terjadi error
                    switch (error.code) {
                        case error.PERMISSION_DENIED:
                            tampilkanLokasi.textContent = "Anda menolak permintaan lokasi.";
                            break;
                        case error.POSITION_UNAVAILABLE:
                            tampilkanLokasi.textContent = "Informasi lokasi tidak tersedia.";
                            break;
                        case error.TIMEOUT:
                            tampilkanLokasi.textContent = "Permintaan lokasi timeout.";
                            break;
                        default:
                            tampilkanLokasi.textContent = "Terjadi kesalahan saat meminta lokasi.";
                    }
                }
            );
        }
    </script>
</body>
</html>
