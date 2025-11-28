<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>2-Step Registration Form</title>

</head>

<body>
<div class="container">

    
    <div id="step1" class="step">
        <h2>Step 1</h2>
        <label>Name:</label><br>
        <input type="text" id="name" style="width: 100%"><br><br>

        <label>Email:</label><br>
        <input type="email" id="email" style="width: 100%"><br>

        <div class="btn-group">
            <span></span>
            <button onclick="nextStep()">Next ➜</button>
        </div>
    </div>

    <!-- Step 2 -->
    <div id="step2" class="step">
        <h2>Step 2 — Summary</h2>
        <p><strong>Name:</strong> <span id="summaryName"></span></p>
        <p><strong>Email:</strong> <span id="summaryEmail"></span></p>

        <div class="btn-group">
            <button onclick="prevStep()">⬅ Back</button>
            <button onclick="alert('Form Submitted!')">Submit</button>
        </div>
    </div>

</div>

<script>
    const step1 = document.getElementById("step1");
    const step2 = document.getElementById("step2");

    // Show Step 1 initially
    step1.style.display = "block";

    function nextStep() {
        const name = document.getElementById("name").value;
        const email = document.getElementById("email").value;

        if (!name || !email) {
            alert("Please enter both name and email.");
            return;
        }

        document.getElementById("summaryName").textContent = name;
        document.getElementById("summaryEmail").textContent = email;

        step1.style.display = "none";
        step2.style.display = "block";
    }

    function prevStep() {
        step2.style.display = "none";
        step1.style.display = "block";
    }
</script>

</body>
</html>
