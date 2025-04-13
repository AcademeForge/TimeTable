
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
    button:disabled { background: #ccc; cursor: not-allowed; }
  </style>
  <script>
    function toggleOfflineFields() {
      const mode = document.getElementById("mode").value;
      const offlineFields = document.querySelectorAll(".offline-only");
      offlineFields.forEach(field => {
        field.style.display = (mode === "Offline") ? "block" : "none";
      });
    }

    async function handleSubmit(event) {
      event.preventDefault();

      const form = event.target;
      const fileInput = document.getElementById("screenshot").files[0];

      // Validation for required file upload
      if (!fileInput) {
        alert("Please upload a payment screenshot.");
        return;
      }

      const reader = new FileReader();

      reader.onload = async function() {
        const base64 = reader.result.split(',')[1];
        const payload = {
          name: form.name.value,
          class: form.class.value,
          pincode: form.pincode.value,
          mode: form.mode.value,
          schoolName: form["school-name"].value || "",
          schoolAddress: form["school-address"].value || "",
          mobile: form.mobile.value,
          email: form.email.value,
          gender: form.gender.value,
          dob: form.dob.value,
          fileData: base64,
          fileName: fileInput.name,
          mimeType: fileInput.type
        };

  <h2>AcademeForge Scholars Test Registration</h2>

  <form onsubmit="handleSubmit(event)">
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

    <label for="pincode">Pincode*</label>
    <input type="text" id="pincode" name="pincode" required>

    <label for="mode">Mode (Offline/Online)*</label>
    <select id="mode" name="mode" onchange="toggleOfflineFields()" required>
      <option value="">Select Mode</option>
      <option value="Offline">Offline</option>
      <option value="Online">Online</option>
    </select>

    <div class="offline-only conditional">
      <label for="school-name">School Name*</label>
      <input type="text" id="school-name" name="school-name">

      <label for="school-address">School Address*</label>
      <textarea id="school-address" name="school-address"></textarea>
    </div>

    <label for="mobile">Mobile Number*</label>
    <input type="tel" id="mobile" name="mobile" required pattern="[0-9]{10}">

    <label for="email">Email Address*</label>
    <input type="email" id="email" name="email" required>

    <label for="gender">Gender*</label>
    <select id="gender" name="gender" required>
      <option value="">Select Gender</option>
      <option value="Male">Male</option>
      <option value="Female">Female</option>
      <option value="Other">Other</option>
    </select>

    <label for="dob">Date of Birth*</label>
    <input type="date" id="dob" name="dob" required>

    <p><strong>Pay ₹50 to UPI ID:</strong> <code>devrajkumar01@ybl</code> using PhonePe or any UPI app.</p>

    <label for="screenshot">Upload Payment Screenshot*</label>
    <input type="file" id="screenshot" name="screenshot" accept="image/*" required>

    <button type="submit">Register Now</button>
  </form>

<script>
    document.getElementById("registrationForm").addEventListener("submit", function(e) {
      e.preventDefault();
      const form = e.target;
      const formData = new FormData(form);

      fetch("https://script.google.com/macros/s/AKfycbySGATEopKeJGf9eQ9fg6r86-q43FAw64RFEZCX3hVCIKR5fPB0eSUemDe2upE9uhuaag/exec", {
        method: "POST",
        body: formData
      })
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

</body>
</html>