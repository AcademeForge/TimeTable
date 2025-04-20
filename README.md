
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>AcademeForge Time Table</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
    }

    body {
      background: linear-gradient(120deg, #0f2027, #203a43, #2c5364);
      color: #fff;
      display: flex;
      flex-direction: column;
      align-items: center;
      min-height: 100vh;
      overflow-x: hidden;
      padding: 2rem;
    }

    h1 {
      margin-bottom: 1rem;
      font-size: 2.5rem;
      animation: fadeInDown 1s ease;
    }

    .btn-group {
      display: flex;
      gap: 1rem;
      margin-bottom: 2rem;
    }

    button {
      padding: 0.6rem 1.5rem;
      background: #00c6ff;
      border: none;
      border-radius: 10px;
      color: #000;
      font-weight: bold;
      cursor: pointer;
      box-shadow: 0 4px 15px rgba(0,198,255,0.4);
      transition: transform 0.3s, background 0.3s;
    }

    button:hover {
      background: #00acc1;
      transform: scale(1.05);
    }

    .timetable {
      width: 100%;
      max-width: 800px;
      background: rgba(255,255,255,0.1);
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
      animation: fadeInUp 1s ease;
    }

    table {
      width: 100%;
      border-collapse: collapse;
    }

    th, td {
      padding: 1rem;
      text-align: center;
      border-bottom: 1px solid rgba(255,255,255,0.1);
    }

    th {
      background-color: rgba(0,198,255,0.2);
    }

    tr:last-child td {
      border-bottom: none;
    }

    .footer {
      margin-top: auto;
      padding: 1rem;
      font-size: 0.9rem;
      color: #ccc;
    }

    @keyframes fadeInDown {
      from { opacity: 0; transform: translateY(-30px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(30px); }
      to { opacity: 1; transform: translateY(0); }
    }
  </style>
</head>
<body>
  <h1>AcademeForge Time Table</h1>
  <div class="btn-group">
    <button onclick="showTimetable('dummy')">Dummy</button>
    <button onclick="showTimetable('regular')">Regular</button>
  </div>

  <div class="timetable" id="timetable-container">
    <!-- Table will be injected here -->
  </div>

  <div class="footer">© 2025 AcademeForge. All rights reserved.</div>

  <script>
    const dummyTable = `
      <table>
        <tr><th>Time</th><th>Monday</th><th>Tuesday</th><th>Wednesday</th><th>Thursday</th><th>Friday</th></tr>
        <tr><td>8:00 - 9:00</td><td>Maths</td><td>Science</td><td>English</td><td>GK</td><td>Activity</td></tr>
        <tr><td>9:15 - 10:15</td><td>Drawing</td><td>Hindi</td><td>EVS</td><td>Maths</td><td>Computer</td></tr>
        <tr><td>10:30 - 11:30</td><td>Break</td><td>Break</td><td>Break</td><td>Break</td><td>Break</td></tr>
        <tr><td>11:30 - 12:30</td><td>Dance</td><td>Music</td><td>Craft</td><td>Story</td><td>Games</td></tr>
      </table>`;

    const regularTable = `
      <table>
        <tr><th>Time</th><th>Monday</th><th>Tuesday</th><th>Wednesday</th><th>Thursday</th><th>Friday</th></tr>
        <tr><td>6:30 - 7:30</td><td>Physics</td><td>Chemistry</td><td>Biology</td><td>Physics</td><td>Chemistry</td></tr>
        <tr><td>7:45 - 8:45</td><td>Maths</td><td>English</td><td>Maths</td><td>Hindi</td><td>English</td></tr>
        <tr><td>9:00 - 10:00</td><td>Break</td><td>Break</td><td>Break</td><td>Break</td><td>Break</td></tr>
        <tr><td>10:15 - 11:15</td><td>Biology</td><td>Physics</td><td>Chemistry</td><td>Maths</td><td>Revision</td></tr>
      </table>`;

    function showTimetable(type) {
      const container = document.getElementById("timetable-container");
      container.style.animation = "none";
      void container.offsetWidth; // Trigger reflow to restart animation
      container.style.animation = "fadeInUp 1s ease";

      container.innerHTML = type === "dummy" ? dummyTable : regularTable;
    }

    // Load default timetable
    showTimetable("regular");
  </script>
</body>
</html>