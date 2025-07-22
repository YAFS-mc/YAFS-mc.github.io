<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>The Official YAFS Website</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/push.js/1.0.12/push.min.js"></script>
</head>
<body>
  <h1>Welcome to the Official YAFS Website</h1>

  <script>
    document.addEventListener("DOMContentLoaded", function () {
      if (Push.Permission.has()) {
        Push.create("Hello world!", {
          body: "Welcome to the YAFS website!",
          timeout: 4000,
          onClick: function () {
            window.focus();
            this.close();
          }
        });
      } else {
        Push.Permission.request();
      }
    });
  </script>
</body>
</html>
