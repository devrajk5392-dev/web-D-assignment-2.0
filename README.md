
<!DOCTYPE html>
<html>
<head>
    <title>Course Selection Form</title>

    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #eaf2f8;
            margin: 0;
            padding: 20px;
        }

        .container {
            background-color: white;
            width: 90%;
            max-width: 400px;
            margin: 40px auto;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 0 10px gray;
        }

        h2 {
            text-align: center;
            color: #154360;
        }

        input[type="text"] {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
            box-sizing: border-box;
        }

        .courses {
            margin: 15px 0;
        }

        button {
            width: 100%;
            padding: 12px;
            background-color: #2874a6;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #154360;
        }

        #result {
            margin-top: 20px;
            color: green;
        }

        @media (max-width: 600px) {
            .container {
                width: 90%;
                padding: 15px;
            }
        }
    </style>
</head>

<body>

<div class="container">

    <h2>Course Selection Form</h2>

    <form id="myForm">

        <label>Student Name:</label>
        <input type="text" id="name" placeholder="Enter your name" required>

        <label>Roll Number:</label>
        <input type="text" id="roll" placeholder="Enter roll number" required>

        <h3>Select Your Courses:</h3>

        <div class="courses">
            <input type="checkbox" name="course" value="HTML"> HTML <br>
            <input type="checkbox" name="course" value="CSS"> CSS <br>
            <input type="checkbox" name="course" value="JavaScript"> JavaScript <br>
            <input type="checkbox" name="course" value="Python"> Python
        </div>

        <button type="submit">Submit</button>

    </form>

    <div id="result"></div>

</div>

<script>

    document.getElementById("myForm").onsubmit = function(event) {

        event.preventDefault();

        let name = document.getElementById("name").value;
        let roll = document.getElementById("roll").value;

        let selected = document.querySelectorAll(
            'input[name="course"]:checked'
        );

        if (selected.length === 0) {
            alert("Please select at least one course!");
            return;
        }

        let courses = [];

        selected.forEach(function(item) {
            courses.push(item.value);
        });

        document.getElementById("result").innerHTML =
            "<h3>Registration Successful!</h3>" +
            "Student Name: " + name + "<br>" +
            "Roll Number: " + roll + "<br>" +
            "Selected Courses: " + courses.join(", ");

    };

</script>

</body>
</html>
