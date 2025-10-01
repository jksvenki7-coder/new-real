# new-real<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>Real Estate & Construction - Complete</title>
<style>
  body {
    font-family: Arial, sans-serif;
    margin: 0;
    background-color: #f0f8ff;
    color: #205081;
  }
  header, footer {
    background-color: white;
    text-align: center;
    padding: 15px 0;
    border-bottom: 2px solid #87ceeb;
  }
  h1 {
    color: #1e90ff;
    margin: 0;
  }
  .container {
    margin: 20px auto;
    max-width: 1100px;
    background-color: white;
    box-shadow: 0 0 10px rgba(135, 206, 235, 0.3);
    padding: 20px;
    border-radius: 8px;
  }
  #dashboard {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    gap: 16px;
  }
  .folder-card {
    background-color: #e6f2ff;
    border: 1px solid #87ceeb;
    border-radius: 8px;
    width: 220px;
    padding: 22px;
    box-sizing: border-box;
    font-weight: 600;
    color: #2a4c8d;
    text-align: center;
    cursor: pointer;
    user-select: none;
    transition: background-color 0.3s ease, color 0.3s ease;
  }
  .folder-card:hover {
    background-color: #87ceeb;
    color: white;
  }
  h2.section-title {
    border-bottom: 2px solid #87ceeb;
    color: #4682b4;
    padding-bottom: 7px;
    margin-bottom: 18px;
    font-size: 1.3em;
  }
  ul {
    margin-top: 10px;
    padding-left: 20px;
    text-align: left;
    color: #273965;
    font-size: 1.1em;
  }
  .folder-section {
    display: none;
  }
  .back-btn {
    background-color: white;
    color: #0288d1;
    border: 3px solid #03a9f4;
    cursor: pointer;
    font-size: 18px;
    border-radius: 12px;
    font-weight: bold;
    padding: 12px 50px;
    box-shadow: 2px 2px 8px rgba(3,169,244,0.3);
    text-align: center;
    margin: 20px auto;
    width: 220px;
    display: block;
    transition: background-color 0.3s ease, color 0.3s ease;
  }
  .back-btn:hover {
    background-color: #03a9f4;
    color: white;
    box-shadow: 2px 2px 12px rgba(3,169,244,0.7);
  }
  form.contact-form {
    max-width: 450px;
    margin: 30px auto 0;
    padding: 20px;
    background-color: #eef7ff;
    border-radius: 10px;
    border: 1px solid #85bbeb;
    font-size: 1.1em;
    text-align: left;
  }
  form.contact-form label {
    font-weight: 600;
    color: #205081;
    display: block;
    margin-bottom: 8px;
  }
  form.contact-form input, form.contact-form textarea {
    width: 100%;
    padding: 10px;
    margin-bottom: 15px;
    border: 2px solid #85bbeb;
    border-radius: 6px;
    box-sizing: border-box;
    resize: vertical;
    font-size: 1em;
  }
  form.contact-form input:focus, form.contact-form textarea:focus {
    border-color: #3a8ddb;
    outline: none;
  }
  button.submit-btn {
    width: 100%;
    background-color: #275db2;
    color: white;
    border: none;
    padding: 14px;
    font-weight: 700;
    font-size: 1.15em;
    border-radius: 8px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }
  button.submit-btn:hover {
    background-color: #1b3f72;
  }
</style>
<script>
  let currentFolder = '';

  function showDashboard() {
    document.getElementById('dashboard').style.display = 'flex';
    let folderSections = document.querySelectorAll('.folder-section');
    folderSections.forEach(s => s.style.display = 'none');
    currentFolder = '';
    window.scrollTo(0,0);
  }

  function openFolder(sectionId) {
    document.getElementById('dashboard').style.display = 'none';
    let folderSections = document.querySelectorAll('.folder-section');
    folderSections.forEach(s => s.style.display = 'none');
    document.getElementById(sectionId).style.display = 'block';
    currentFolder = sectionId;
    window.scrollTo(0,0);
  }

  function handleSubmit(event) {
    event.preventDefault();
    const form = event.target;
    const name = form.name.value.trim();
    const email = form.email.value.trim();
    const phone = form.phone.value.trim();
    const message = form.message.value.trim();

    if(!name || !email || !phone || !message) {
      alert('Please fill all fields.');
      return;
    }

    const phoneNumber = '8977143043';
    const messageText = `Name: ${encodeURIComponent(name)}%0AEmail: ${encodeURIComponent(email)}%0APhone: ${encodeURIComponent(phone)}%0AService: ${encodeURIComponent(currentFolder)}%0AMessage: ${encodeURIComponent(message)}`;
    const waUrl = `https://wa.me/${phoneNumber}?text=${messageText}`;
    window.open(waUrl, '_blank');

    form.reset();
    showDashboard();
  }
</script>
</head>
<body>
<header>
  <h1>Real Estate & Construction</h1>
</header>

