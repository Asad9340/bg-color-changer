# bg-color-changer

```javascript

<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Bg Color Changer</title>
  </head>
  <style>
    .container {
      height: 80vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
    }
    .btn-container {
      display: flex;
      gap: 40px;
    }
    .btn {
      padding: 10px 25px;
      font-size: 20px;
      border-radius: 5px;
      outline: none;
      border: 0;
    }
    .btn-1,
    .btn-2 {
      background-color: rgb(7, 7, 22);
      color: white;
    }
    .btn-1:hover,
    .btn-2:hover {
      background-color: rgb(22, 22, 24);
    }
  </style>
  <body style="background-color: #212121; color: white">
    <div class="container">
      <h1>Background Collor Changer</h1>
      <div class="btn-container">
        <button class="btn btn-1">Start</button>
        <button class="btn btn-2">Stop</button>
      </div>
    </div>
  </body>
  <script>
    const randomColor = function () {
      const value = '0123456789ABCDEF';
      let color = '#';
      for (let i = 0; i < 6; i++) {
        const randomNumber = Math.floor(Math.random() * 16);
        color += value[randomNumber];
      }
      return color;
    };
    let stopChange;
    document.querySelector('.btn-1').addEventListener('click', () => {
       stopChange = setInterval(() => {
        document.body.style.backgroundColor = randomColor();
      }, 1000);
    });
    document.querySelector('.btn-2').addEventListener('click', () => {
      clearInterval(stopChange);
      stopChange='';
    });
  </script>
</html>

```
