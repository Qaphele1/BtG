<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Sign In / Sign Up</title>
  <style>
    /* Basic Reset */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: Arial, sans-serif;
    }

    body {
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      background: #f0f4f8;
    }

    /* Container Setup */
    .container {
      position: relative;
      width: 800px;
      height: 500px;
      background: #fff;
      box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
      border-radius: 10px;
      overflow: hidden;
      display: flex;
    }

    /* Forms */
    .form-container {
      width: 50%;
      height: 100%;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      padding: 20px;
      transition: all 0.6s ease-in-out;
    }

    .form-container form {
      width: 100%;
      max-width: 300px;
      display: flex;
      flex-direction: column;
      align-items: center;
    }

    .form-container h1 {
      margin-bottom: 20px;
      font-size: 24px;
    }

    input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #ddd;
      border-radius: 5px;
      font-size: 14px;
    }

    button {
      background: #ffa600;
      border: none;
      padding: 10px 20px;
      color: #000;
      font-weight: bold;
      cursor: pointer;
      transition: 0.3s ease;
      border-radius: 20px;
    }


    /* Hide Forms Dynamically */
    .form-container.hidden {
      display: none;
    }

    /* Overlay Panel */
    .overlay-container {
      position: relative;
      width: 50%;
      background: #064669;
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      flex-direction: column;
      padding: 20px;
    }

    .overlay-container h1 {
      font-size: 24px;
      margin-bottom: 15px;
    }

    p {
      margin: 10px 0 20px;
    }

    .overlay-container button {
      background: #ffa600;
      color: #000;
      padding: 10px 20px;
      border: none;
      border-radius: 20px;
      cursor: pointer;
      transition: 0.3s ease;
    }

    .overlay-container button:hover {
      background: #ffa600;
    }

  </style>
</head>
<body>
  <div class="container">
    <!-- Forms -->
    <div class="form-container sign-in-container" id="signInForm">
      <form action="#">
        <h1>Log In</h1>
        <input type="text" placeholder="Username" required />
        <input type="password" placeholder="Password" required />
        <button>Sign In</button>
      </form>
    </div>

    <div class="form-container sign-up-container hidden" id="signUpForm">
      <form action="#">
        <h1>Create Account</h1>
        <input type="email" placeholder="Email" required />
        <input type="password" placeholder="Password" required />
        <input type="password" placeholder="Confirm Password" required />
        <button>Sign Up</button>
      </form>
    </div>

    <!-- Overlay -->
    <div class="overlay-container">
      <h1 id="overlayHeading">Hi there!</h1>
      <p id="overlayText">Do not have an account yet? Click below to create an account</p>
      <button id="toggleForm">Sign Up</button>
    </div>
  </div>

  <script>
    // Toggle Between Forms
    const signInForm = document.getElementById('signInForm');
    const signUpForm = document.getElementById('signUpForm');
    const toggleFormButton = document.getElementById('toggleForm');
    const overlayHeading = document.getElementById('overlayHeading');
    const overlayText = document.getElementById('overlayText');

    let isSignInActive = true;

    toggleFormButton.addEventListener('click', () => {
      if (isSignInActive) {
        // Show Sign Up Form
        signInForm.classList.add('hidden');
        signUpForm.classList.remove('hidden');
        overlayHeading.innerText = 'Welcome Back!';
        overlayText.innerText = 'If you have an account with us, please sign in using your info';
        toggleFormButton.innerText = 'Sign In';
      } else {
        // Show Sign In Form
        signUpForm.classList.add('hidden');
        signInForm.classList.remove('hidden');
        overlayHeading.innerText = 'Hi there!';
        overlayText.innerText = 'Do not have an account yet? Click below to create an account';
        toggleFormButton.innerText = 'Sign Up';
      }

      isSignInActive = !isSignInActive;
    });
  </script>
</body>
</html>
