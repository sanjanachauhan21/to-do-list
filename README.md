# to-do-list
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>To-Do List</title>
<style>
    body {
        font-family: Arial, sans-serif;
    }
    .container {
        max-width: 400px;
        margin: 0 auto;
        padding: 20px;
        border: 1px solid #ccc;
        border-radius: 5px;
    }
    input[type="text"] {
        width: 100%;
        padding: 10px;
        margin-bottom: 10px;
        border: 1px solid #ccc;
        border-radius: 5px;
    }
    button {
        padding: 10px 20px;
        background-color: #4CAF50;
        color: white;
        border: none;
        border-radius: 5px;
        cursor: pointer;
    }
    button:hover {
        background-color: #45a049;
    }
    ul {
        list-style-type: none;
        padding: 0;
    }
    li {
        margin-bottom: 5px;
    }
    .delete {
        background-color: #f44336;
    }
</style>
</head>
<body>

<div class="container">
    <h2>To-Do List</h2>
    <input type="text" id="taskInput" placeholder="Enter task">
    <button onclick="addTask()">Add Task</button>
    <ul id="taskList"></ul>
</div>

<script>
    function addTask() {
        var input = document.getElementById("taskInput");
        var task = input.value.trim();
        if (task !== "") {
            var ul = document.getElementById("taskList");
            var li = document.createElement("li");
            li.textContent = task;
            var deleteButton = document.createElement("button");
            deleteButton.textContent = "Delete";
            deleteButton.className = "delete";
            deleteButton.onclick = function() {
                ul.removeChild(li);
            };
            li.appendChild(deleteButton);
            ul.appendChild(li);
            input.value = "";
        } else {
            alert("Please enter a task.");
        }
    }
</script>

</body>
</html>
