<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GymFolio - Fitness Tracker</title>
    <link rel="stylesheet" href="Back.css">
   <link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap">
    <style>
        :root {
            --primary: #4361ee;
            --accent: #f72585;
            --dark: #212529;
            --light: #f8f9fa;
        }
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Poppins', sans-serif;
        }
  body {
    margin:0;
    padding:10px;
    min-height: 100vh;
    display:flex;
    justify-content: center;
    background-image:url('back.jpg');
    background-repeat:no-repeat;
    background-position:center center;
    background-attachment:fixed;
    background-size:cover;
    align-items: center;
    font-family:Arial, sans-serif;
        }
        .frame {
            background: white;
            border-radius: 20px;
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.1);
            padding: 40px;
            width: 100%;
            max-width: 700px;
            text-align: center;
        }
        h1 {
            color: var(--primary);
            font-size: 2.5rem;
        }
        p {
            color: var(--dark);
            font-size: 1.2rem;
            margin-bottom: 15px;
        }
        .form-group {
            margin: 15px 0;
            text-align: left;
        }
        label {
            display: block;
            font-weight: 600;
            margin-bottom: 5px;
            color: var(--dark);
        }
        input, select {
            width: 100%;
            padding: 12px;
            border-radius: 8px;
            border: 2px solid #ddd;
            font-size: 1rem;
        }
        input:focus, select:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 5px rgba(67, 97, 238, 0.3);
        }
        button {
            margin-top: 20px;
            padding: 12px;
            background: linear-gradient(135deg, var(--accent), var(--primary));
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 1.1rem;
            cursor: pointer;
            width: 100%;
        }
        .dashboard {
            margin-top: 20px;
            display: grid;
            grid-template-columns: 1fr;
            gap: 15px;
        }
        .dashboard button {
            background: var(--primary);
            padding: 15px;
            border: none;
            color: white;
            border-radius: 10px;
            font-size: 1.2rem;
            cursor: pointer;
            transition: all 0.3s;
        }
        .dashboard button:hover {
            background: var(--accent);
        }
    </style>
