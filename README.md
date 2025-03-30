# TODO
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple To-Do List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #1a1a2e;
            flex-direction: column;
            color: #ffffff;
        }
        #todo-container {
            background: #0f3460;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 255, 255, 0.6);
            width: 300px;
            text-align: center;
        }
        input {
            width: 70%;
            padding: 8px;
            background: #16213e;
            color: #00ffff;
            border: 1px solid #00ffff;
            border-radius: 5px;
        }
        button {
            padding: 8px;
            margin-left: 5px;
            cursor: pointer;
            background: #e94560;
            color: white;
            border: none;
            border-radius: 5px;
            font-weight: bold;
        }
        ul {
            list-style-type: none;
            padding: 0;
        }
        li {
            display: flex;
            justify-content: space-between;
            background: #16213e;
            margin-top: 5px;
            padding: 5px;
            border-radius: 5px;
            color: #00ffff;
            border: 1px solid #00ffff;
        }
        .delete {
            background: #e94560;
            color: white;
            border: none;
            padding: 5px;
            cursor: pointer;
            border-radius: 5px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div id="todo-container">
        <h2>To-Do List</h2>
        <input type="text" id="taskInput" placeholder="Add a new task">
        <button onclick="addTask()">Add</button>
        <ul id="taskList"></ul>
    </div>

    <script>
        function addTask() {
            let taskInput = document.getElementById("taskInput");
            let taskText = taskInput.value.trim();
            if (taskText === "") return;

            let li = document.createElement("li");
            li.innerHTML = `${taskText} <button class='delete' onclick='removeTask(this)'>X</button>`;
            document.getElementById("taskList").appendChild(li);

            taskInput.value = "";
        }
        
        function removeTask(button) {
            button.parentElement.remove();
        }
    </script>
</body>
</html>
