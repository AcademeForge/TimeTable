
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>AcademeForge</title>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600&display=swap');

    :root {
      --bg-color: #0f2027;
      --bg-gradient: linear-gradient(120deg, #0f2027, #203a43, #2c5364);
      --text-color: #ffffff;
      --table-text: #00b0ff;
      --table-bg: rgba(255,255,255,0.1);
    }

    body.light-mode {
      --bg-color: #ffffff;
      --bg-gradient: linear-gradient(120deg, #e3f2fd, #bbdefb, #90caf9);
      --text-color: #000000;
      --table-text: #0d47a1;
      --table-bg: rgba(0, 0, 0, 0.05);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Poppins', sans-serif;
      transition: background 0.4s, color 0.4s;
    }

    body {
      background: var(--bg-gradient);
      color: var(--text-color);
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
      flex-wrap: wrap;
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

    .switch-mode {
      margin-bottom: 2rem;
    }

    .timetable {
      width: 100%;
      max-width: 800px;
      background: var(--table-bg);
      border-radius: 20px;
      overflow: hidden;
      box-shadow: 0 10px 25px rgba(0,0,0,0.3);
      animation: fadeInUp 1s ease;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      color: var(--table-text);
    }

    th, td {
      padding: 1rem;
      text-align: center;
      border-bottom: 1px solid rgba(255,255,255,0.1);
    }

    th {
      background-color: rgba(0,198,255,0.2);
      color: var(--table-text);
    }

    tr:last-child td {
      border-bottom: none;
    }

    .footer {
      margin-top: auto;
      padding: 1rem;
      font-size: 0.9rem;
      color: var(--text-color);
}
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
<body class="dark-mode">
  <h1>AcademeForge Time Table</h1>

  <div class="switch-mode">
    <button onclick="toggleMode()">Switch Mode</button>
  </div>

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
        <tr><th>Time</th><th>Activity / Subject</th></tr>
        <tr><td>6:30 – 7:00 AM</td><td>Wake up & Freshen up</td></tr>
        <tr><td>7:00 – 7:30 AM</td><td>Light Exercise / Meditation</td></tr>
        <tr><td>7:30 – 8:00 AM</td><td>Breakfast</td></tr>
        <tr><td>8:00 – 9:00 AM</td><td>Math (Concept + Practice)</td></tr>
        <tr><td>9:00 – 10:00 AM</td><td>Science (Theory + Diagrams)</td></tr>
        <tr><td>10:00 – 10:15 AM</td><td>Short Break</td></tr>
        <tr><td>10:15 – 11:00 AM</td><td>English (Grammar + Reading)</td></tr>
        <tr><td>11:00 – 11:45 AM</td><td>Social Science (1 Chapter)</td></tr>
        <tr><td>11:45 – 12:30 PM</td><td>Hindi (Reading + Writing)</td></tr>
        <tr><td>12:30 – 1:30 PM</td><td>Lunch + Rest</td></tr>
        <tr><td>1:30 – 2:30 PM</td><td>Revision / Homework</td></tr>
        <tr><td>2:30 – 4:00 PM</td><td>Free Time / Hobbies</td></tr>
        <tr><td>4:00 – 5:00 PM</td><td>Doubts / Online Learning</td></tr>
        <tr><td>5:00 – 5:30 PM</td><td>Snacks + Relaxation</td></tr>
        <tr><td>5:30 – 6:30 PM</td><td>Mixed Practice (MCQs / PYQs)</td></tr>
        <tr><td>6:30 – 7:30 PM</td><td>Outdoor Walk / Light Games</td></tr>
        <tr><td>7:30 – 8:00 PM</td><td>Dinner</td></tr>
        <tr><td>8:00 – 9:00 PM</td><td>Light Study / Revision</td></tr>
        <tr><td>9:00 – 9:30 PM</td><td>Plan for Tomorrow / Chill</td></tr>
        <tr><td>9:30 PM</td><td>Sleep</td></tr>
      </table>`;

    const regularTable = `
      <table>
        <tr><th>Time</th><th>Activity / Subject</th></tr>
        <tr><td>5:00 – 5:30 AM</td><td>Wake up & Freshen up</td></tr>
        <tr><td>5:30 – 6:00 AM</td><td>Light Exercise / Yoga</td></tr>
        <tr><td>6:00 – 6:45 AM</td><td>Math Revision / Practice</td></tr>
        <tr><td>6:45 – 7:15 AM</td><td>Breakfast & Get Ready</td></tr>
        <tr><td>7:15 – 8:00 AM</td><td>Travel / Prepare for School</td></tr>
        <tr><td>8:00 – 2:00 PM</td><td>School Time</td></tr>
        <tr><td>2:00 – 2:30 PM</td><td>Lunch + Relax</td></tr>
        <tr><td>2:30 – 3:30 PM</td><td>Nap / Rest Time</td></tr>
        <tr><td>3:30 – 4:30 PM</td><td>Science or Social Homework</td></tr>
        <tr><td>4:30 – 5:00 PM</td><td>Snacks + Chill</td></tr>
        <tr><td>5:00 – 6:00 PM</td><td>English or Hindi Practice</td></tr>
        <tr><td>6:00 – 7:00 PM</td><td>Doubt-solving / MCQ Practice</td></tr>
        <tr><td>7:00 – 7:45 PM</td><td>Dinner</td></tr>
        <tr><td>7:45 – 8:30 PM</td><td>Light Revision (any subject)</td></tr>
        <tr><td>8:30 – 9:00 PM</td><td>Plan for next day / Relax</td></tr>
        <tr><td>9:00 PM</td><td>Sleep</td></tr>
      </table>`;

    function showTimetable(type) {
      const container = document.getElementById("timetable-container");
      container.style.animation = "none";
      void container.offsetWidth;
      container.style.animation = "fadeInUp 1s ease";

      container.innerHTML = type === "dummy" ? dummyTable : regularTable;
    }

    function toggleMode() {
      document.body.classList.toggle('light-mode');
    }

    // Default timetable
    showTimetable("regular");
  </script>
</body>
</html>






    
    