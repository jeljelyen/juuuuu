<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>sTEM 1103</title>
  <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    @keyframes dance {
      0% { transform: rotate(0deg); }
      25% { transform: rotate(10deg); }
      50% { transform: rotate(-10deg); }
      75% { transform: rotate(10deg); }
      100% { transform: rotate(0deg); }
    }
    .dancing {
      animation: dance 0.5s infinite;
    }
    .uppercase-message {
      text-transform: uppercase;
    }
  </style>
</head>
<body class="bg-pink-300 text-white font-mono flex flex-col items-center justify-center min-h-screen p-4">

  <h1 class="text-4xl mb-4 text-violet-300 animate-bounce"> TO STEM 1103</h1>

  <button id="partyBtn" class="bg-violet-600 hover:bg-pink-700 text-white font-bold py-2 px-4 rounded shadow-lg mb-6 animate-pulse">
    CLICK FOR CHAOS 🎉
  </button>

  <div id="celebration" class="hidden flex flex-col items-center gap-4">
    <!-- Local images: Ensure that photo1.jpg and photo2.jpg are in the same directory as this HTML file -->
    <img src="photo1.jpg" alt="Local Class Photo One" class="w-80 h-auto rounded-lg shadow-md">
    <img src="photo2.jpg" alt="Local Class Photo Two" class="w-96 h-auto rounded-lg dancing shadow-md">
    
    <h2 class="text-3xl text-pink-900 font-bold">🎓 CONGRATULATIONS 🎓</h2>
    <p class="text-lg text-white mt-4 text-justify max-w-3xl px-4 uppercase-message">
        Parang kailan lang, we walked into this school year na parang clueless kung anong naghihintay satin. Hindi man tayo palaging sabay-sabay sa lahat ng bagay sa pacing ng tasks, sa energy levels, or even sa mood natin sa bawat araw, one thing’s for sure: we’ve all grown, and survived together.
      <br><br>
      Hindi naging madali — puyat, stress, deadlines, sabayang quizzes, labs, at kung anu-ano pa. Pero through it all, we had each other. Hindi lang tayo classmates; naging support system din tayo sa isa’t isa. Yung mga tawanan, sabay-sabay mag-cram, comfort during breakdowns, or kahit simpleng kamustahan — sobrang laking bagay na nun sa bawat isa sa atin. 
      <br><br>
      Thank you sa bawat isa sa inyo. Sa mga tahimik man o maingay, sa mga laging reciting o silent warriors — you all brought something unique sa klase natin. Hindi naging buo ang 1103 kung wala ka. You matter, and your presence truly made this year more meaningful. Minsan makalat, madaldal, at sabog tayo, pero deep inside, I know may malasakit tayo sa isa’t isa. Malayo pa ang lalakbayin natin, pero kung nalampasan natin ‘to nang magkakasama, I know we’ll be okay. STEM 1103, thank you for the memories, the chaos, the care, and the quiet strength.
    </p>
  </div>

  <script>
    const partyBtn = document.getElementById('partyBtn');
    const celebration = document.getElementById('celebration');

    partyBtn.addEventListener('click', () => {
      // Confetti animation for 3 seconds
      const duration = 3 * 1000;
      const animationEnd = Date.now() + duration;
      const defaults = { startVelocity: 30, spread: 360, ticks: 60, zIndex: 999 };

      const interval = setInterval(() => {
        const timeLeft = animationEnd - Date.now();

        if (timeLeft <= 0) {
          clearInterval(interval);
        }

        confetti(Object.assign({}, defaults, {
          particleCount: 50,
          origin: { x: Math.random(), y: Math.random() - 0.2 }
        }));
      }, 250);

      // Reveal the celebration content
      celebration.classList.remove('hidden');
      celebration.scrollIntoView({ behavior: 'smooth' });
      partyBtn.disabled = true;
      partyBtn.innerText = 'ENJOY 🎊';
    });
  </script>

</body>
</html>
