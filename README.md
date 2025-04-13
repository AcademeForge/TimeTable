
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
    button { margin-top: 20px; padding: 10px 20px; background: #007BFF; color: white; border: none; border-radius: 5px; }
  </style>
  <script>
    function toggleOfflineFields() {
      const mode = document.getElementById("mode").value;
      const offlineFields = document.querySelectorAll(".offline-only");
      offlineFields.forEach(field => {
        field.style.display = (mode === "Offline") ? "block" : "none";
      });
    }
  </script>
</head>
<body>

  <h2>AcademeForge Scholars Test Registration</h2>

  <form action="https://formsubmit.co/your@email.com" method="POST" enctype="multipart/form-data">
    <!-- Redirect after submit (optional) -->
    <input type="hidden" name="_next" value="https://yourwebsite.com/thankyou.html">

    <!-- Disable captcha -->
    <input type="hidden" name="_captcha" value="false">

    <label for="name">Full Name*</label>
    <input type="text" id="name" name="Name" required>

    <label for="class">Class*</label>
    <select id="class" name="Class" required>
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

    <label for="pincode">Pincode*</label>
    <input type="text" id="pincode" name="Pincode" required>

    <label for="mode">Mode (Offline/Online)*</label>
    <select id="mode" name="Mode" onchange="toggleOfflineFields()" required>
      <option value="">Select Mode</option>
      <option value="Offline">Offline</option>
      <option value="Online">Online</option>
    </select>

    <div class="offline-only conditional">
      <label for="school-name">School Name*</label>
      <input type="text" id="school-name" name="School Name">

      <label for="school-address">School Address*</label>
      <textarea id="school-address" name="School Address"></textarea>
    </div>

    <label for="mobile">Mobile Number*</label>
    <input type="tel" id="mobile" name="Mobile Number" required pattern="[0-9]{10}">

    <label for="email">Email Address*</label>
    <input type="email" id="email" name="Email Address" required>

    <label for="gender">Gender*</label>
    <select id="gender" name="Gender" required>
      <option value="">Select Gender</option>
      <option value="Male">Male</option>
      <option value="Female">Female</option>
      <option value="Other">Other</option>
    </select>

    <label for="dob">Date of Birth*</label>
    <input type="date" id="dob" name="Date of Birth" required>
Pay the test fee of <strong>₹50</strong> to <strong>devrajkumar01@ybl</strong> using any UPI app (PhonePe, Google Pay, Paytm, etc.).</p>
<p><strong>Note:</strong> Please complete the payment before submitting the form and upload the payment screenshot below.</p>
    <label for="screenshot">Upload Payment Screenshot*</label>
    <input type="file" id="screenshot" name="Payment Screenshot" accept="image/*" required>

    <button type="submit">Register Now</button>
  </form>

</body>
</html>