<div class="container">
  <div id="dashboard">
    <div class="folder-card" onclick="openFolder('buySection')">Buy</div>
    <div class="folder-card" onclick="openFolder('sellSection')">Sell</div>
    <div class="folder-card" onclick="openFolder('toletSection')">Tolet</div>
    <div class="folder-card" onclick="openFolder('keySection')">Key</div>
    <div class="folder-card" onclick="openFolder('constructionSection')">Construction</div>
    <div class="folder-card" onclick="openFolder('industrySection')">Industry</div>
  </div>

  <div id="buySection" class="folder-section">
    <h2 class="section-title">Buy Services</h2>
    <ul>
      <li>Location</li>
      <li>Apartment</li>
      <li>Land</li>
      <li>Venture</li>
      <li>Others</li>
    </ul>
    <form class="contact-form" onsubmit="handleSubmit(event)">
      <h3>Contact Details</h3>
      <label>Name:</label><input type="text" name="name" required />
      <label>Email:</label><input type="email" name="email" required />
      <label>Phone:</label><input type="tel" name="phone" required />
      <label>Message:</label><textarea name="message" rows="4" required></textarea>
      <button type="submit" class="submit-btn">Send via WhatsApp</button>
    </form>
    <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>
  </div>

  <div id="sellSection" class="folder-section">
    <h2 class="section-title">Sell Services</h2>
    <ul>
      <li>Location</li>
      <li>Apartment</li>
      <li>House</li>
      <li>Others</li>
    </ul>
    <form class="contact-form" onsubmit="handleSubmit(event)">
      <h3>Contact Details</h3>
      <label>Name:</label><input type="text" name="name" required />
      <label>Email:</label><input type="email" name="email" required />
      <label>Phone:</label><input type="tel" name="phone" required />
      <label>Message:</label><textarea name="message" rows="4" required></textarea>
      <button type="submit" class="submit-btn">Send via WhatsApp</button>
    </form>
    <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>
  </div>

  <div id="toletSection" class="folder-section">
    <h2 class="section-title">Tolet Services</h2>
    <ul>
      <li>Office</li>
      <li>Hotel</li>
      <li>Apartment</li>
      <li>House</li>
      <li>Others</li>
    </ul>
    <form class="contact-form" onsubmit="handleSubmit(event)">
      <h3>Contact Details</h3>
      <label>Name:</label><input type="text" name="name" required />
      <label>Email:</label><input type="email" name="email" required />
      <label>Phone:</label><input type="tel" name="phone" required />
      <label>Message:</label><textarea name="message" rows="4" required></textarea>
      <button type="submit" class="submit-btn">Send via WhatsApp</button>
    </form>
    <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>
  </div>

  <div id="keySection" class="folder-section">
    <h2 class="section-title">Key Services</h2>
    <ul>
      <li>Land</li>
      <li>Hotel</li>
      <li>Apartment</li>
      <li>Others</li>
    </ul>
    <form class="contact-form" onsubmit="handleSubmit(event)">
      <h3>Contact Details</h3>
      <label>Name:</label><input type="text" name="name" required />
      <label>Email:</label><input type="email" name="email" required />
      <label>Phone:</label><input type="tel" name="phone" required />
      <label>Message:</label><textarea name="message" rows="4" required></textarea>
      <button type="submit" class="submit-btn">Send via WhatsApp</button>
    </form>
    <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>
  </div>

  <div id="constructionSection" class="folder-section">
    <h2 class="section-title">Construction Services</h2>
    <ul>
      <li>Location</li>
      <li>House</li>
      <li>Shop</li>
      <li>Mall</li>
      <li>Park</li>
      <li>Hotel</li>
    </ul>
    <form class="contact-form" onsubmit="handleSubmit(event)">
      <h3>Contact Details</h3>
      <label>Name:</label><input type="text" name="name" required />
      <label>Email:</label><input type="email" name="email" required />
      <label>Phone:</label><input type="tel" name="phone" required />
      <label>Message:</label><textarea name="message" rows="4" required></textarea>
      <button type="submit" class="submit-btn">Send via WhatsApp</button>
    </form>
    <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>
  </div>

  <div id="industrySection" class="folder-section">
    <h2 class="section-title">Industry Services</h2>
    <ul>
      <li>Location</li>
      <li>Sample Display</li>
    </ul>
    <form class="contact-form" onsubmit="handleSubmit(event)">
      <h3>Contact Details</h3>
      <label>Name:</label><input type="text" name="name" required />
      <label>Email:</label><input type="email" name="email" required />
      <label>Phone:</label><input type="tel" name="phone" required />
      <label>Message:</label><textarea name="message" rows="4" required></textarea>
      <button type="submit" class="submit-btn">Send via WhatsApp</button>
    </form>
    <button class="back-btn" onclick="showDashboard()">Back to Dashboard</button>
  </div>

</div>
<footer>
  <p style="text-align:center; padding: 12px;">Services & Support</p>
</footer>
</body>
</html>
