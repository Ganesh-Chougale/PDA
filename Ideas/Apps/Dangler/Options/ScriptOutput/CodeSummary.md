SubPages\DataConverter\DataConverte.html:
```html

```

SubPages\DataConverter\DataConverter.css:
```css

```

SubPages\DataConverter\DataConverter.js:
```js

```

SubPages\Tools.html:
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>My Developer Tools</title>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css"/>
<link rel="stylesheet" href="../style.css">
<link rel="stylesheet" href="Tools.css">
</head>
<body>
<div id="password-protection" class="password-container">
<div class="card p-4 shadow-sm" style="max-width: 400px; width: 100%;">
<h4 class="card-title text-center mb-4">Enter Password to Access Personal Tools</h4>
<div class="mb-3">
<input type="password" class="form-control" id="passwordInput" placeholder="Enter value of PI">
</div>
<button class="btn btn-primary" id="submitPassword">Access Tools</button>
<p id="passwordError" class="text-danger mt-3 d-none">Incorrect password. Please try again.</p>
</div>
</div>
<div id="tools-content" class="container my-5 d-none">
<h1 class="text-center mb-5">My Developer Tools & Utilities</h1>
<div class="row row-cols-1 row-cols-md-2 row-cols-lg-3 g-4 justify-content-center">
<div class="col">
<div class="card h-100 tool-card">
<div class="card-body text-center">
<i class="fas fa-language fa-3x mb-3 text-primary"></i>
<h5 class="card-title">Vocabulary Translator</h5>
<p class="card-text">English, Marathi & Hindi translator.</p>
<a href="./Vocabulary/Vocabulary.html" class="btn btn-outline-primary mt-3">Go to Tool</a>
</div>
</div>
</div>
<div class="col">
<div class="card h-100 tool-card">
<div class="card-body text-center">
<i class="fas fa-brain fa-3x mb-3 text-success"></i>
<h5 class="card-title">Sequencer Memory Booster</h5>
<p class="card-text">Boost your memory and cognitive skills by arranging sequences from CSV data.</p>
<a href="./Sequencer/Sequencer.html" class="btn btn-outline-success mt-3">Go to Tool</a>
</div>
</div>
</div>
<div class="col">
<div class="card h-100 tool-card">
<div class="card-body text-center">
<i class="fas fa-code-branch fa-3x mb-3 text-warning"></i>
<h5 class="card-title">File Differ</h5>
<p class="card-text">Compare & manage file versions.</p>
<a href="./FileDIffer/FileDIffer.html" class="btn btn-outline-warning mt-3">Go to Tool</a>
</div>
</div>
</div>
</div>
</div>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
<script type="module" src="Tools.js"></script>
</body>
</html>
```

SubPages\Tools.js:
```js
import BINGO from "../Assets/Utils/Bingo.js"; 
document.addEventListener('DOMContentLoaded', function () {
const correctPassword = BINGO.PieValue;
const passwordInput = document.getElementById('passwordInput');
const submitPasswordBtn = document.getElementById('submitPassword');
const passwordProtectionDiv = document.getElementById('password-protection');
const card = passwordProtectionDiv.querySelector(".card");
const toolsContentDiv = document.getElementById('tools-content');
const passwordError = document.getElementById('passwordError');
if (sessionStorage.getItem('accessGranted') === 'true') {
passwordProtectionDiv.classList.add('d-none');
toolsContentDiv.classList.remove('d-none');
}
function handleIncorrectPassword() {
passwordInput.value = '';
passwordError.classList.remove('d-none');
card.classList.add('shake');
setTimeout(() => card.classList.remove('shake'), 400);
setTimeout(() => passwordError.classList.add('d-none'), 3000);
}
submitPasswordBtn.addEventListener('click', function () {
submitPasswordBtn.disabled = true;
setTimeout(() => { submitPasswordBtn.disabled = false; }, 1000);
if (passwordInput.value === correctPassword) {
passwordProtectionDiv.classList.add('d-none');
toolsContentDiv.classList.remove('d-none');
sessionStorage.setItem('accessGranted', 'true');
} else {
handleIncorrectPassword();
}
});
passwordInput.addEventListener('keypress', function (event) {
if (event.key === 'Enter') {
submitPasswordBtn.click();
}
});
});
```

SubPages\Vocabulary\Vocabulary.css:
```css
body {
background-color: #e9ecef;
font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}
.container {
max-width: 800px;
}
h1.text-primary {
font-weight: 700;
}
.card {
border: none;
border-radius: 0.75rem;
}
.form-control-lg {
border-radius: 0.5rem;
}
.btn-lg {
border-radius: 0.5rem;
}
#marathiOutput,
#hindiOutput,
#englishOutput {
font-size: 1.1rem;
font-weight: 500;
line-height: 1.5;
word-wrap: break-word;
overflow-wrap: break-word;
}
#marathiResultContainer,
#hindiResultContainer,
#englishResultContainer {
padding: 1rem;
border-left: 5px solid;
border-radius: 0.25rem;
color: #333;
box-shadow: 0 0.125rem 0.25rem rgba(0, 0, 0, 0.075);
min-height: 120px;
display: flex;
flex-direction: column;
}
#marathiResultContainer {
border-color: #FF6F00;
background-color: rgba(255, 111, 0, 0.08);
}
#marathiResultContainer h5 {
color: #FF6F00;
margin-bottom: 0.5rem;
}
#hindiResultContainer {
border-color: #5A2377;
background-color: rgba(90, 35, 119, 0.08);
}
#hindiResultContainer h5 {
color: #5A2377;
margin-bottom: 0.5rem;
}
#englishResultContainer {
border-color: #1565C0;
background-color: rgba(21, 101, 192, 0.08);
}
#englishResultContainer h5 {
color: #1565C0;
margin-bottom: 0.5rem;
}
#errorMessage, #loadingMessage, #noResultFound {
font-style: italic;
font-weight: 500;
text-align: center;
width: 100%;
}
#errorMessage {
color: #dc3545;
}
#loadingMessage .spinner-border {
color: #007bff !important;
}
.spinner-border {
width: 2rem;
height: 2rem;
}
#translationOutput {
padding-right: 0;
}
#csvOutputDisplay { 
font-family: 'Consolas', 'Menlo', monospace; 
font-size: 1rem;
padding: 0.75rem 1rem;
background-color: #f8f9fa; 
border: 1px solid #dee2e6; 
border-radius: 0.5rem;
white-space: nowrap; 
overflow-x: auto; 
cursor: copy; 
color: #212529;
min-height: 48px; 
display: flex; 
align-items: center; 
}
.container .card:first-of-type {
margin-bottom: 1rem !important; 
}
.card .mb-4 { 
margin-bottom: 1rem !important;
}
.card .mt-4 { 
margin-top: 1rem !important;
}
.text-center.mt-5 { 
margin-top: 2rem !important;
}
#copyFeedback {
z-index: 10; 
font-size: 0.85rem;
padding: 0.25em 0.6em;
border-radius: 0.25rem;
white-space: nowrap;
}
@media (max-width: 767.98px) {
.col-12.col-md-4 {
margin-bottom: 1rem !important;
}
#marathiOutput,
#hindiOutput,
#englishOutput {
font-size: 1.25rem;
}
}
@media (max-width: 575.98px) {
.form-label.fs-5 {
font-size: 1.1rem !important;
}
.form-control-lg {
font-size: 1rem;
padding: 0.75rem 1rem;
}
.card-title {
font-size: 1.5rem;
}
}
```

SubPages\Vocabulary\Vocabulary.html:
```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Universal Vocabulary Translator - Ganesh Chougale</title>
<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet"
integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.2/css/all.min.css"
integrity="sha512-SnH5WK+bZxgPHs44uWIX+LLJAJ9/2PkPKZ5QiAj6Ta86w+fsb2TkcmfRyVX3pBnMFcV7oQPJkl9QevSCWr3W6A=="
crossorigin="anonymous" referrerpolicy="no-referrer" />
<link rel="stylesheet" href="Vocabulary.css">
</head>
<body>
<div class="container my-3">
<div class="card p-4 shadow-sm mb-5">
<div class="mb-3">
<input type="text" class="form-control form-control-lg" id="universalInput" placeholder="Type any word to translate..." autofocus>
</div>
<div id="loadingMessage" class="text-center mt-3 d-none">
<div class="spinner-border text-primary" role="status">
<span class="visually-hidden">Loading...</span>
</div>
<p class="mt-2 text-muted">Translating...</p>
</div>
<p id="errorMessage" class="text-danger text-center mt-3 d-none"></p>
</div>
<div class="card p-4 shadow-sm">
<h3 class="card-title mb-4">Translations:</h3>
<div class="row" id="translationOutput">
<div class="col-12 col-md-4 mb-3 d-none" id="marathiResultContainer">
<h5 class="text-primary"><i class="fas fa-language me-2"></i> Marathi:</h5>
<p id="marathiOutput" class="lead ms-2"></p>
</div>
<div class="col-12 col-md-4 mb-3 d-none" id="hindiResultContainer">
<h5 class="text-success"><i class="fas fa-language me-2"></i> Hindi:</h5>
<p id="hindiOutput" class="lead ms-2"></p>
</div>
<div class="col-12 col-md-4 mb-3 d-none" id="englishResultContainer">
<h5 class="text-info"><i class="fas fa-language me-2"></i> English:</h5>
<p id="englishOutput" class="lead ms-2"></p>
</div>
<div class="col-12 d-none" id="noResultFoundContainer"> <p id="noResultFound" class="text-muted text-center mt-3 d-none">No translation found for the entered word.</p>
</div>
</div>
<div id="csvOutputContainer" class="mt-4 p-3 border rounded bg-light d-none">
<h5 class="mb-3">CSV Output</h5>
<div id="csvOutputDisplay" class="text-muted"></div>
<span id="copyFeedback" class="position-absolute translate-middle-x badge bg-success d-none" style="bottom: -15px; left: 50%;">Copied!</span>
</div>
</div>
<div class="text-center mt-5">
<a href="../Tools.html" class="btn btn-secondary btn-lg">
<i class="fas fa-arrow-left me-2"></i> Back to Tools
</a>
</div>
</div>
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"
integrity="sha384-YvpcrYf0tY3lHB60NNkmXc5s9fDVZLESaAA55NDzOxhy9GkcIdslK1eN7N6jIeHz"
crossorigin="anonymous"></script>
<script src="Vocabulary.js"></script>
</body>
</html>
```

SubPages\Vocabulary\Vocabulary.js:
```js
document.addEventListener("DOMContentLoaded", () => {
const universalInput = document.getElementById("universalInput");
const marathiResultContainer = document.getElementById(
"marathiResultContainer"
);
const hindiResultContainer = document.getElementById("hindiResultContainer");
const englishResultContainer = document.getElementById(
"englishResultContainer"
);
const marathiOutput = document.getElementById("marathiOutput");
const hindiOutput = document.getElementById("hindiOutput");
const englishOutput = document.getElementById("englishOutput");
const loadingMessage = document.getElementById("loadingMessage");
const errorMessage = document.getElementById("errorMessage");
const noResultFound = document.getElementById("noResultFound");
const noResultFoundContainer = document.getElementById(
"noResultFoundContainer"
);
const csvOutputContainer = document.getElementById("csvOutputContainer"); 
const csvOutputDisplay = document.getElementById("csvOutputDisplay"); 
const copyFeedback = document.getElementById("copyFeedback");
function toCapitalCase(str) {
return str.charAt(0).toUpperCase() + str.slice(1).toLowerCase();
}
let debounceTimer;
const debounce = (func, delay) => {
clearTimeout(debounceTimer);
debounceTimer = setTimeout(func, delay);
};
async function fetchTranslation(text, targetLang) {
if (!text || text.trim() === "") {
return "";
}
const url = `https:
text
)}`;
try {
const response = await fetch(url);
if (!response.ok) {
throw new Error(`HTTP error! Status: ${response.status}`);
}
const data = await response.json();
if (data && data[0] && Array.isArray(data[0][0]) && data[0][0][0]) {
return data[0][0][0]; 
} else if (data && data[0] && typeof data[0][0] === "string") {
return data[0][0]; 
} else {
console.warn("Unexpected API response structure:", data);
return ""; 
}
} catch (error) {
console.error(`Error translating to ${targetLang}:`, error);
return ""; 
}
}
function displayResults(translations, originalWord) {
marathiResultContainer.classList.add("d-none");
hindiResultContainer.classList.add("d-none");
englishResultContainer.classList.add("d-none");
noResultFound.classList.add("d-none");
if (noResultFoundContainer) {
noResultFoundContainer.classList.add("d-none");
}
errorMessage.classList.add("d-none");
csvOutputContainer.classList.add("d-none"); 
let hasTranslation = false;
let marathiTrans = "";
let hindiTrans = "";
let englishTrans = "";
if (translations.marathi && translations.marathi !== "") {
marathiOutput.textContent = translations.marathi;
marathiResultContainer.classList.remove("d-none");
marathiTrans = translations.marathi;
hasTranslation = true;
}
if (translations.hindi && translations.hindi !== "") {
hindiOutput.textContent = translations.hindi;
hindiResultContainer.classList.remove("d-none");
hindiTrans = translations.hindi;
hasTranslation = true;
}
if (translations.english && translations.english !== "") {
englishOutput.textContent = translations.english;
englishResultContainer.classList.remove("d-none");
englishTrans = translations.english;
hasTranslation = true;
}
if (hasTranslation) {
csvOutputDisplay.textContent = `${toCapitalCase(
translations.english
)}, ${marathiTrans}, ${hindiTrans}`;
csvOutputContainer.classList.remove("d-none"); 
} else if (originalWord.trim() !== "") {
noResultFound.classList.remove("d-none");
if (noResultFoundContainer) {
noResultFoundContainer.classList.remove("d-none");
}
csvOutputContainer.classList.add("d-none"); 
}
if (!hasTranslation && originalWord.trim() === "") {
csvOutputDisplay.textContent = "";
}
}
async function handleTranslation() {
const text = universalInput.value.trim();
if (text === "") {
displayResults({}); 
noResultFound.classList.add("d-none");
if (noResultFoundContainer) {
noResultFoundContainer.classList.add("d-none");
}
errorMessage.classList.add("d-none");
loadingMessage.classList.add("d-none");
csvOutputContainer.classList.add("d-none"); 
csvOutputDisplay.textContent = ""; 
return;
}
loadingMessage.classList.remove("d-none");
errorMessage.classList.add("d-none");
noResultFound.classList.add("d-none");
if (noResultFoundContainer) {
noResultFoundContainer.classList.add("d-none");
}
csvOutputContainer.classList.add("d-none"); 
csvOutputDisplay.textContent = ""; 
try {
const translations = {};
const targetLanguages = ["en", "mr", "hi"];
const promises = targetLanguages.map((target) =>
fetchTranslation(text, target).then((result) => ({ target, result }))
);
const results = await Promise.all(promises);
results.forEach(({ target, result }) => {
if (target === "mr") translations.marathi = result;
if (target === "hi") translations.hindi = result;
if (target === "en") translations.english = result;
});
displayResults(translations, text);
} catch (error) {
console.error("Overall translation error:", error);
errorMessage.textContent =
"An error occurred during translation. Please try again.";
errorMessage.classList.remove("d-none");
displayResults({}); 
csvOutputContainer.classList.add("d-none"); 
csvOutputDisplay.textContent = ""; 
} finally {
loadingMessage.classList.add("d-none");
}
}
csvOutputContainer.addEventListener("click", async () => {
const textToCopy = csvOutputDisplay.textContent;
if (textToCopy) {
try {
await navigator.clipboard.writeText(textToCopy);
copyFeedback.classList.remove("d-none");
setTimeout(() => {
copyFeedback.classList.add("d-none");
}, 1500); 
} catch (err) {
console.error("Failed to copy text: ", err);
}
}
});
universalInput.addEventListener("input", () => {
debounce(handleTranslation, 500);
});
});
```

