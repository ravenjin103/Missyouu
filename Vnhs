<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VICTORIAS NATIONAL HIGH SCHOOL</title>
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap" rel="stylesheet">
<style>
    * {margin:0; padding:0; box-sizing:border-box; font-family:'Poppins', sans-serif;}
    body {
        background: url('https://i.imgur.com/3e7b7UK.jpg') no-repeat center center fixed;
        background-size: cover;
        color: #fff;
    }
    .overlay { background: rgba(0,0,0,0.6); min-height:100vh; padding:20px; }
    header { text-align:center; padding:50px 20px; }
    header h1 { font-size:3rem; color:#00ffcc; } /* no glow */
    header img {
        width:200px;
        height:200px;
        object-fit:cover;
        border-radius:50%; /* circle image */
        margin-top:20px;
        border:4px solid #FFD700;
    }
    .btn {
        display:inline-block;
        padding:12px 25px;
        margin:10px;
        border:none;
        border-radius:8px;
        background: linear-gradient(45deg,#ff4d4d,#00ff7f,#1e90ff);
        color:#fff;
        font-weight:bold;
        cursor:pointer;
        transition: all 0.3s ease;
        box-shadow:0 0 10px rgba(255,255,255,0.3);
    }
    .btn:hover { transform:scale(1.1); }
    section { padding:50px 20px; text-align:center; display:none; transition: 0.5s; }
    section.active { display:block; animation: glowAnim 0.8s ease; }
    section h2 { font-size:2.5rem; margin-bottom:20px; color:#00ffff; }
    section p { max-width:800px; margin:auto; font-size:1.1rem; line-height:1.6; }
    .cards { display:grid; grid-template-columns:repeat(auto-fit,minmax(250px,1fr)); gap:20px; margin-top:30px; }
    .card { background: rgba(255,255,255,0.1); padding:20px; border-radius:15px; transition: transform 0.3s; cursor:pointer; }
    .card:hover { transform:translateY(-10px); }
    .gallery { display:grid; grid-template-columns:repeat(auto-fit,minmax(200px,1fr)); gap:15px; margin-top:30px; }
    .gallery img { width:100%; border-radius:15px; transition: transform 0.3s; }
    .gallery img:hover { transform:scale(1.05); }
    .contact-info, .login-form { max-width:600px; margin:auto; text-align:left; background: rgba(255,255,255,0.1); padding:20px; border-radius:15px; margin-top:20px; }
    .contact-info p, .login-form p { margin:10px 0; }
    input[type=text], input[type=password], input[type=email] { width:100%; padding:10px; margin:5px 0 15px 0; border-radius:5px; border:none; }
    input[type=submit] { background: linear-gradient(45deg,#ff4d4d,#00ff7f,#1e90ff); color:#fff; padding:12px 20px; border:none; border-radius:8px; cursor:pointer; font-weight:bold; transition:0.3s; }
    input[type=submit]:hover { transform:scale(1.05); }
    #map { width:100%; height:400px; border-radius:15px; margin-top:20px; }

    @keyframes glowAnim {
        0% { box-shadow:0 0 0px #fff; }
        50% { box-shadow:0 0 20px #00ffff, 0 0 40px #ff00ff; }
        100% { box-shadow:0 0 0px #fff; }
    }
</style>
</head>
<body>
<div class="overlay">
    <header>
        <h1>VICTORIAS NATIONAL HIGH SCHOOL</h1>
        <p>Negros Occidental, Philippines</p>
        <img src="/storage/emulated/0/DCIM/Facebook/FB_IMG_1771162537799_3.jpg" alt="vnhs-logo">
    </header>

    <!-- Buttons -->
    <div style="text-align:center;">
        <button class="btn" onclick="showSection('about')">What is VNHS?</button>
        <button class="btn" onclick="showSection('facilities')">Facilities</button>
        <button class="btn" onclick="showSection('achievements')">Achievements</button>
        <button class="btn" onclick="showSection('photos')">Photos</button>
        <button class="btn" onclick="showSection('hymn')">School Hymn</button>
        <button class="btn" onclick="showSection('map')">Location Map</button>
        <button class="btn" onclick="showSection('login')">Login</button>
    </div>

    <!-- Sections -->
    <section id="about">
        <h2>What is VNHS?</h2>
        <p>Victoria National High School (VNHS) is a premier educational institution in Negros Occidental, Philippines, committed to providing quality education, fostering excellence, and developing well-rounded students who are ready to face global challenges.</p>
    </section>

    <section id="facilities">
        <h2>Our Facilities</h2>
        <div class="cards">
            <div class="card"><b>ICT Computer Rooms</b><br>State-of-the-art technology labs for digital learning.</div>
            <div class="card"><b>Science Laboratories</b><br>Fully equipped for practical science experiments.</div>
            <div class="card"><b>Library</b><br>A vast collection of books and study resources.</div>
            <div class="card"><b>Sports Facilities</b><br>Football pitch, basketball courts, and more.</div>
            <div class="card"><b>Auditorium</b><br>For school programs, events, and performances.</div>
            <div class="card"><b>Canteen</b><br>Comfortable place for students to eat and socialize.</div>
        </div>
    </section>

    <section id="achievements">
        <h2>Achievements</h2>
        <div class="cards">
            <div class="card"><b>Academic Excellence Awards</b><br>Top-performing students in regional and national competitions.</div>
            <div class="card"><b>Sports Championships</b><br>Outstanding achievements in football, basketball, and athletics.</div>
            <div class="card"><b>Science & Tech Innovations</b><br>Award-winning projects in science fairs and tech contests.</div>
        </div>
    </section>

    <section id="photos">
        <h2>Photos</h2>
        <div class="gallery">
            <img src="https://i.imgur.com/1.jpg" alt="VNHS Photo 1">
            <img src="https://i.imgur.com/2.jpg" alt="VNHS Photo 2">
            <img src="https://i.imgur.com/3.jpg" alt="VNHS Photo 3">
            <img src="https://i.imgur.com/4.jpg" alt="VNHS Photo 4">
            <img src="https://i.imgur.com/5.jpg" alt="VNHS Photo 5">
            <img src="https://i.imgur.com/6.jpg" alt="VNHS Photo 6">
        </div>
    </section>

    <section id="hymn">
        <h2>School Hymn</h2>
        <video width="80%" controls autoplay loop muted style="border-radius:15px;">
            <source src="https://www.example.com/vnhs-hymn.mp4" type="video/mp4">
            Your browser does not support the video tag.
        </video>
    </section>

    <section id="map">
        <h2>Our Location</h2>
        <iframe id="map" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3875.998584239784!2d122.875598215147!3d10.7903011923026!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x33aa6b7c2b0b4c27%3A0x123456789abcdef!2sVictorias%20National%20High%20School!5e0!3m2!1sen!2sph!4v1687412345678!5m2!1sen!2sph" style="border:0;" allowfullscreen="" loading="lazy"></iframe>
    </section>

    <section id="login">
        <h2>Login</h2>
        <div class="login-form">
            <form>
                <p><b>Username:</b></p>
                <input type="text" placeholder="Enter your username" required>
                <p><b>Password:</b></p>
                <input type="password" placeholder="Enter your password" required>
                <p><b>Email:</b></p>
                <input type="email" placeholder="Enter your email" required>
                <input type="submit" value="Login">
            </form>
        </div>
    </section>

</div>

<script>
function showSection(id){
    document.querySelectorAll('section').forEach(sec=>sec.classList.remove('active'));
    let section = document.getElementById(id);
    section.classList.add('active');
}
</script>
</body>
</html>
