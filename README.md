<!DOCTYPE html>
<html>
<head>
  <title>Webcam Demo (With Consent)</title>
</head>
<body>
  <h2>Webcam Demo</h2>
  <p>This demo asks for permission and does not store or transmit video.</p>
  <video id="video" autoplay playsinline width="400"></video>

  <script>
    async function startCamera() {
      try {
        const stream = await navigator.mediaDevices.getUserMedia({ video: true });
        document.getElementById("video").srcObject = stream;
      } catch (err) {
        alert("Camera access denied or unavailable.");
      }
    }
    startCamera();
  </script>
</body>
</html>
