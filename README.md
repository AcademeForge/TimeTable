# TimeTable

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Timetable | AcademeForge</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>Select Your Class</h1>
        <div class="class-buttons">
            <button onclick="selectClass(1)">Class 1 & 2</button>
            <button onclick="selectClass(3)">Class 3 & 4</button>
            <button onclick="selectClass(5)">Class 5 & 6</button>
            <button onclick="selectClass(7)">Class 7 & 8</button>
            <button onclick="selectClass(9)">Class 9 & 10</button>
            <button onclick="selectClass(11)">Class 11 & 12</button>
        </div>
    </div>

    <script>
        function selectClass(classGroup) {
            if (classGroup === 11) {
                window.location.href = "stream.html";
            } else {
                window.location.href = `timetable.html?class=${classGroup}`;
            }
        }
    </script>


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Select Stream | AcademeForge</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>Select Your Stream</h1>
        <div class="class-buttons">
            <button onclick="selectStream('Science')">Science</button>
            <button onclick="selectStream('Commerce')">Commerce</button>
            <button onclick="selectStream('Arts')">Arts</button>
        </div>
    </div>

    <script>
        function selectStream(stream) {
            window.location.href = `timetable.html?class=11&stream=${stream}`;
        }
    </script>


<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Timetable | AcademeForge</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h1>Select Timetable Type</h1>
        <div class="class-buttons">
            <button onclick="loadTimetable('Regular')">Regular</button>
            <button onclick="loadTimetable('Dummy')">Dummy</button>
        </div>

        <div id="timetable-container" class="hidden">
            <h2>Your Timetable</h2>
            <table>
                <tr>
                    <th>Time</th>
                    <th>Subject</th>
                    <th>Actions</th>
                </tr>
                <tbody id="timetable-body"></tbody>
            </table>
            <button onclick="saveTimetable()">Save Changes</button>
        </div>
    </div>

    <script>
        function loadTimetable(type) {
            document.getElementById("timetable-container").classList.remove("hidden");

            let timetable = {
                "Regular": [
                    { time: "6:00 AM - 7:00 AM", subject: "Wake Up & Exercise" },
                    { time: "7:00 AM - 8:00 AM", subject: "Math" },
                    { time: "8:00 AM - 9:00 AM", subject: "Science" },
                    { time: "9:00 AM - 10:00 AM", subject: "Break / School" }
                ],
                "Dummy": [
                    { time: "6:00 AM - 7:00 AM", subject: "Wake Up & Study" },
                    { time: "7:00 AM - 8:00 AM", subject: "Self Study - Math" },
                    { time: "8:00 AM - 9:00 AM", subject: "Self Study - Science" },
                    { time: "9:00 AM - 10:00 AM", subject: "Revision" }
                ]
            };

            let tbody = document.getElementById("timetable-body");
            tbody.innerHTML = "";

            timetable[type].forEach((slot, index) => {
                let row = `<tr>
                    <td>${slot.time}</td>
                    <td contenteditable="true">${slot.subject}</td>
                    <td><button onclick="setReminder('${slot.subject}')">Set Reminder</button></td>
                </tr>`;
                tbody.innerHTML += row;
            });
        }

        function saveTimetable() {
            alert("Timetable saved successfully!");
        }

        function setReminder(subject) {
            alert(`Reminder set for ${subject}!`);
        }
    </script>

body {
    font-family: Arial, sans-serif;
    background-color: #121212;
    color: white;
    text-align: center;
    margin: 0;
    padding: 0;
}

.container {
    margin-top: 50px;
    padding: 20px;
}

h1, h2 {
    color: #00FF7F;
    text-shadow: 2px 2px 5px #000;
}

.class-buttons {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 15px;
}

button {
    background-color: #1DB954;
    border: none;
    color: white;
    padding: 15px;
    width: 80%;
    font-size: 18px;
    border-radius: 10px;
    box-shadow: 3px 3px 8px rgba(0, 255, 127, 0.2);
    cursor: pointer;
}

button:hover {
    background-color: #1AA34A;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;
}

th, td {
    padding: 15px;
    border-bottom: 1px solid white;
}

.hidden {
    display: none;
}
</script>

</body>
</html>