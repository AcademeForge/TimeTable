<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Timetable</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="container">
        <h1>Select Your Class</h1>
        <div class="class-selection">
            <button onclick="selectClass('1-2')">Class 1 & 2</button>
            <button onclick="selectClass('3-4')">Class 3 & 4</button>
            <button onclick="selectClass('5-6')">Class 5 & 6</button>
            <button onclick="selectClass('7-8')">Class 7 & 8</button>
            <button onclick="selectClass('9-10')">Class 9 & 10</button>
            <button onclick="selectClass('11-12')">Class 11 & 12</button>
        </div>

        <div id="stream-selection" class="hidden">
            <h2>Select Stream (Only for Class 11 & 12)</h2>
            <button onclick="selectStream('science')">Science</button>
            <button onclick="selectStream('commerce')">Commerce</button>
            <button onclick="selectStream('arts')">Arts</button>
        </div>

        <div id="timetable-type" class="hidden">
            <h2>Regular or Dummy?</h2>
            <button onclick="generateTimetable('regular')">Regular</button>
            <button onclick="generateTimetable('dummy')">Dummy</button>
        </div>

        <div id="timetable" class="hidden">
            <h2>Your Timetable</h2>
            <p id="schedule"></p>
            <button onclick="modifyTimetable()">Modify Timetable</button>
        </div>
    </div>
<style>
body {
    background-color: #121212;
    color: white;
    font-family: Arial, sans-serif;
    text-align: center;
    margin: 0;
    padding: 20px;
}

button {
    background-color: #1e1e1e;
    color: white;
    border: none;
    padding: 10px 20px;
    margin: 10px;
    cursor: pointer;
    border-radius: 5px;
    transition: 0.3s;
}

button:hover {
    background-color: #333;
}

.container {
    max-width: 400px;
    margin: auto;
}

.hidden {
    display: none;
} 
<style>
    <script src="script.js">let selectedClass = "";
let selectedStream = "";

function selectClass(classGroup) {
    selectedClass = classGroup;
    document.getElementById("stream-selection").classList.add("hidden");
    document.getElementById("timetable-type").classList.remove("hidden");

    if (classGroup === "11-12") {
        document.getElementById("stream-selection").classList.remove("hidden");
        document.getElementById("timetable-type").classList.add("hidden");
    }
}

function selectStream(stream) {
    selectedStream = stream;
    document.getElementById("timetable-type").classList.remove("hidden");
}

function generateTimetable(type) {
    let schedule = "";
    
    if (selectedClass === "1-2") {
        schedule = type === "regular" ? "9 AM - English\n10 AM - Math\n11 AM - Play Time" : "10 AM - Fun Learning\n11 AM - Stories\n12 PM - Drawing";
    } else if (selectedClass === "3-4") {
        schedule = type === "regular" ? "9 AM - English\n10 AM - Math\n11 AM - Science" : "10 AM - Reading\n11 AM - Math Puzzles\n12 PM - Games";
    } else if (selectedClass === "5-6") {
        schedule = type === "regular" ? "9 AM - English\n10 AM - Math\n11 AM - Science\n12 PM - Social Studies" : "10 AM - Self Study\n11 AM - Math Practice\n12 PM - Science Experiments";
    } else if (selectedClass === "7-8") {
        schedule = type === "regular" ? "9 AM - Science\n10 AM - Math\n11 AM - English\n12 PM - Social Studies" : "10 AM - Science Projects\n11 AM - Online Learning\n12 PM - Physical Activities";
    } else if (selectedClass === "9-10") {
        schedule = type === "regular" ? "8 AM - Physics\n9 AM - Math\n10 AM - Chemistry\n11 AM - English" : "9 AM - Online Courses\n10 AM - Exam Prep\n11 AM - Revision";
    } else if (selectedClass === "11-12") {
        if (selectedStream === "science") {
            schedule = type === "regular" ? "8 AM - Physics\n9 AM - Chemistry\n10 AM - Math\n11 AM - English" : "9 AM - JEE Prep\n10 AM - Self Study\n11 AM - Revision";
        } else if (selectedStream === "commerce") {
            schedule = type === "regular" ? "8 AM - Accounts\n9 AM - Business Studies\n10 AM - Economics\n11 AM - English" : "9 AM - Finance Learning\n10 AM - Case Studies\n11 AM - Stock Market Basics";
        } else if (selectedStream === "arts") {
            schedule = type === "regular" ? "8 AM - History\n9 AM - Political Science\n10 AM - Psychology\n11 AM - English" : "9 AM - Literature Studies\n10 AM - Research Work\n11 AM - Writing Practice";
        }
    }

    document.getElementById("schedule").innerText = schedule;
    document.getElementById("timetable").classList.remove("hidden");
}

function modifyTimetable() {
    let newSchedule = prompt("Enter your modified timetable:");
    if (newSchedule) {
        document.getElementById("schedule").innerText = newSchedule;
    }
}
</script>

</body>
</html>