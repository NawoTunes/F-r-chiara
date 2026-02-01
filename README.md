<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<style>
  body { 
    margin: 0; padding: 0; height: 100vh; width: 100vw; 
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    background: #fff5f7; font-family: -apple-system, sans-serif; overflow: hidden;
  }
  .aesthetic-bg {
    position: fixed; top: 0; left: 0; width: 100%; height: 100%;
    background: linear-gradient(135deg, #fbc2eb 0%, #a6c1ee 100%);
    opacity: 0.4; z-index: 1;
  }
  .content { position: relative; z-index: 2; text-align: center; width: 100%; }
  h1 { color: #5a5a5a; font-size: 24px; padding: 20px; line-height: 1.4; }
  .btn-area { position: relative; width: 100%; height: 120px; margin-top: 20px; }
  button { 
    padding: 15px 35px; font-size: 18px; border-radius: 50px; border: none; font-weight: bold;
    position: absolute; box-shadow: 0 4px 15px rgba(0,0,0,0.1); touch-action: none;
  }
  #yes { background: #ff758c; color: white; left: 50%; transform: translateX(-110%); }
  #no { background: #ffffff; color: #ff758c; left: 50%; transform: translateX(10%); transition: 0.1s; }
  .final-screen { 
    display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; 
    background: #fff; z-index: 100; flex-direction: column; align-items: center; justify-content: center; text-align: center;
  }
</style>
</head>
<body>
  <div class="aesthetic-bg"></div>
  <div id="main-ui" class="content">
    <h1>Chiara, willst du mein Valentine sein? ❤️</h1>
    <div class="btn-area">
      <button id="yes" onclick="askQuestion()">Yes</button>
      <button id="no" onclick="wrongAnswer()">No</button>
    </div>
  </div>

  <div id="final-ui" class="final-screen">
    <h1 style="color: #ff758c;">Besser so für dich 😏❤️</h1>
    <img src="https://media3.giphy.com/media/v1.Y2lkPTc5MGI3NjExOHpueGZid3ByYmZ3NXh4eHh4eHh4eHh4eHh4eHh4eHh4eHh4eCZlcD12MV9pbnRlcm5hbF9naWZfYnlfaWQmY3Q9Zw/T86knKzgnYI6s/giphy.gif" style="width:85%; border-radius:20px;">
  </div>

  <script>
    function wrongAnswer() {
      alert("wrong answer dumbass 🙄");
      const b = document.getElementById('no');
      const x = Math.random() * (window.innerWidth - b.offsetWidth - 40) + 20;
      const y = Math.random() * (window.innerHeight - b.offsetHeight - 40) + 20;
      b.style.position = 'fixed'; b.style.left = x + 'px'; b.style.top = y + 'px'; b.style.transform = 'none';
    }

    function askQuestion() {
      let response = prompt("Warum willst du mit dem einzigartigen Nawo Tunes ausgehen? (Nenn mir mindestens 3 Wörter!)");
      
      if (response) {
        // Zählt die Wörter in der Antwort
        const wordCount = response.trim().split(/\s+/).filter(word => word.length > 0).length;
        
        if (wordCount >= 3) {
          document.getElementById('main-ui').style.display = 'none';
          document.getElementById('final-ui').style.display = 'flex';
        } else {
          alert("Nur " + wordCount + " Wörter? Das reicht dem einzigartigen Nawo Tunes nicht. Streng dich an! 😘");
        }
      }
    }
  </script>
</body>
</html>
