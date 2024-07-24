This project is all about heart disease.
It tells us about the chances that a person is having any heart related problem.
Some input needs to be given to it reoated to the person and it tells the output as the risk.
CODE
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Heart Disease Diagnostic Tool</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 20px;
    }
    label {
        font-weight: bold;
    }
</style>
</head>
<body>
    <h2>Heart Disease Diagnostic Tool</h2>
    <form id="heartDiseaseForm">
        <label for="age">Age:</label>
        <input type="number" id="age" name="age" required><br><br>
        
        <label for="gender">Gender:</label>
        <select id="gender" name="gender" required>
            <option value="">Select</option>
            <option value="male">Male</option>
            <option value="female">Female</option>
        </select><br><br>
        
        <label for="chestPain">Chest Pain Type:</label>
        <select id="chestPain" name="chestPain" required>
            <option value="">Select</option>
            <option value="typical">Typical Angina</option>
            <option value="atypical">Atypical Angina</option>
            <option value="non-anginal">Non-Anginal Pain</option>
            <option value="asymptomatic">Asymptomatic</option>
        </select><br><br>
        
        <label for="bloodPressure">Resting Blood Pressure (mm Hg):</label>
        <input type="number" id="bloodPressure" name="bloodPressure" required><br><br>
        
        <label for="cholesterol">Serum Cholesterol (mg/dl):</label>
        <input type="number" id="cholesterol" name="cholesterol" required><br><br>
        
        <label for="submit"></label>
        <button type="button" onclick="diagnose()">Diagnose</button>
    </form>

    <div id="diagnosisResult"></div>

    <script>
        function diagnose() {
            // Retrieve form values
            var age = document.getElementById('age').value;
            var gender = document.getElementById('gender').value;
            var chestPain = document.getElementById('chestPain').value;
            var bloodPressure = document.getElementById('bloodPressure').value;
            var cholesterol = document.getElementById('cholesterol').value;

            // Perform basic validation (you can add more complex validation as needed)

            // Example: Check if age is a number and within a reasonable range
            if (isNaN(age) || age < 0 || age > 150) {
                alert('Please enter a valid age.');
                return;
            }

            // Example: Check if blood pressure and cholesterol are numbers
            if (isNaN(bloodPressure) || isNaN(cholesterol)) {
                alert('Please enter valid numbers for blood pressure and cholesterol.');
                return;
            }

            // Example: Perform a simple diagnosis based on inputs
            var diagnosis = "Based on your inputs, ";

            // Example logic (you would need medical expertise to fill this out properly)
            if (age > 50 && gender === 'male' && chestPain === 'typical' && bloodPressure > 140 && cholesterol > 200) {
                diagnosis += "you are at a higher risk of heart disease.";
            } else {
                diagnosis += "you are at a lower risk of heart disease.";
            }

            // Display the result
            var resultDiv = document.getElementById('diagnosisResult');
            resultDiv.innerHTML = '<p>' + diagnosis + '</p>';
        }
    </script>
</body>
</html>
