<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>The Official YAFS Website</title>
</head>
<body>
  <h1>Welcome to the Official YAFS Website</h1>
  <button id="downloadBtn">S2 World Download</button>

  <script>
    document.addEventListener("DOMContentLoaded", function () {
      const downloadBtn = document.getElementById("downloadBtn");

      downloadBtn.addEventListener("click", function () {
        const link = document.createElement('a');
        link.href = '/World-Downloads/yafs-s2.zip'; // Non Existant file
        link.download = 'yafs-s2.zip'; 
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
      });
    });
  </script>
</body>
</html>
