<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Siapkah Kau 'Tuk Jatuh Cinta Lagi - Hivi!</title>
  <style>
    /* Video background fullscreen tanpa suara */
    #bgVideo {
      position: fixed;
      top: 0; left: 0;
      width: 100vw;
      height: 100vh;
      object-fit: cover;
      z-index: -1;
      filter: brightness(0.6);
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background-color: #4b2df5;
      color: white;
      padding: 20px;
      max-width: 600px;
      margin-left: auto;
      margin-right: auto;
      position: relative;
      z-index: 1;
    }

    h1, h2 {
      text-align: center;
      margin: 0.5em 0;
    }

    .lyrics {
      
      padding: 15px 20px;
      border-radius: 8px;
      box-shadow: 0 0 10px rgba(0,0,0,0.3);
      white-space: pre-line;
      line-height: 1.0;
      font-size: 29px;
      margin-bottom: 20px;
    }

    audio {
      display: block;
      margin: 0 auto;
      width: 100%;
      max-width: 600px;
      outline: none;
    }
  </style>
</head>
<body>

  <!-- Video background tanpa suara -->
  <video id="bgVideo" autoplay muted loop playsinline>
    <source src="c:\Users\hasbi\Videos\Captures\Video tanpa judul ‐ Dibuat dengan Clipchamp.mp4" type="video/mp4" />
    Browser Anda tidak mendukung video.
  </video>

  <h1>Siapkah Kau 'Tuk Jatuh Cinta Lagi'</h1>
  <h2>Hivi!</h2>
  <div class="lyrics">
    Kini Ku Tak Lagi Dengannya<br />
    Sudah Tak Ada Lagi Rasa<br />
    Antara Aku Dengan Dia<br />
    Siapkah Kau Bertahta, Dihatiku Adinda<br />
    Karena Ini Saat Yang Tepat<br />
    Untuk Singgah Dihatiku<br />
  </div>

  <!-- Audio musik dengan suara -->
  <audio id="myAudio" controls>
    <source src="c:\Users\hasbi\Downloads\HIVI! - Siapkah Kau 'Tuk Jatuh Cinta Lagi (Official Lyric Video).mp3" type="audio/mpeg" />
    Browser Anda tidak mendukung elemen audio.
  </audio>

  <script>
    const audio = document.getElementById('myAudio');
    const startTime = 83;  // mulai dari detik ke-83
    const endTime = 110;   // berhenti di detik ke-103

    audio.addEventListener('loadedmetadata', () => {
      audio.currentTime = startTime;
      const playPromise = audio.play();
      if (playPromise !== undefined) {
        playPromise.catch(error => {
          console.log('Autoplay gagal:', error);
          // Jika autoplay gagal, pengguna bisa klik tombol play manual
        });
      }
    });

    audio.addEventListener('timeupdate', () => {
      if (audio.currentTime >= endTime) {
        audio.pause();
      }
    });
  </script>

</body>
</html>
