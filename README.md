<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>The Official YAFS Website</title>
  <script src="https://cdnjs.cloudflare.com/ajax/libs/push.js/1.0.12/push.min.js"></script>
</head>
<body>
  <h1>Welcome to the Official YAFS Website</h1>
  <button id="notifyBtn">Send Notification</button>

  <script>
    document.addEventListener("DOMContentLoaded", function () {
      const notifyBtn = document.getElementById("notifyBtn");

      notifyBtn.addEventListener("click", function () {
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
          Push.Permission.request(
            function () {
              // Permission granted
              Push.create("Hello world!", {
                body: "Welcome to the YAFS website!",
                timeout: 4000,
                onClick: function () {
                  window.focus();
                  this.close();
                }
              });
            },
            function () {
              // Permission denied
              alert("Notification permission denied.");
            }
          );
        }
      });
    });
  </script>
</body>
</html>
