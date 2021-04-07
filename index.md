<!DOCTYPE html>
<html>
 <head>
 <title>To-Do List App</title>
 <script>
  function addItem() {
   var newItem = document.createElement("div");
   newItem.innerHTML = document.getElementById("box").value;
   newItem.onclick = removeItem;
   document.getElementById("list").appendChild(newItem);
   saveList();
  }
  function removeItem() {
   document.getElementById("list").removeChild(this);
   saveList();
  }
  function saveList() {
   localStorage.storedList = document.getElementById("list").innerHTML;
  }
  function loadList() {
   document.getElementById("list").innerHTML = localStorage.storedList;
   for(var i = 0; i < list.children.length; i++) {
    list.children[i].onclick = removeItem;
   }
  }
 </script>
 <style>
  .header {
    height:113px; 
    width: 602px; 
    background-color:red; 
    float: center; 
    padding:10px; 
    margin:20px;
    text-align:centre; 
    font-size:24px;
  }
  .app {
    height:10000000000000000000000000000000000000000000000000000px;
    width: 600px; 
    background-color:rgb(3, 255, 255); 
    float: center; 
    padding:10px; 
    margin:20px;
  }
  input[type="button"] {
   background-color: red;
  }
 </style>
</head>
<body>
 <div class="header">
  <img src="https://cdn.kastatic.org/third_party/javascript-khansrc/live-editor/build/images/avatars/avatar-team.png" style="float: left;"> 
  <p>Mason's to-do list app</p>
 </div>
 <div class="app">
  <p style="font-size:18px; font-style:bold;">To-Do List App</p>
  <input type="text" id="box" value=""/>
  <br/>
  <input type="button" value="Add item" onclick="addItem();"/>
  <br/>
   <div id="list"></div>
 </div>
 <script>
  if(localStorage.storedList) {
   loadList();
  }
 </script>
</body>
</html>
