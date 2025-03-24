
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Study Planner</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>Study Planner</h1>
        <form>
            <div class="class-selection">
                <label for="class">Select Class:</label>
                <select id="class" name="class">
                    <option value="class1-2">Class 1-2</option>
                    <option value="class3-4">Class 3-4</option>
                    <option value="class5-6">Class 5-6</option>
                    <option value="class7-8">Class 7-8</option>
                    <option value="class9-10">Class 9-10</option>
                    <option value="class11-12">Class 11-12</option>
                </select>
            </div>
            <div class="stream-selection" style="display:none;">
                <label for="stream">Select Stream:</label>
                <select id="stream" name="stream">
                    <option value="science">Science</option>
                    <option value="commerce">Commerce</option>
                    <option value="arts">Arts</option>
                </select>
            </div>
            <div class="dummy-regular-selection">
                <label for="dummy-regular">Select Type:</label>
                <select id="dummy-regular" name="dummy-regular">
                    <option value="dummy">Dummy</option>
                    <option value="regular">Regular</option>
                </select>
            </div>
            <button id="submit-btn">Submit</button>
        </form>
        <div class="timetable-container" style="display:none;">
            <h2>Timetable</h2>
            <table id="timetable">
                <thead>
                    <tr>
                        <th>Day</th>
                        <th>Time</th>
                        <th>Subject</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <td>Monday</td>
                        <td>9:00 AM - 10:00 AM</td>
                        <td>Mathematics</td>
                    </tr>
                    <tr>
                        <td>Monday</td>
                        <td>10:00 AM - 11:00 AM</td>
                        <td>Science</td>
                    </tr>
                    <tr>
                        <td>Monday</td>
                        <td>11:00 AM - 12:00 PM</td>
                        <td>English</td>
                    </tr>
                    <tr>
                        <td>Tuesday</td>
                        <td>9:00 AM - 10:00 AM</td>
                        <td>Social Studies</td>
                    </tr>
                    <tr>
                        <td>Tuesday</td>
                        <td>10:00 AM - 11:00 AM</td>
                        <td>Hindi</td>
                    </tr>
                    <tr>
                        <td>Wednesday</td>
                        <td>9:00 AM - 10:00 AM</td>
                        <td>Computer Science</td>
                    </tr>
                    <tr>
                        <td>Wednesday</td>
                        <td>10:00 AM - 11:00 AM</td>
                        <td>Physical Education</td>
                    </tr>
                    <tr>
                        <td>Thursday</td>
                        <td>9:00 AM - 10:00 AM</td>
                        <td>Mathematics</td>
                    </tr>
                    <tr>
                        <td>Thursday</td>
                        <td>10:00 AM - 11:00 AM</td>
                        <td>Science</td>
                    </tr>
                    <tr>
                        <td>Friday</td>
                        <td>9:00 AM - 10:00 AM</td>
                        <td>English</td>
                    </tr>
                    <tr>
                        <td>Saturday</td>
                        <td>9:00 AM - 10:00 AM</td>
                        <td>Social Studies</td>
                    </tr>
                </tbody>
            </table>
            <button id="modify-timetable-btn">Modify Timetable</button>
            <button id="set-reminder-btn">Set Reminder</button>
        </div>
    </div>
    <script src="script.js"></script>
</body>
</html>
