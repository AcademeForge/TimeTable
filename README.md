
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AcademeForge Timetable</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Select Your Class</h1>
        <div id="classSelection">
            <button onclick="selectClass('1-2')">Class 1 & 2</button>
            <button onclick="selectClass('3-4')">Class 3 & 4</button>
            <button onclick="selectClass('5-6')">Class 5 & 6</button>
            <button onclick="selectClass('7-8')">Class 7 & 8</button>
            <button onclick="selectClass('9-10')">Class 9 & 10</button>
            <button onclick="selectClass('11-12')">Class 11 & 12</button>
        </div>

        <div id="streamSelection" class="hidden">
            <h2>Select Your Stream</h2>
            <button onclick="selectStream('Science')">Science</button>
            <button onclick="selectStream('Commerce')">Commerce</button>
            <button onclick="selectStream('Arts')">Arts</button>
        </div>

        <div id="modeSelection" class="hidden">
            <h2>Select Mode</h2>
            <button onclick="selectMode('Regular')">Regular</button>
            <button onclick="selectMode('Dummy')">Dummy</button>
        </div>

        <div id="timetableSection" class="hidden">
            <h2>Your Timetable</h2>
            <table id="timetable">
                <tr>
                    <th>Time</th>
                    <th>Activity</th>
                </tr>
                <tr>
                    <td>6:00 AM</td>
                    <td contenteditable="true">Wake Up</td>
                </tr>
                <tr>
                    <td>7:00 AM</td>
                    <td contenteditable="true">Study</td>
                </tr>
                <tr>
                    <td>8:00 AM</td>
                    <td contenteditable="true">Breakfast</td>
                </tr>
            </table>
            <button onclick="setReminder()">Set Reminder</button>
        </div>
    </div>

    <script src="script.js"></script>
body {
    font-family: Arial, sans-serif;
    background-color: #121212;
    color: white;
    text-align: center;
}

.container {
    width: 90%;
    margin: auto;
    max-width: 400px;
    padding: 20px;
    border-radius: 10px;
    background: #1e1e1e;
    box-shadow: 0px 4px 10px rgba(255, 255, 255, 0.1);
}

button {
    width: 100%;
    padding: 10px;
    margin: 5px 0;
    border: none;
    border-radius: 5px;
    background: #00c853;
    color: white;
    font-size: 18px;
    cursor: pointer;
    transition: 0.3s;
}

button:hover {
    background: #009624;
}

.hidden {
    display: none;
}

table {
    width: 100%;
    margin-top: 10px;
    border-collapse: collapse;
}

th, td {
    border: 1px solid #555;
    padding: 8px;
}

td {
    background: #333;
}

td[contenteditable="true"] {
    cursor: pointer;
}
let selectedClass = "";
let selectedStream = "";
let selectedMode = "";

function selectClass(classGroup) {
    selectedClass = classGroup;
    document.getElementById("classSelection").classList.add("hidden");

    if (classGroup === "11-12") {
        document.getElementById("streamSelection").classList.remove("hidden");
    } else {
        document.getElementById("modeSelection").classList.remove("hidden");
    }
}

function selectStream(stream) {
    selectedStream = stream;
    document.getElementById("streamSelection").classList.add("hidden");
    document.getElementById("modeSelection").classList.remove("hidden");
}

function selectMode(mode) {
    selectedMode = mode;
    document.getElementById("modeSelection").classList.add("hidden");
    document.getElementById("timetableSection").classList.remove("hidden");
}

function setReminder() {
    alert("Reminder Set!");
}
</body>
</html>