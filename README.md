<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hippokrates - Healthcare Chatbot Service</title>
    <link rel="stylesheet" href="styles.css">
    <script src="script.js" defer></script>
</head>
<body>
    <header>
        <div class="container">
            <h1>Hippokrates</h1>
            <nav>
                <ul>
                    <li><a href="#home">Home</a></li>
                    <li><a href="#services">Services</a></li>
                    <li><a href="#about">About Us</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section id="home" class="hero">
        <div class="container">
            <h2>Your Health, Our Priority</h2>
            <p>Experience personalized healthcare suggestions with our advanced AI chatbot.</p>
            <button onclick="openChat()">Chat Now</button>
        </div>
    </section>

    <section id="services" class="services">
        <div class="container">
            <h2>Our Services</h2>
            <div class="service">
                <h3>24/7 Chatbot Assistance</h3>
                <p>Get healthcare suggestions anytime, anywhere.</p>
            </div>
            <div class="service">
                <h3>Personalized Health Tips</h3>
                <p>Receive tips tailored to your specific health needs.</p>
            </div>
            <div class="service">
                <h3>Health Monitoring</h3>
                <p>Track your health metrics and get actionable insights.</p>
            </div>
        </div>
    </section>

    <section id="about" class="about">
        <div class="container">
            <h2>About Us</h2>
            <p>Hippokrates is dedicated to improving your health through advanced AI technology. Our chatbot provides reliable healthcare suggestions based on the latest medical research and your personal health data.</p>
        </div>
    </section>

    <section id="contact" class="contact">
        <div class="container">
            <h2>Contact Us</h2>
            <form id="contact-form">
                <label for="name">Name:</label>
                <input type="text" id="name" name="name" required>
                
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" required>
                
                <label for="message">Message:</label>
                <textarea id="message" name="message" required></textarea>
                
                <button type="submit">Send Message</button>
            </form>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>&copy; 2024 Hippokrates. All rights reserved.</p>
        </div>
    </footer>

    <div id="chatbox" class="chatbox">
        <div class="chatbox-header">
            <h3>Hippokrates Chatbot</h3>
            <button onclick="closeChat()">X</button>
        </div>
        <div class="chatbox-content">
            <div class="messages"></div>
        </div>
        <div class="chatbox-input">
            <input type="text" id="chat-input" placeholder="Type your message...">
            <button onclick="sendMessage()">Send</button>
        </div>
    </div>
</body>
</html>
