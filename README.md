<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Timetable - AcademeForge</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Select Your Class</h1>
        <div id="class-selection">
            <button onclick="selectClass('1-2')">Class 1 & 2</button>
            <button onclick="selectClass('3-4')">Class 3 & 4</button>
            <button onclick="selectClass('5-6')">Class 5 & 6</button>
            <button onclick="selectClass('7-8')">Class 7 & 8</button>
            <button onclick="selectClass('9-10')">Class 9 & 10</button>
            <button onclick="selectClass('11-12')">Class 11 & 12</button>
        </div>

        <div id="stream-selection" class="hidden">
            <h2>Select Your Stream (Only for Class 11 & 12)</h2>
            <button onclick="selectStream('Science')">Science</button>
            <button onclick="selectStream('Commerce')">Commerce</button>
            <button onclick="selectStream('Arts')">Arts</button>
        </div>

        <div id="timetable-options" class="hidden">
            <h2>Choose Your Study Mode</h2>
            <button onclick="showTimetable('regular')">Regular</button>
            <button onclick="showTimetable('dummy')">Dummy</button>
        </div>

        <div id="timetable" class="hidden">
            <h2>Your Timetable</h2>
            <table id="timetable-table"></table>
            <button onclick="editTimetable()">Modify Timetable</button>
        </div>
    </div>

    <script src="script.js"></script>
</body>
</html>

body {
    font-family: Arial, sans-serif;
    background-color: #121212;
    color: white;
    text-align: center;
    padding: 20px;
}

.container {
    max-width: 400px;
    margin: auto;
    padding: 20px;
    background: #1e1e1e;
    border-radius: 10px;
    box-shadow: 0px 0px 10px rgba(255, 255, 255, 0.1);
}

h1, h2 {
    font-weight: bold;
}

button {
    width: 100%;
    padding: 10px;
    margin: 10px 0;
    border: none;
    background: #03dac6;
    color: black;
    font-size: 16px;
    border-radius: 5px;
    cursor: pointer;
}

button:hover {
    background: #018786;
}

.hidden {
    display: none;
}

table {
    width: 100%;
    border-collapse: collapse;
}

td, th {
    padding: 10px;
    border: 1px solid white;
}

let selectedClass = "";
let selectedStream = "";
let selectedMode = "";

function selectClass(cls) {
    selectedClass = cls;
    document.getElementById("class-selection").classList.add("hidden");

    if (cls === "11-12") {
        document.getElementById("stream-selection").classList.remove("hidden");
    } else {
        document.getElementById("timetable-options").classList.remove("hidden");
    }
}

function selectStream(stream) {
    selectedStream = stream;
    document.getElementById("stream-selection").classList.add("hidden");
    document.getElementById("timetable-options").classList.remove("hidden");
}

function showTimetable(mode) {
    selectedMode = mode;
    document.getElementById("timetable-options").classList.add("hidden");
    document.getElementById("timetable").classList.remove("hidden");
    
    const timetableTable = document.getElementById("timetable-table");
    timetableTable.innerHTML = "";

    let timetable = getTimetable(selectedClass, selectedStream, mode);
    
    for (let row of timetable) {
        let tr = document.createElement("tr");
        for (let cell of row) {
            let td = document.createElement("td");
            td.innerText = cell;
            tr.appendChild(td);
        }
        timetableTable.appendChild(tr);
    }
}

function getTimetable(cls, stream, mode) {
    let defaultTimetable = {
        "1-2": [["Time", "Subject"], ["9:00 AM", "Math"], ["10:00 AM", "English"]],
        "3-4": [["Time", "Subject"], ["9:00 AM", "Science"], ["10:00 AM", "English"]],
        "5-6": [["Time", "Subject"], ["9:00 AM", "Math"], ["10:00 AM", "Science"]],
        "7-8": [["Time", "Subject"], ["9:00 AM", "Math"], ["10:00 AM", "Physics"]],
        "9-10": [["Time", "Subject"], ["9:00 AM", "Math"], ["10:00 AM", "Science"]],
        "11-12": {
            "Science": [["Time", "Subject"], ["9:00 AM", "Physics"], ["10:00 AM", "Chemistry"]],
            "Commerce": [["Time", "Subject"], ["9:00 AM", "Accounts"], ["10:00 AM", "Economics"]],
            "Arts": [["Time", "Subject"], ["9:00 AM", "History"], ["10:00 AM", "Political Science"]]
        }
    };

    let timetable = cls === "11-12" ? defaultTimetable[cls][stream] : defaultTimetable[cls];

    if (mode === "dummy") {
        timetable.push(["1:00 PM", "Self Study"]);
    }

    return timetable;
}

function editTimetable() {
    alert("Feature Coming Soon!");
}