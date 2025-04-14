
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AcademeForge Scholars Test Registration</title>
  <style>
    body { font-family: Arial, sans-serif; background: #f4f4f4; padding: 20px; }
    form { max-width: 600px; margin: auto; background: #fff; padding: 20px; border-radius: 10px; }
    label { display: block; margin: 10px 0 5px; }
    input, select, textarea { width: 100%; padding: 8px; }
    .conditional { display: none; }
    button { margin-top: 20px; padding: 10px 20px; background: #007BFF; color: white; border: none; border-radius: 5px; cursor: pointer; }
  </style>
</head>
<body>

  <h2>AcademeForge Scholars Test Registration</h2>

  <form id="registrationForm">
    
    <!-- Form Fields -->
    <label for="name">Full Name*</label>
    <input type="text" id="name" name="name" required>

    <label for="class">Class*</label>
    <select id="class" name="class" required>
      <option value="">Select Class</option>
      <option value="1">1</option>
      <option value="2">2</option>
      <option value="3">3</option>
      <option value="4">4</option>
      <option value="5">5</option>
      <option value="6">6</option>
      <option value="7">7</option>
      <option value="8">8</option>
      <option value="9">9</option>
      <option value="10">10</option>
    </select>

    <label for="Pincode">pincode*</label>
<input type="text" id="pincode" name="pincode" required>

    <label for="mode">Mode (Offline/Online)*</label>
    <select id="mode" name="mode" onchange="toggleOfflineFields()" required>
      <option value="">Select Mode</option>
      <option value="Offline">Offline</option>
      <option value="Online">Online</option>
    </select>

    <label for="schoolName">School Name*</label>
<input type="text" id="schoolName" name="schoolName" required>

<label for="schoolAddress">School Address*</label>
<input type="text" id="schoolAddress" name="schoolAddress" required>

    <label for="mobile">Mobile Number*</label>
    <input type="tel" id="mobile" name="mobile" required pattern="[0-9]{10}">

    <label for="email">Email Address*</label>
    <input type="email" id="email" name="email" required>

    <label for="gender">Gender*</label>
    <select id="gender" name="gender" required>
      <option value="">Select Gender</option>
      <option value="Male">Male</option> <option value="Female">Female</option> <option value="Other">Other</option>
    </select>

    <label for="dob">Date of Birth*</label>
    <input type="date" id="dob" name="dob" required>
<!-- Payment Info before screenshot -->
    <label><strong>Step 1: Pay the Test Fee</strong></label>
    <p>Pay <strong>₹50</strong> to UPI ID <strong>devrajkumar01@ybl</strong> using any UPI app (PhonePe, Google Pay, etc.).</p>
    <p><strong>Note:</strong> After payment, upload the screenshot below.</p>

    <!-- UPI Pay Button -->
    <a href="upi://pay?pa=devrajkumar01@ybl&pn=Devraj+Kumar&mc=0000&tid=1234567890&tr=1234567890&tn=Test+Payment&am=50&cu=INR" 
       target="_blank">
       <button type="button">Pay ₹50 Now</button>
    </a>

    <label for="screenshot">Upload Payment Screenshot*</label>
    <input type="file" id="screenshot" name="screenshot" accept="image/*" required>

    <button type="submit">Register Now</button>
  </form>

     <script>
    document.getElementById("registrationForm").addEventListener("submit",function(e) {
      e.preventDefault();
  const form = e.target;
      const formData = new FormData(form);

   
      fetch("https://script.google.com/macros/s/AKfycbxKUHRKkUA8Mt42QGrYR07fDye-tcs9R6_qkCJsv8osOpyG_gus6_9Xa7AyhzNjx84SpQ/exec", {
        method: "POST",
     body: formData})      

      .then(response => response.text())
      .then(result => {
        alert("Registration successful!");
        form.reset();
      })
      .catch(error => {
        alert("Error submitting form.");
        console.error(error);
      });
    });
  </script>

<!-- Telegram Button and Instructions -->
<div style="margin-top: 30px; background: #f9f9f9; padding: 20px; border-radius: 10px;">
  <h3>After Form Submission</h3>
  <p><strong>Important:</strong> Please send your <strong>payment screenshot</strong>, <strong>School Name</strong>, and <strong>School Address</strong> to our official Telegram handle:</p>
  <a href="https://t.me/AcademeaForgeScholarsTest_AST" target="_blank">
    <button style="background-color: #0088cc;">Send Details via Telegram</button>
  </a>
  <p>Or you can email us at: <strong>academeforge@gmail.com</strong></p>
</div>

<!-- Captcha Checkbox with Timer -->
<div style="margin-top: 30px;">
  <label>
    <input type="checkbox" id="humanCheck" disabled>
    I am not a robot (wait 3 seconds)
  </label>
</div>

<!-- Hidden Success Message -->
<div id="successMessage" style="display: none; margin-top: 30px; padding: 20px; background: #d4edda; border-left: 5px solid #28a745; border-radius: 10px;">
  <h3>Congratulations!</h3>
  <p>You have successfully submitted the Application for <strong>AST</strong>.</p>
  <p>If you are a <strong>school authority</strong>, our team will visit your school soon.</p>
  <p>If you're an <strong>independent student</strong>, our team will call you soon.</p>
  <p>Make sure to send the <strong>payment screenshot</strong> and your <strong>School Name & Address</strong> on Telegram (<a href="https://t.me/AcademeaForgeScholarsTest_AST" target="_blank">@AcademeaForgeScholarsTest_AST</a>) or via Email at <strong>academeforge@gmail.com</strong>.</p>
  <p><strong>Thank you</strong> for participating in the AcademeForge Scholars Test. We wish you the best of luck!</p>
  <p style="color: red; font-weight: bold;">With love ♥️ from Team AcademeForge</p>
</div>

<script>
  // Enable checkbox after 3 seconds
  window.onload = () => {
    setTimeout(() => {
      document.getElementById('humanCheck').disabled = false;
    }, 3000);
  };

  // Update existing form submit logic to show success message
  const originalSubmitHandler = document.getElementById("registrationForm").onsubmit;
  document.getElementById("registrationForm").addEventListener("submit", function(e) {
    e.preventDefault();
    
    // Human check
    if (!document.getElementById('humanCheck').checked) {
      alert("Please verify that you're not a robot.");
      return;
    }

    const form = e.target;
    const formData = new FormData(form);

    fetch("https://script.google.com/macros/s/AKfycbxKUHRKkUA8Mt42QGrYR07fDye-tcs9R6_qkCJsv8osOpyG_gus6_9Xa7AyhzNjx84SpQ/exec", {
      method: "POST",
      body: formData
    })
    .then(response => response.text())
    .then(result => {
      form.reset();
      document.getElementById("successMessage").style.display = "block";
      window.scrollTo({ top: document.body.scrollHeight, behavior: 'smooth' });
    })
    .catch(error => {
      alert("Error submitting form.");
      console.error(error);
    });
  });
</script>

</body>
</html>