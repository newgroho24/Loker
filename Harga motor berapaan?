<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Akses Kamera</title>
</head>
<body>
    <h1>Akses Kamera dengan Izin</h1>
    <video id="video" width="640" height="480" autoplay></video>
    <button id="start-camera">Mulai Kamera</button>

    <script>
        // Elemen video untuk menampilkan stream kamera
        const video = document.getElementById('video');

        // Tombol untuk memulai kamera
        const startCameraButton = document.getElementById('start-camera');

        // Event listener untuk tombol
        startCameraButton.addEventListener('click', async () => {
            try {
                // Meminta izin akses kamera
                const stream = await navigator.mediaDevices.getUserMedia({ video: true });

                // Menampilkan stream kamera ke elemen video
                video.srcObject = stream;
            } catch (error) {
                console.error('Error mengakses kamera:', error);
                alert('Tidak dapat mengakses kamera. Pastikan Anda memberikan izin.');
            }
        });
    </script>
</body>
</html>