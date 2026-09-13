<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Laykari Echoverse Studio Communication</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    scroll-behavior:smooth;
}

body{
    font-family:Arial,Helvetica,sans-serif;
    background:#08080d;
    color:#fff;
    line-height:1.6;
}

:root{
    --primary:#a855f7;
    --secondary:#ec4899;
    --dark:#08080d;
    --card:#12121a;
}

nav{
    position:fixed;
    top:0;
    left:0;
    width:100%;
    z-index:1000;
    padding:16px 7%;
    display:flex;
    justify-content:space-between;
    align-items:center;
    background:rgba(8,8,13,.85);
    backdrop-filter:blur(15px);
    border-bottom:1px solid rgba(255,255,255,.08);
}

.logo{
    font-size:20px;
    font-weight:800;
    color:#fff;
}

.logo span{
    color:var(--primary);
}

nav ul{
    list-style:none;
    display:flex;
    gap:25px;
}

nav a{
    color:#ddd;
    text-decoration:none;
    font-size:14px;
    transition:.3s;
}

nav a:hover{
    color:#c084fc;
}

.menu{
    display:none;
    font-size:27px;
    cursor:pointer;
}

.hero{
    min-height:100vh;
    display:flex;
    align-items:center;
    justify-content:center;
    text-align:center;
    padding:120px 7% 70px;
    background:
      radial-gradient(circle at 20% 20%,rgba(168,85,247,.25),transparent 30%),
      radial-gradient(circle at 80% 70%,rgba(236,72,153,.20),transparent 30%),
      #08080d;
}

.hero-content{
    max-width:900px;
}

.badge{
    display:inline-block;
    padding:7px 16px;
    border:1px solid rgba(192,132,252,.4);
    border-radius:30px;
    color:#d8b4fe;
    margin-bottom:20px;
    font-size:13px;
}

.hero h1{
    font-size:clamp(42px,7vw,82px);
    line-height:1.05;
    margin-bottom:20px;
}

