<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Albert N Njagi | Professional Portfolio</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <header>
    <img src="albert.jpg" alt="Albert N Njagi" class="profile-img">
    <h1>Albert N Njagi</h1>
    <p>Educator | Researcher | Innovator</p>
    <nav>
      <ul>
        <li><a href="#about">About</a></li>
        <li><a href="#portfolio">Portfolio</a></li>
        <li><a href="#skills">Skills</a></li>
        <li><a href="#experience">Experience</a></li>
        <li><a href="#education">Education</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <section id="about">
    <h2>About Me</h2>
    <p>Albert Njagi is an experienced educator and researcher specializing in Mechanical and Automotive Technology. Currently serving as a Vocational College Lecturer at Mukiria Technical Training Institute, he teaches Mathematics, Engineering Drawing and Designs, Welding and Fabrications, and Mechanical Production. He has also held various leadership roles, including Head of Mechanical and Automotive Engineering Department, Applied Research Lead, and Research Coordinator.</p>
  </section>

  <section id="portfolio">
    <h2>Portfolio</h2>
    <div class="project">
      <h3>Young Africa Works - Kenya Applied Research</h3>
      <p>A CICan and MasterCard Foundation funded project focusing on sustainable innovations and technical skills enhancement.</p>
    </div>
    <div class="project">
      <h3>Recognition of Prior Learning (RPL) Initiatives</h3>
      <p>Advancing the recognition and certification of informal and non-formal learning in TVET.</p>
    </div>
  </section>

  <section id="skills">
    <h2>Skills</h2>
    <ul>
      <li>Curriculum Development</li>
      <li>Applied Research</li>
      <li>Technical Training</li>
      <li>Leadership in TVET Education</li>
      <li>Innovation and Research Coordination</li>
    </ul>
  </section>

  <section id="experience">
    <h2>Experience</h2>
    <h3>Mukiria Technical Training Institute</h3>
    <p><strong>Vocational College Lecturer & Research Coordinator</strong> (Current)</p>
    <ul>
      <li>Teaching Mathematics, Engineering Drawing, Welding, and Mechanical Production.</li>
      <li>Head of Mechanical and Automotive Engineering Department.</li>
      <li>Leading applied research initiatives and curriculum development.</li>
    </ul>
  </section>

  <section id="education">
    <h2>Education</h2>
    <ul>
      <li>Master's Degree in Education (Technology Education - Mechanical and Automotive Technology), University of Eldoret (Ongoing)</li>
      <li>Bachelor's Degree in Technology Education (Mechanical Technology), University of Eldoret, Second Class Honors (Upper Division)</li>
    </ul>
  </section>

  <section id="contact">
    <h2>Contact Me</h2>
    <form id="contactForm">
      <input type="text" id="name" placeholder="Your Name" required />
      <input type="email" id="email" placeholder="Your Email" required />
      <textarea id="message" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
    <p>
      <strong>Social Media:</strong>
      <a href="https://github.com/albertdoublen">GitHub</a>
    </p>
  </section>

  <footer>
    <p>&copy; 2025 Albert N Njagi. All rights reserved.</p>
  </footer>

  <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
  <script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-database.js"></script>
  <script>
    const firebaseConfig = {
      apiKey: "YOUR_FIREBASE_API_KEY",
      authDomain: "YOUR_FIREBASE_AUTH_DOMAIN",
      databaseURL: "YOUR_FIREBASE_DATABASE_URL",
      projectId: "YOUR_FIREBASE_PROJECT_ID",
      storageBucket: "YOUR_FIREBASE_STORAGE_BUCKET",
      messagingSenderId: "YOUR_FIREBASE_MESSAGING_SENDER_ID",
      appId: "YOUR_FIREBASE_APP_ID"
    };

    firebase.initializeApp(firebaseConfig);

    document.getElementById("contactForm").addEventListener("submit", function(e) {
      e.preventDefault();

      const name = document.getElementById("name").value;
      const email = document.getElementById("email").value;
      const message = document.getElementById("message").value;

      firebase.database().ref("messages").push({
        name,
        email,
        message,
        timestamp: new Date().toISOString()
      }).then(() => {
        alert("Message sent successfully!");
        document.getElementById("contactForm").reset();
      }).catch((error) => {
        alert("Error: " + error.message);
      });
    });
  </script>
</body>
</html>
