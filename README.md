
<html>
<head>
  <title>AcademeForge Scholars Test Registration</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <style>
    body { font-family: Arial, sans-serif; max-width: 500px; margin: auto; padding: 20px; }
    input, select, textarea { width: 100%; padding: 10px; margin: 10px 0; }
    button { background-color: #4CAF50; color: white; padding: 10px; border: none; cursor: pointer; }
    button:hover { background-color: #45a049; }
  </style>
</head>
<body>
  <h2>AcademeForge Scholars Test</h2>
  <form id="registrationForm">
    <input type="text" name="name" placeholder="Full Name" required>
    <input type="text" name="class" placeholder="Class" required>
    <input type="text" name="pincode" placeholder="School Code" required>
    
    <select name="mode" required>
      <option value="">Select Mode</option>
      <option value="Online">Online</option>
      <option value="Offline">Offline</option>
    </select>
    
    <input type="text" name="schoolName" placeholder="School Name" required>
    <textarea name="schoolAddress" placeholder="School Address" required></textarea>
    <input type="tel" name="mobile" placeholder="Mobile Number" required>
    <input type="email" name="email" placeholder="Email Address" required>

    <p><strong>Pay Now:</strong> <br> UPI ID: <b>academeforge@okaxis</b> <br>Scan & pay using any UPI app, then upload the payment screenshot below.</p>
    
    <input type="file" id="screenshot" accept="image/*" required>
    <input type="hidden" id="fileData">
    <input type="hidden" id="fileName">
    <input type="hidden" id="mimeType">

    <button type="submit">Submit</button>
  </form>

  <script>
    document.getElementById("screenshot").addEventListener("change", function () {
      const file = this.files[0];
      if (file) {
        const reader = new FileReader();
        reader.onload = function () {
          const base64String = reader.result.split(',')[1];
          document.getElementById("fileData").value = base64String;
          document.getElementById("fileName").value = file.name;
          document.getElementById("mimeType").value = file.type;
        };
        reader.readAsDataURL(file);
      }
    });

    document.getElementById("registrationForm").addEventListener("submit", function (e) {
      e.preventDefault();

      const form = e.target;
      const data = {
        name: form.name.value,
        class: form.class.value,
        pincode: form.pincode.value,
        mode: form.mode.value,
        schoolName: form.schoolName.value,
        schoolAddress: form.schoolAddress.value,
        mobile: form.mobile.value,
        email: form.email.value,
        fileData: document.getElementById("fileData").value,
        fileName: document.getElementById("fileName").value,
        mimeType: document.getElementById("mimeType").value
      };

      fetch("https://script.google.com/macros/s/AKfycbxKUHRKkUA8Mt42QGrYR07fDye-tcs9R6_qkCJsv8osOpyG_gus6_9Xa7AyhzNjx84SpQ/exec", {
        method: "POST",
        body: JSON.stringify(data),
        headers: { "Content-Type": "application/json" }
      })
      .then(res => res.json())
      .then(res => {
        if (res.status === "success") {
          alert("Registration successful!");
          form.reset();
        } else {
          alert("Error: " + res.message);
        }
      })
      .catch(err => {
        alert("Submission failed: " + err.message);
      });
    });
  </script>
</body>
</html>