.gradient{
    background:linear-gradient(90deg,#c084fc,#f472b6);
    -webkit-background-clip:text;
    color:transparent;
}

.hero p{
    color:#aaa;
    max-width:650px;
    margin:auto;
    font-size:17px;
}

.buttons{
    margin-top:32px;
    display:flex;
    justify-content:center;
    gap:15px;
    flex-wrap:wrap;
}

.btn{
    padding:13px 24px;
    border-radius:30px;
    text-decoration:none;
    font-weight:bold;
    display:inline-block;
    transition:.3s;
}

.btn-primary{
    background:linear-gradient(90deg,#9333ea,#db2777);
    color:#fff;
}

.btn-secondary{
    border:1px solid #555;
    color:#fff;
}

.btn:hover{
    transform:translateY(-3px);
}

section{
    padding:90px 7%;
}

.section-title{
    text-align:center;
    margin-bottom:50px;
}

.section-title h2{
    font-size:38px;
    margin-bottom:10px;
}

.section-title p{
    color:#999;
}

.cards{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:22px;
}

.card{
    background:linear-gradient(145deg,#15151e,#0e0e14);
    border:1px solid rgba(255,255,255,.08);
    padding:30px;
    border-radius:20px;
    transition:.3s;
}

.card:hover{
    transform:translateY(-8px);
    border-color:#9333ea;
}

.icon{
    font-size:38px;
    margin-bottom:15px;
}

.card h3{
    margin-bottom:10px;
}

.card p{
    color:#999;
}

.about{
    display:grid;
    grid-template-columns:1fr 1fr;
    gap:50px;
    align-items:center;
}

.about-box{
    background:linear-gradient(145deg,#17131e,#0d0d13);
    border-radius:25px;
    padding:45px;
    border:1px solid rgba(255,255,255,.08);
}

.about-box h2{
    font-size:40px;
    margin-bottom:20px;
}

.about-box p{
    color:#aaa;
}

.features{
    margin-top:25px;
}

.features div{
    margin:12px 0;
    color:#ddd;
}

.player{
    max-width:700px;
    margin:auto;
    padding:30px;
    background:#111119;
    border-radius:22px;
    border:1px solid rgba(255,255,255,.08);
}

.player h3{
    margin-bottom:15px;
}

audio{
    width:100%;
}

.pricing{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:22px;
}

.price-card{
    background:#111119;
    border:1px solid rgba(255,255,255,.08);
    padding:35px;
    border-radius:22px;
    text-align:center;
}

.price-card.featured{
    border:1px solid #a855f7;
    transform:scale(1.03);
}

.price{
    font-size:35px;
    font-weight:bold;
    margin:20px 0;
}

.price-card ul{
    list-style:none;
    color:#aaa;
    margin-bottom:25px;
}

.price-card li{
    margin:8px 0;
}

.gallery{
    display:grid;
    grid-template-columns:repeat(3,1fr);
    gap:18px;
}

.gallery div{
    height:220px;
    border-radius:18px;
    display:flex;
    align-items:center;
    justify-content:center;
    background:
      linear-gradient(135deg,rgba(168,85,247,.35),rgba(236,72,153,.15)),
      #15151d;
    border:1px solid rgba(255,255,255,.08);
    font-size:45px;
}

form{
    max-width:700px;
    margin:auto;
    background:#111119;
    padding:35px;
    border-radius:22px;
    border:1px solid rgba(255,255,255,.08);
}

input,textarea,select{
    width:100%;
    padding:14px;
    margin-bottom:15px;
    border-radius:10px;
    border:1px solid #333;
    background:#08080d;
    color:#fff;
    outline:none;
}

textarea{
    min-height:130px;
    resize:vertical;
}

form button{
    border:0;
    cursor:pointer;
    width:100%;
}

.contact{
    text-align:center;
}

.contact-info{
    margin-top:25px;
    color:#aaa;
}

footer{
    padding:35px 7%;
    text-align:center;
    border-top:1px solid rgba(255,255,255,.08);
    color:#777;
}

.socials{
    margin:20px 0;
}

.socials a{
    color:#ddd;
    text-decoration:none;
    margin:0 8px;
}

@media(max-width:800px){

    nav ul{
        display:none;
        position:absolute;
        top:70px;
        left:0;
        width:100%;
        background:#0b0b10;
        flex-direction:column;
        text-align:center;
        padding:25px;
    }

    nav ul.active{
        display:flex;
    }

    .menu{
        display:block;
    }

    .cards,
    .pricing,
    .gallery,
    .about{
        grid-template-columns:1fr;
    }

    .price-card.featured{
        transform:none;
    }

    section{
        padding:70px 5%;
    }

    .hero h1{
        font-size:45px;
    }
}
</style>
</head>

<body>

<nav>
    <div class="logo">
        Laykari <span>Echoverse</span>
    </div>

    <div class="menu" onclick="toggleMenu()">☰</div>

    <ul id="navLinks">
        <li><a href="#home">Home</a></li>
        <li><a href="#about">Studio</a></li>
        <li><a href="#services">Services</a></li>
        <li><a href="#music">Music</a></li>
        <li><a href="#pricing">Pricing</a></li>
        <li><a href="#booking">Booking</a></li>
        <li><a href="#contact">Contact</a></li>
    </ul>
</nav>


<!-- HOME -->
<section class="hero" id="home">
    <div class="hero-content">

        <div class="badge">
            🎙️ Professional Music Production Studio
        </div>

        <h1>
            Laykari <span class="gradient">Echoverse</span><br>
            Studio Communication
        </h1>

        <p>
            Record. Create. Mix. Master.  
            Turn your musical ideas into professional-quality sound.
        </p>

        <div class="buttons">
            <a href="#booking" class="btn btn-primary">
                🎤 Book a Session
            </a>

            <a href="#music" class="btn btn-secondary">
                ▶ Listen to Music
            </a>
        </div>

    </div>
</section>


<!-- ABOUT -->
<section id="about">

    <div class="about">

        <div class="about-box">
            <h2>
                Your Sound.<br>
                <span class="gradient">Your Identity.</span>
            </h2>

            <p>
                Welcome to Laykari Echoverse Studio Communication,
                a creative space for singers, musicians, rappers,
                creators and artists.
            </p>

            <div class="features">
                <div>🎙️ Professional Recording</div>
                <div>🎚️ Mixing & Mastering</div>
                <div>🎹 Music Production</div>
                <div>🎧 Creative Audio Production</div>
            </div>
        </div>

        <div class="about-box">
            <h2>Why Choose Us?</h2>

            <p>
                We focus on clean sound, creative production and
                a comfortable recording experience for every artist.
            </p>

            <div class="features">
                <div>✓ High-quality recording setup</div>
                <div>✓ Experienced production workflow</div>
                <div>✓ Modern music production</div>
                <div>✓ Artist-focused environment</div>
            </div>
        </div>

    </div>

</section>


<!-- SERVICES -->
<section id="services">

    <div class="section-title">
        <h2>Our <span class="gradient">Services</span></h2>
        <p>Everything you need to create your next track.</p>
    </div>

    <div class="cards">

        <div class="card">
            <div class="icon">🎙️</div>
            <h3>Vocal Recording</h3>
            <p>
                Professional vocal recording for songs,
                covers, rap, podcasts and creative projects.
            </p>
        </div>

        <div class="card">
            <div class="icon">🎚️</div>
            <h3>Mixing & Mastering</h3>
            <p>
                Balanced, polished and release-ready sound
                for your music.
            </p>
        </div>

        <div class="card">
            <div class="icon">🎹</div>
            <h3>Music Production</h3>
            <p>
                Build your song from an idea into a complete
                musical production.
            </p>
        </div>

        <div class="card">
            <div class="icon">🎧</div>
            <h3>Audio Editing</h3>
            <p>
                Clean editing, vocal processing and creative
                audio work.
            </p>
        </div>

        <div class="card">
            <div class="icon">🎤</div>
            <h3>Artist Sessions</h3>
            <p>
                Comfortable sessions designed around your
                creative workflow.
            </p>
        </div>

        <div class="card">
            <div class="icon">🎼</div>
            <h3>Song Creation</h3>
            <p>
                Develop melodies, arrangements and complete
                song concepts.
            </p>
        </div>

    </div>
</section>


<!-- MUSIC -->
<section id="music">

    <div class="section-title">
        <h2>Featured <span class="gradient">Music</span></h2>
        <p>Listen to your studio tracks directly from the website.</p>
    </div>

    <div class="player">

        <h3>🎵 Studio Demo Track</h3>

        <!-- Put your music file in the same folder and name it music.mp3 -->
        <audio controls>
            <source src="music.mp3" type="audio/mpeg">
            Your browser does not support the audio player.
        </audio>

        <p style="margin-top:15px;color:#777;">
            Replace "music.mp3" with your own song file.
        </p>

    </div>

</section>


<!-- PRICING -->
<section id="pricing">

    <div class="section-title">
        <h2>Studio <span class="gradient">Packages</span></h2>
        <p>Example packages — edit prices according to your studio.</p>
    </div>

    <div class="pricing">

        <div class="price-card">
            <h3>Basic</h3>

            <div class="price">₹499</div>

            <ul>
                <li>🎙️ Recording Session</li>
                <li>⏱️ 1 Hour</li>
                <li>🎧 Basic Editing</li>
            </ul>

            <a href="#booking" class="btn btn-secondary">
                Book Now
            </a>
        </div>


        <div class="price-card featured">

            <h3>Artist</h3>

            <div class="price">₹999</div>

            <ul>
                <li>🎙️ Recording</li>
                <li>⏱️ 2 Hours</li>
                <li>🎚️ Mixing</li>
                <li>🎧 Basic Mastering</li>
            </ul>

            <a href="#booking" class="btn btn-primary">
                Book Now
            </a>

        </div>


        <div class="price-card">

            <h3>Pro</h3>

            <div class="price">₹1999</div>

            <ul>
                <li>🎙️ Recording</li>
                <li>🎹 Production</li>
                <li>🎚️ Mixing</li>
                <li>💿 Mastering</li>
            </ul>

            <a href="#booking" class="btn btn-secondary">
                Book Now
            </a>

        </div>

    </div>
</section>


<!-- GALLERY -->
<section>

    <div class="section-title">
        <h2>Studio <span class="gradient">Gallery</span></h2>
        <p>Add your real studio photographs here.</p>
    </div>

    <div class="gallery">

        <div>🎙️</div>
        <div>🎧</div>
        <div>🎹</div>
        <div>🎚️</div>
        <div>🎤</div>
        <div>🎼</div>

    </div>

</section>


<!-- BOOKING -->
<section id="booking">

    <div class="section-title">
        <h2>Book a <span class="gradient">Session</span></h2>
        <p>Fill the form and send your booking request.</p>
    </div>

    <form onsubmit="sendBooking(event)">

        <input
            type="text"
            id="name"
            placeholder="Your Name"
            required
        >

        <input
            type="tel"
            id="phone"
            placeholder="Phone Number"
            required
        >

        <select id="service" required>
            <option value="">Select Service</option>
            <option>Vocal Recording</option>
            <option>Mixing & Mastering</option>
            <option>Music Production</option>
            <option>Audio Editing</option>
            <option>Artist Session</option>
        </select>

        <input
            type="date"
            id="date"
            required
        >

        <textarea
            id="message"
            placeholder="Tell us about your project..."
        ></textarea>

        <button class="btn btn-primary" type="submit">
            📲 Send Booking Request
        </button>

    </form>

</section>


<!-- CONTACT -->
<section id="contact">

    <div class="contact">

        <div class="section-title">
            <h2>Let's Create <span class="gradient">Music</span></h2>
            <p>Contact Laykari Echoverse Studio Communication.</p>
        </div>

        <div class="contact-info">
            📞 Phone: +91 XXXXXXXXXX<br>
            📧 Email: yourstudio@email.com<br>
            📍 Location: Your City, India
        </div>

        <div class="socials">
            <a href="#" target="_blank">Instagram</a>
            <a href="#" target="_blank">YouTube</a>
            <a href="#" target="_blank">Facebook</a>
        </div>

    </div>

</section>


<footer>

    <h3>Laykari Echoverse Studio Communication</h3>

    <p>
        © <span id="year"></span> All Rights Reserved.
    </p>

</footer>


<script>

function toggleMenu(){

    document
    .getElementById("navLinks")
    .classList.toggle("active");

}


// Close mobile menu after clicking link

document.querySelectorAll("#navLinks a").forEach(function(link){

    link.addEventListener("click",function(){

        document
        .getElementById("navLinks")
        .classList.remove("active");

    });

});


// Booking WhatsApp

function sendBooking(event){

    event.preventDefault();

    const name =
        document.getElementById("name").value;

    const phone =
        document.getElementById("phone").value;

    const service =
        document.getElementById("service").value;

    const date =
        document.getElementById("date").value;

    const message =
        document.getElementById("message").value;


    /*
      IMPORTANT:
      Replace 919999999999 with your
      WhatsApp number including country code.
    */

    const whatsappNumber = "919999999999";


    const text =
        "🎵 *Laykari Echoverse Studio Communication*%0A%0A" +
        "*New Booking Request*%0A%0A" +
        "👤 Name: " + name + "%0A" +
        "📱 Phone: " + phone + "%0A" +
        "🎧 Service: " + service + "%0A" +
        "📅 Date: " + date + "%0A" +
        "📝 Message: " + message;


    const url =
        "https://wa.me/" +
        whatsappNumber +
        "?text=" +
        text;


    window.open(url,"_blank");

}


// Current year

document.getElementById("year").textContent =
    new Date().getFullYear();

</script>

</body>
</html>
