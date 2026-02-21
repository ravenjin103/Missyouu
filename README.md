<!DOCTYPE html>
<html>
<head>
<title>Miss Mo Ba?</title>
<style>
  body {
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    background-color: #f0f0f0; /* Default background is light gray */
    margin: 0;
    text-align: center;
    padding: 10px;
    box-sizing: border-box;
    transition: background-color 0.5s ease; /* Smooth transition for background color */
  }
  .question-container {
    display: block; /* Visible by default */
    text-align: center;
    transition: opacity 0.5s ease; /* Smooth fade-out */
  }
  .question {
    font-size: 3.5em;
    font-weight: bold;
    margin-bottom: 40px;
    color: #222;
    text-shadow: 2px 2px 4px rgba(0,0,0,0.2);
  }
  .buttons {
    display: flex;
    gap: 30px;
    margin-bottom: 50px;
    justify-content: center;
  }
  .button {
    padding: 20px 40px;
    font-size: 1.8em;
    border: none;
    border-radius: 10px;
    cursor: pointer;
    transition: background-color 0.3s ease, transform 0.2s ease, box-shadow 0.2s ease;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
  }
  .button:hover {
    transform: translateY(-3px);
    box-shadow: 0 6px 12px rgba(0,0,0,0.3);
  }
  .no-button {
    background-color: #e74c3c;
    color: white;
  }
  .no-button:hover {
    background-color: #c0392b;
  }
  .yes-button {
    background-color: #2ecc71;
    color: white;
  }
  .yes-button:hover {
    background-color: #27ae60;
  }
  .message {
    font-size: 1.8em; /* Slightly smaller for error, more direct */
    color: #e74c3c;
    margin-top: 30px;
    font-weight: bold;
    opacity: 0; /* Hidden by default */
    transition: opacity 0.3s ease; /* Smooth fade-in */
  }
  .message.show {
      opacity: 1;
  }
  .video-container {
    display: none; /* Hidden until "Yes" is clicked */
    position: fixed; /* Position fixed to take up full screen behind other content initially */
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: black; /* Ensure black background for video */
    justify-content: center;
    align-items: center;
    opacity: 0; /* Hidden initially, fades in */
    transition: opacity 0.5s ease;
    z-index: 1000; /* Ensure video is on top */
  }
  .video-container.show {
      opacity: 1;
      display: flex; /* Only show when needed */
  }

  video {
    width: 100%;
    height: 100%;
    object-fit: contain; /* CHANGED: No distortion, entire video content is visible */
    display: block;
    /* Removed all transform: scaleX and object-position settings */
  }

  /* Fullscreen specific styles to ensure black background */
  :fullscreen {
      background-color: black;
  }
  :-webkit-full-screen {
      background-color: black;
  }
  video:fullscreen {
      width: 100vw;
      height: 100vh;
      object-fit: contain; /* CHANGED: No distortion, entire video content is visible */
    /* Removed all transform: scaleX and object-position settings */
  }
  video::-webkit-full-screen {
      width: 100vw;
      height: 100vh;
      object-fit: contain; /* CHANGED: No distortion, entire video content is visible */
    /* Removed all transform: scaleX and object-position settings */
  }
</style>
</head>
<body>

  <div class="question-container" id="questionAndButtons">
    <div class="question">Miss mo ba?</div>
    <div class="buttons">
      <button class="button no-button" id="noBtn">No</button>
      <button class="button yes-button" id="yesBtn">Yes</button>
    </div>
  </div>

  <div class="message" id="responseMessage"></div>

  <div class="video-container" id="myVideoContainer">
    <video id="myVideo" controls playsinline>
      <source src="/storage/emulated/0/vnhs/missmo.mp4" type="video/mp4">
      <source src="/storage/emulated/0/vnhs/missmo.webm" type="video/webm">
      Your browser does not support the video tag.
    </video>
  </div>

  <script>
    const noButton = document.getElementById('noBtn');
    const yesButton = document.getElementById('yesBtn');
    const responseMessage = document.getElementById('responseMessage');
    const videoContainer = document.getElementById('myVideoContainer');
    const videoPlayer = document.getElementById('myVideo');
    const questionAndButtons = document.getElementById('questionAndButtons');
    const body = document.body;

    function requestFullScreen(element) {
      if (element.requestFullscreen) {
        element.requestFullscreen();
      } else if (element.webkitRequestFullscreen) { /* Safari */
        element.webkitRequestFullscreen();
      } else if (element.msRequestFullscreen) { /* IE11 */
        element.msRequestFullscreen();
      }
    }

    // --- No Button Logic ---
    noButton.addEventListener('click', () => {
      responseMessage.textContent = "Error: Please click the other button!";
      responseMessage.style.color = '#e74c3c';
      responseMessage.classList.add('show');
      
      videoContainer.classList.remove('show');
      videoPlayer.pause();
      
      if (document.fullscreenElement) {
        document.exitFullscreen();
      } else if (document.webkitExitFullscreen) {
          document.webkitExitFullscreen();
      } else if (document.msExitFullscreen) {
          document.msExitFullscreen();
      }

      body.style.backgroundColor = '#f0f0f0';
    });

    // --- Yes Button Logic ---
    yesButton.addEventListener('click', () => {
      responseMessage.classList.remove('show');
      
      questionAndButtons.style.opacity = '0';
      setTimeout(() => {
        questionAndButtons.style.display = 'none';
      }, 500);

      body.style.backgroundColor = 'black';
      
      videoContainer.classList.add('show');

      videoPlayer.setAttribute('autoplay', 'autoplay');
      videoPlayer.load();

      videoPlayer.play()
        .then(() => {
          requestFullScreen(videoPlayer);
        })
        .catch(error => {
          console.error("Video play or fullscreen failed:", error);
          responseMessage.textContent = "Video requires a tap to play with sound. Tap the video area.";
          responseMessage.style.color = 'white';
          responseMessage.classList.add('show');
          videoPlayer.controls = true;
          
          videoPlayer.muted = true;
          videoPlayer.play().then(() => requestFullScreen(videoPlayer)).catch(e => console.error("Fallback silent play failed", e));
        });
    });

    // --- Fullscreen Exit Handling ---
    const exitFullscreenHandler = () => {
        if (!document.fullscreenElement && !document.webkitFullscreenElement) {
            videoPlayer.pause();

            videoContainer.classList.remove('show');
            setTimeout(() => {
                videoContainer.style.display = 'none';
                videoPlayer.removeAttribute('autoplay');
                videoPlayer.currentTime = 0;
                videoPlayer.controls = false;
                videoPlayer.muted = false;
            }, 500);

            questionAndButtons.style.display = 'block';
            setTimeout(() => {
                questionAndButtons.style.opacity = '1';
            }, 10);

            body.style.backgroundColor = '#f0f0f0';
            responseMessage.classList.remove('show');
        }
    };
    document.addEventListener('fullscreenchange', exitFullscreenHandler);
    document.addEventListener('webkitfullscreenchange', exitFullscreenHandler);
  </script>

</body>
</html>

