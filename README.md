<!DOCTYPE html>
<html>
<head>
    <title>Simple To-Do List App</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
        }

        h1 {
            color: #3498db;
        }

        #app {
            width: 300px;
            margin: 20px auto;
            text-align: left;
        }

        ul {
            list-style: none;
            padding: 0;
        }

        li {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border: 1px solid #f0f0f0;
            padding: 5px 10px;
            margin: 5px 0;
        }
    </style>
</head>
<body>
    <h1>Simple To-Do List App</h1>
    <div id="app">
        <input type="text" id="task" placeholder="Enter a task">
        <button onclick="addTask()">Add Task</button>
        <ul id="task-list"></ul>
    </div>

    <script>
        function addTask() {
            const taskInput = document.getElementById('task');
            const taskText = taskInput.value.trim();
            if (taskText === '') return;

            const taskList = document.getElementById('task-list');
            const listItem = document.createElement('li');
            listItem.innerHTML = `<span>${taskText}</span><button onclick="removeTask(this)">Remove</button>`;
            taskList.appendChild(listItem);

            taskInput.value = '';
        }

        function removeTask(button) {
            const taskList = document.getElementById('task-list');
            const listItem = button.parentNode;
            taskList.removeChild(listItem);
        }
    </script>
</body>
</html>
