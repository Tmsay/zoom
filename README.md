
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Zoom Redirect</title>
  <script>
    const urlParams = new URLSearchParams(window.location.search);
    const uid = urlParams.get('uid');

    fetch('https://script.google.com/macros/s/AKfycbzIQhWGuL03HUnfRM2DLQAGY1NLohWUFaQuzZ7XnZWwF3k91PJvR1WDURyOrsvnvk97/exec', {
      method: 'POST',
      mode: 'no-cors',
      headers: {
        'Content-Type': 'application/json'
      },
      body: JSON.stringify({
        uid: uid,
        timestamp: new Date().toISOString(),
        userAgent: navigator.userAgent,
        page: window.location.href
      })
    });

    setTimeout(() => {
      window.location.href = 'https://zoom.us/j/YOUR_MEETING_ID';
    }, 2000);
  </script>
</head>
<body>
  <h2 style="text-align:center; font-family:sans-serif; margin-top:50px;">
    Переход в Zoom...<br />
    Пожалуйста, подождите пару секунд
  </h2>
</body>
</html>
