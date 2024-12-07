
<style>
  body {
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #f4f4f4;
}

.container {
  text-align: center;
  background: white;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
}

.customizer {
  display: flex;
  gap: 20px;
  margin-top: 20px;
}

.controls {
  flex: 1;
}

.controls label {
  display: block;
  margin: 10px 0 5px;
}

.preview {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: center;
}

.tshirt {
  width: 200px;
  height: 250px;
  background-color: #fff;
  border: 2px solid #ddd;
  border-radius: 5px;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}

#custom-text-preview {
  position: absolute;
  font-size: 20px;
  color: black;
  text-align: center;
}

</style>

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>T-Shirt Customizer</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div class="container">
    <h1>T-Shirt Customizer</h1>
    <div class="customizer">
      <div class="controls">
        <label for="tshirt-color">T-Shirt Color:</label>
        <input type="color" id="tshirt-color" value="#ffffff">
        <label for="custom-text">Custom Text:</label>
        <input type="text" id="custom-text" placeholder="Enter your text">

        <label for="text-color">Text Color:</label>
        <input type="color" id="text-color" value="#000000">

        <label for="text-size">Text Size:</label>
        <input type="range" id="text-size" min="10" max="50" value="20">
      </div>

      <div class="preview">
        <div class="tshirt" id="tshirt-preview">
          <p id="custom-text-preview">Your Text Here</p>
        </div>
      </div>
    </div>
  </div>

<script>
const tshirtColorInput = document.getElementById('tshirt-color');
const customTextInput = document.getElementById('custom-text');
const textColorInput = document.getElementById('text-color');
const textSizeInput = document.getElementById('text-size');
const tshirtPreview = document.getElementById('tshirt-preview');
const customTextPreview = document.getElementById('custom-text-preview');

tshirtColorInput.addEventListener('input', () => {
  tshirtPreview.style.backgroundColor = tshirtColorInput.value;
});
customTextInput.addEventListener('input', () => {
  customTextPreview.textContent = customTextInput.value || "Your Text Here";
});
textColorInput.addEventListener('input', () => {
  customTextPreview.style.color = textColorInput.value;
});
textSizeInput.addEventListener('input', () => {
  customTextPreview.style.fontSize = `${textSizeInput.value}px`;
});
  </script>
</body>
</html>
