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
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

header {
    background: #333;
    color: #fff;
    padding: 1rem 0;
}

.container {
    width: 80%;
    margin: 0 auto;
}

nav ul {
    list-style: none;
    padding: 0;
}

nav ul li {
    display: inline;
    margin-right: 1rem;
}

nav ul li a {
    color: #fff;
    text-decoration: none;
}

.hero {
    background: url('hero-image.jpg') no-repeat center center/cover;
    color: #fff;
    text-align: center;
    padding: 5rem 0;
}

.services, .about, .contact {
    padding: 2rem 0;
    text-align: center;
}

.service {
    margin-bottom: 1rem;
}

footer {
    background: #333;
    color: #fff;
    text-align: center;
    padding: 1rem 0;
}

#contact-form {
    display: flex;
    flex-direction: column;
    align-items: center;
}

#contact-form label, #contact-form input, #contact-form textarea, #contact-form button {
    width: 100%;
    max-width: 500px;
    margin-bottom: 0.5rem;
}

#chatbox {
    position: fixed;
    bottom: 0;
    right: 1rem;
    width: 300px;
    border: 1px solid #ccc;
    display: none;
    flex-direction: column;
}

.chatbox-header {
    background: #333;
    color: #fff;
    padding: 0.5rem;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

.chatbox-content {
    background: #fff;
    padding: 0.5rem;
    flex: 1;
    overflow-y: auto;
}

.chatbox-input {
    display: flex;
    padding: 0.5rem;
    background: #f4f4f4;
}

.chatbox-input input {
    flex: 1;
    padding: 0.5rem;
    border: 1px solid #ccc;
    border-radius: 0;
}

.chatbox-input button {
    padding: 0.5rem;
    background: #333;
    color: #fff;
    border: none;
}
function openChat() {
    document.getElementById('chatbox').style.display = 'flex';
}

function closeChat() {
    document.getElementById('chatbox').style.display = 'none';
}

function sendMessage() {
    const input = document.getElementById('chat-input');
    const message = input.value.trim();
    if (message) {
        const messagesContainer = document.querySelector('.chatbox .messages');
        const userMessage = document.createElement('div');
        userMessage.classList.add('message', 'user-message');
        userMessage.textContent = message;
        messagesContainer.appendChild(userMessage);
        
        // Simulate chatbot response
        const botMessage = document.createElement('div');
        botMessage.classList.add('message', 'bot-message');
        botMessage.textContent = 'This is a response from the chatbot.';
        messagesContainer.appendChild(botMessage);

        input.value = '';
        messagesContainer.scrollTop = messagesContainer.scrollHeight;
    }
}

// Handle contact form submission
document.getElementById('contact-form').addEventListener('submit', function(event) {
    event.preventDefault();
    alert('Message sent successfully!');
});
