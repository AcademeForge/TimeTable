<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AcademeForge</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <!-- Top Banner -->
    <header>
        <div class="banner">
            <h1>Welcome to AcademeForge</h1>
        </div>
    </header>

    <!-- Navigation -->
    <nav>
        <ul>
            <li><a href="index.html">Home</a></li>
            <li><a href="about.html">About Us</a></li>
            <li><a href="contact.html">Contact</a></li>
            <li><a href="login.html">Login</a></li>
        </ul>
    </nav>

    <!-- Homepage Content -->
    <section class="homepage">
        <h2>Explore AcademeForge</h2>
        <div class="options">
            <a href="class-selection.html?type=notes" class="btn">Access Notes</a>
            <a href="class-selection.html?type=lectures" class="btn">Watch Lectures</a>
            <div class="social-links">
                <h3>Follow Us</h3>
                <a href="[SPACE]" class="social-btn">Instagram</a>
                <a href="[SPACE]" class="social-btn">Twitter</a>
                <a href="[SPACE]" class="social-btn">Telegram</a>
                <a href="[SPACE]" class="social-btn">YouTube</a>
                <a href="[SPACE]" class="social-btn">Facebook</a>
            </div>
            <a href="mailto:AcademeForge@gmail.com" class="btn">Send Us Your Query</a>
        </div>
    </section>

    <!-- Chat Box -->
    <div class="chat-box">
        <p>Need Help? Chat with us!</p>
        <!-- [SPACE for chat integration] -->
    </div>

    <!-- Footer -->
    <footer>
        <p>&copy; 2025 AcademeForge. All rights reserved.</p>
    </footer>
</script>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Login - AcademeForge</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <section class="login-page">
        <h2>Login</h2>
        <form>
            <input type="text" placeholder="Username or Email" required>
            <input type="password" placeholder="Password" required>
            <button type="submit">Login</button>
            <p><a href="[SPACE]">Forgot Password?</a></p>
            <p>Not a member? <a href="[SPACE]">Sign Up</a></p>
        </form>
    </section>
</script>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Us - AcademeForge</title>
    <link rel="stylesheet" href="styles.css">
</script>

    <section class="about-page">
        <h2>About Us</h2>
        <p>[SPACE for your text]</p>
    </section>
</script>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact - AcademeForge</title>
    <link rel="stylesheet" href="styles.css">
</script>

    <section class="contact-page">
        <h2>Contact Us</h2>
        <p>Email: <a href="mailto:AcademeForge@gmail.com">AcademeForge@gmail.com</a></p>
        <form>
            <input type="text" placeholder="Your Name" required>
            <input type="email" placeholder="Your Email" required>
            <textarea placeholder="Your Message" required></textarea>
            <button type="submit">Submit</button>
        </form>
        <div class="social-links">
            <a href="[SPACE]" class="social-btn">Instagram</a>
            <a href="[SPACE]" class="social-btn">Twitter</a>
            <a href="[SPACE]" class="social-btn">Telegram</a>
            <a href="[SPACE]" class="social-btn">YouTube</a>
            <a href="[SPACE]" class="social-btn">Facebook</a>
        </div>
    </section>
</script>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Class Selection - AcademeForge</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <section class="class-selection">
        <h2>Select Your Class</h2>
        <div class="class-options">
            <a href="notes.html?class=9" class="btn">Class 9</a>
            <a href="notes.html?class=10" class="btn">Class 10</a>
            <a href="stream-selection.html?class=11" class="btn">Class 11</a>
            <a href="stream-selection.html?class=12" class="btn">Class 12</a>
        </div>
    </section>
</script>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stream Selection - AcademeForge</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <section class="stream-selection">
        <h2>Select Your Stream</h2>
        <div class="stream-options">
            <a href="notes.html?class=11&stream=science" class="btn">Science</a>
            <a href="notes.html?class=11&stream=commerce" class="btn">Commerce</a>
            <a href="notes.html?class=11&stream=arts" class="btn">Arts</a>
        </div>
    </section>
</script>

/* Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

body {
    font-family: Arial, sans-serif;
    line-height: 1.6;
}

/* Banner */
.banner {
    background-color: #007bff;
    color: white;
    text-align: center;
    padding: 20px;
}

/* Navigation */
nav {
    background-color: #333;
    padding: 10px;
}
nav ul {
    list-style: none;
    display: flex;
    justify-content: center;
}
nav ul li {
    margin: 0 15px;
}
nav ul li a {
    color: white;
    text-decoration: none;
}

/* Homepage */
.homepage {
    text-align: center;
    padding: 40px;
}
.options {
    margin-top: 20px;
}
.btn {
    display: inline-block;
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    text-decoration: none;
    margin: 10px;
    border-radius: 5px;
}
.social-links {
    margin: 20px 0;
}
.social-btn {
    background-color: #555;
    padding: 8px 15px;
    color: white;
    text-decoration: none;
    margin: 5px;
    border-radius: 5px;
}

/* Chat Box */
.chat-box {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: #007bff;
    color: white;
    padding: 10px;
    border-radius: 5px;
}

/* Login Page */
.login-page {
    text-align: center;
    padding: 50px;
}
.login-page form {
    display: flex;
    flex-direction: column;
    max-width: 300px;
    margin: 0 auto;
}
.login-page input, .contact-page textarea {
    margin: 10px 0;
    padding: 8px;
}
.login-page button, .contact-page button {
    padding: 10px;
    background-color: #007bff;
    color: white;
    border: none;
    border-radius: 5px;
}

/* About & Contact Pages */
.about-page, .contact-page {
    text-align: center;
    padding: 50px;
}

/* Class & Stream Selection */
.class-selection, .stream-selection {
    text-align: center;
    padding: 50px;
}
.class-options, .stream-options {
    margin-top: 20px;
}

/* Footer */
footer {
    text-align: center;
    padding: 20px;
    background-color: #333;
    color: white;
    position: fixed;
    bottom: 0;
    width: 100%;
}

</script>

</body>
</html>


