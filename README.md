# TO-DO-LIST

HTML PART 


<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>TO-DO-LIST</title>
    <Link rel="stylesheet" href="STYLE.CSS">

</head>
<body>
    <div class="todo-container">
        <h1>TO-DO LISTS</h1>
        <input type="text" id="todo-input" placeholder="Add a new task...">
        <button id="add-btn">Add task</button>
        <ul id="todo-list"></ul>
    </div>
    <script src="script.js"></script>
</body>
</html>



body {
    font-family: Arial, Helvetica, sans-serif;
    background-color: #f0f0f0;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    margin: 0;
}


.todo-container
{
    background-color: white;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0,0,0,0.2);
    width: 350px;
    text-align: ceneter;

}

h1{
    color:#333;
}
#todo-input {
    width: 80%;
    padding: 10px;
    border-radius: 5px;
    border: 2px solid #ccc;
}

#add-btn {
    padding: 10px;
    border-radius: 5px;
    border: none;
    background-color: #28a745;
    color:white;
    cursor: pointer;
    margin-left: 10px;
}

#add-btn:hover {
    background-color: green;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    background-color: #f9f9f9;
    margin: 10px 0;
    padding: 10px;
    border-radius: 5px;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

button.delete-btn {
    background-color: #dc3545;
    border: none;
    color: white;
    padding: 5px 10px;
    border-radius: 5px;
    cursor: pointer;
}

button.delete-btn:hover {
    background-color: #c82333;
}


JS PART


document.getElementById('add-btn').addEventListener('click',function() {
    const todoInput=document.getElementById('todo-input');
    const todotext = todoInput.value.trim();

    if (todotext !==""){
        const todolist = document .getElementById('todo-list');

        const listitem=document.createElement('li');
      listitem.textcontent = todotext;

      const deletebutton= document.createElement('button');
      deletebutton.textContent='Delete';
      deletebutton.classList.add('delete-btn');

      deletebutton.addEventListener('click',function()
    {
        todolist.removeChild(listitem);
    });

    listitem.appendChild(deletebutton);
    todolist.appendChild(listitem);

    todoInput.value="";

    }



}
);
