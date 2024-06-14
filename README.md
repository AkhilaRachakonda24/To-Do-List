# To-Do-List
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>To-Do App</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1>To-Do App</h1>
        <div id="inputContainer">
            <input type="text" id="taskInput" placeholder="Add a new task">
            <button onclick="addTask()">Add Task</button>
        </div>
        <div id="pendingTasks">
            <h2>Pending Tasks</h2>
            <ul id="pendingList"></ul>
        </div>
        <div id="completedTasks">
            <h2>Completed Tasks</h2>
            <ul id="completedList"></ul>
        </div>
    </div>

    <script>
        // Function to add a new task
        function addTask() {
            var input = document.getElementById("taskInput");
            var task = input.value;
            if (task.trim() !== "") {
                var listItem = document.createElement("li");
                listItem.innerHTML = task + '<button onclick="completeTask(this)">Complete</button>' +
                    '<button onclick="deleteTask(this)">Delete</button>';
                document.getElementById("pendingList").appendChild(listItem);
                input.value = "";
            }
        }

        // Function to mark a task as complete
        function completeTask(button) {
            var listItem = button.parentNode;
            document.getElementById("completedList").appendChild(listItem);
            button.parentNode.removeChild(button);
        }

        // Function to delete a task
        function deleteTask(button) {
            var listItem = button.parentNode;
            listItem.parentNode.removeChild(listItem);
        }
    </script>
</body>
</html>