</head>
<body style="margin:0; padding:0; background: url('back.jpg') no-repeat center center fixed; background-size: cover;">
    <div class="frame" id="mainFrame">
        <!-- First Interface -->
        <header>
            <h1>GymFolio</h1>
            <p>Track Your Fitness Journey</p>
        </header>

        <form id="nameForm">
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" placeholder="Enter your name" required>
            </div>

            <div class="form-group">
                <label for="age">Age</label>
                <input type="number" id="age" placeholder="Enter your age" step="1" min="15" max="40" required>
            </div>

            <div class="form-group">
                <label for="gender">Gender</label>
                <select id="gender" required>
                    <option value="" disabled selected>Select your gender</option>
                    <option value="Male">Male</option>
                    <option value="Female">Female</option>
                    <option value="Other">Other</option>
                </select>
            </div>

            <button type="button" onclick="goToDetails()">Add Details</button>
        </form>
    </div>

    <script>
        // Transition to the second interface
        function goToDetails() {
            const name = document.getElementById("name").value.trim();
            const age = document.getElementById("age").value.trim();
            const gender = document.getElementById("gender").value;

            if (!name || !age || !gender) {
                alert("Please fill out all fields!");
                return;
            }

            const mainFrame = document.getElementById("mainFrame");
            mainFrame.innerHTML = `
                <header>
                    <h1>GymFolio</h1>
                    <p>Hello, ${name}! Welcome to GymFolio!!</p>
                </header>

                <form id="detailsForm">
                    <div class="form-group">
                        <label for="weight">Weight (kg)</label>
                        <input type="number" id="weight" placeholder="Enter your weight" required>
                    </div>

                    <div class="form-group">
                        <label for="bp">Blood Pressure</label>
                        <select id="bp" required>
                            <option value="" disabled selected>Select your BP level</option>
                            <option value="High">High</option>
                            <option value="Moderate">Moderate</option>
                            <option value="Low">Low</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="sugar">Sugar Level</label>
                        <select id="sugar" required>
                            <option value="" disabled selected>Select your sugar level</option>
                            <option value="High">High</option>
                            <option value="Moderate">Moderate</option>
                            <option value="Low">Low</option>
                        </select>
                    </div>

                    <div class="form-group">
                        <label for="steps">Daily Steps</label>
                        <input type="number" id="steps" placeholder="Enter your daily steps" min="100" max="100000" required>
                    </div>
                    <button type="button" onclick="goToDashboard()">Submit</button>
                    <button 
                    width=100px heigth=50px type="button" onclick="goToFirst()" style="margin-top:10px; background-color:#e0e0e0; color:#000;">←Back</button>
               </form>
            `;
        }
        function goToFirst() {
    const mainFrame = document.getElementById("mainFrame");
    mainFrame.innerHTML = `
        <header>
            <h1>GymFolio</h1>
            <p>Track Your Fitness Journey</p>
        </header>

        <form id="nameForm">
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" placeholder="Enter your name" required>
            </div>

            <div class="form-group">
                <label for="age">Age</label>
                <input type="number" id="age" placeholder="Enter your age" step="1" min="15" max="40" required>
            </div>

            <div class="form-group">
                <label for="gender">Gender</label>
                <select id="gender" required>
                    <option value="" disabled selected>Select your gender</option>
                    <option value="Male">Male</option>
                    <option value="Female">Female</option>
                    <option value="Other">Other</option>
                </select>
            </div>

            <button type="button" onclick="goToDetails()">Add Details</button>
        </form>
    `;
}
        // Transition to the third interface
        function goToDashboard() {
            const weight = document.getElementById("weight").value.trim();
            const bp = document.getElementById("bp").value;
            const sugar = document.getElementById("sugar").value;
            const steps = document.getElementById("steps").value.trim();

            if (!weight || !bp || !sugar || !steps) {
                alert("Please fill out all fields!");
                return;
            }
            const mainFrame = document.getElementById("mainFrame");
            mainFrame.innerHTML = `
                <header>
                    <h1>GymFolio</h1>
                    <p>Your personalized fitness dashboard</p>
                </header>
                
                <div class="dashboard"">
                    <button onclick="logWorkout()" class="square-btn">🏋️‍♂️Log Workout</button>
                    <button onclick="dietPlan()" class="square-btn">🥗Diet Plan</button>
                    <button onclick="setGoals()" class="square-btn">🎯Set Goals</button>
                    <button onclick="goToFirst()" style="
                            width: 100px;
                            height: 50px;
                            font-size: 1rem;
                            background-color:#e0e0e0;
                            color: #000;
                            border: none;
                            border-radius: 10px;
                            cursor: pointer
                    ">←Back</button>
                </div>     
            `;
            // Example functions for dashboard buttons
            window.logWorkout = function () {
    const mainFrame = document.getElementById("mainFrame");
    mainFrame.innerHTML = `
        <header>
            <h1>Log Workout</h1>
            <p>Track your daily exercises</p>
        </header>

        <div id="exerciseList" style="
            display: flex;
            flex-wrap: wrap;
            gap: 15px;
            padding: 10px 0;
            max-height: 500px;
            overflow-y: auto;
        ">
        </div> <center>
        <button onclick="goToFirst()" style="
           width: 100px;
           height: 50px;
           font-size: 1rem;
           background-color:#e0e0e0;
           color: #000;
           border: none;
           border-radius: 10px;
           cursor: pointer
        ">←Back</button>
         </center>
        <canvas id="repsChart" style="margin-top: 30px;">
        </canvas>
    `;
    const exercises = [
        { name: 'Chest Press', icon: '💪' },
        { name: 'Crunches', icon: '🌀' },
        { name: 'Push-ups', icon: '🤸' },
        { name: 'Pull-ups', icon: '🏋️' },
        { name: 'Squats', icon: '🦵' },
        { name: 'Lunges', icon: '🚶' },
        { name: 'Bicep Curls', icon: '💪🏻' },
        { name: 'Deadlift', icon: '🏋️‍♂️' },
        { name: 'Bench Press', icon: '🏋️‍♀️' },
        { name: 'Plank', icon: '🧘' },
        { name: 'Jumping Jacks', icon: '🤾' },
        { name: 'Running', icon: '🏃' },
        { name: 'Cycling', icon: '🚴' },
        { name: 'Yoga', icon: '🧘‍♀️' },
        { name: 'Stretching', icon: '🤸‍♂️' },
    ];

    const listDiv = document.getElementById("exerciseList");
    exercises.forEach(ex => {
        const card = document.createElement("div");
        card.style.border = "2px solid #ddd";
        card.style.borderRadius = "10px";
        card.style.padding = "15px";
        card.style.textAlign = "center";
        card.style.width = "48%";
        card.style.boxSizing = "border-box";
        card.innerHTML = `
           <div style="font-size: 2rem;" title="${ex.name}">${ex.icon}</div>
           <p>${ex.name}</p>
        `;
        listDiv.appendChild(card);
    });
    const ctx = document.getElementById("repsChart").getContext("2d");
};
    window.dietPlan = function () {
        const mainFrame = document.getElementById("mainFrame");
        const days = ['Monday','Tuesday','Wednesday','Thursday','Friday','Saturday','Sunday'];
            mainFrame.innerHTML = `
    <header>
        <h1>Weekly Diet Plan</h1>
        <p>Select a day to view your diet chart</p>
    </header>
    <div style="
        display: flex;
        flex-direction: column;
        gap: 15px;
        max-height: 400px;
        overflow-y: auto;
        margin: 20px 0;
        padding-right: 10px;
    ">
        ${(() => {
            let rows = '';
            for (let i = 0; i < days.length; i += 2) {
                const day1 = days[i];
                const day2 = days[i + 1];
                rows += `
                    <div style="display: flex; justify-content: center; gap: 15px;">
                        <button onclick="showDietChart('${day1}')" style="
                            width: 150px;
                            height: 150px;
                            font-size: 1rem;
                            background: var(--primary);
                            color: white;
                            border: none;
                            border-radius: 10px;
                            cursor: pointer;
                        ">${day1}</button>
                        ${day2 ? `
                            <button onclick="showDietChart('${day2}')" style="
                                width: 150px;
                                height: 150px;
                                font-size: 1rem;
                                background: var(--primary);
                                color: white;
                                border: none;
                                border-radius: 10px;
                                cursor: pointer;
                            ">${day2}</button>
                        ` : ''}
                    </div>
                `;
            }
            return rows;
        })()}
    </div>
    <center>
    <button onclick="goToFirst()" style="
           width: 100px;
           height: 50px;
           font-size: 1rem;
           background-color:#e0e0e0;
           color: #000;
           border: none;
           border-radius: 10px;
           cursor: pointer
    ">←Back</button>
    </center>
`;
};

window.showDietChart = function(day) {
    const mainFrame = document.getElementById("mainFrame");

    const diets = {
        Monday: ['🍳 Breakfast: Oatmeal & Fruits', '🥗 Lunch: Grilled Chicken Salad', '🍎 Snack: Apple & Nuts', '🍲 Dinner: Lentil Soup'],
        Tuesday: ['🍞 Breakfast: Whole Grain Toast & Eggs', '🥘 Lunch: Brown Rice & Veggies', '🥒 Snack: Cucumber Sticks & Hummus', '🍛 Dinner: Grilled Fish & Steamed Veggies'],
        Wednesday: ['🥣 Breakfast: Smoothie Bowl', '🥪 Lunch: Turkey Sandwich', '🍌 Snack: Banana', '🍝 Dinner: Pasta with Tomato Sauce'],
        Thursday: ['🍓 Breakfast: Yogurt & Berries', '🥙 Lunch: Falafel Wrap', '🥜 Snack: Mixed Nuts', '🥘 Dinner: Chicken Stir Fry'],
        Friday: ['🍳 Breakfast: Scrambled Eggs & Avocado', '🍚 Lunch: Quinoa & Beans', '🍍 Snack: Pineapple Chunks', '🍲 Dinner: Veggie Soup & Bread'],
        Saturday: ['🥞 Breakfast: Pancakes & Honey', '🍝 Lunch: Spaghetti & Meatballs', '🍊 Snack: Orange Slices', '🍔 Dinner: Grilled Burger & Salad'],
        Sunday: ['🍩 Breakfast: Bagel & Cream Cheese', '🥗 Lunch: Caesar Salad', '🍇 Snack: Grapes', '🍕 Dinner: Veggie Pizza'],
    };

    mainFrame.innerHTML = `
        <div style="
            max-width: 900px;
            margin: 10px auto;
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
            position: relative;
        ">
            <header style="text-align: center;">
                <h1 style="color: #2d5eff; margin-bottom: 10px;">${day}'s Diet Plan</h1>
                <p style="font-size: 1.1rem; color: #444;">Here's what to eat for optimal health today</p>
            </header>

            <ul style="text-align: left; margin-top: 30px; line-height: 2; font-size: 1rem;">
                ${diets[day].map(item => `<li>${item}</li>`).join('')}
            </ul>

            <button onclick="window.dietPlan()" 
             width: 80px;
           height: 30px;
           font-size: 1rem;
           background-color:#e0e0e0;
           color: #000;
           border: none;
           border-radius: 10px;
           cursor: pointer
            ">← Back</button>

        </div>
    `;
 };
 window.setGoals = function () {
    const mainFrame = document.getElementById("mainFrame");
    mainFrame.innerHTML = `
        <header>
            <h1>Set Your Fitness Goals</h1>
            <p>Define what you aim to achieve</p>
        </header>

        <form id="goalForm" style="text-align: left; margin-top: 20px;">
            <div class="form-group">
                <label for="goalWeight">Target Weight (kg)</label>
                <input type="number" id="goalWeight" placeholder="e.g., 70" required>
            </div>

            <div class="form-group">
                <label for="dailySteps">Daily Steps Goal</label>
                <input type="number" id="dailySteps" placeholder="e.g., 10000" required>
            </div>

            <div class="form-group">
                <label for="workoutsPerWeek">Workouts per Week</label>
                <input type="number" id="workoutsPerWeek" placeholder="e.g., 4" required>
            </div>

            <button type="button" onclick="saveGoals()">Save Goals</button>
        </form>

        <center>
            <button onclick="goToFirst()" style="
                width: 100px;
                height: 50px;
                font-size: 1rem;
                background-color:#e0e0e0;
                color: #000;
                border: none;
                border-radius: 10px;
                cursor: pointer;
                margin-top: 20px;
            ">←Back</button>
        </center>
    `;
};

function saveGoals() {
    const goalWeight = document.getElementById("goalWeight").value;
    const dailySteps = document.getElementById("dailySteps").value;
    const workoutsPerWeek = document.getElementById("workoutsPerWeek").value;

    if (!goalWeight || !dailySteps || !workoutsPerWeek) {
        alert("Please fill out all goal fields!");
        return;
    }

    alert(`${userName}, your goal is saved! 🎯
- Target Weight: ${goalWeight} kg
- Daily Steps: ${dailySteps}
- Workouts/Week: ${workoutsPerWeek}`);
    goToDashboard(); // optional auto-return
}

        }
    </script>
</body>
</html>
