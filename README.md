# OCTANET_FEBRUARY-2
The 2nd task given buy OctaNet service PVT LTD.--->>>

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>TO DO LIST</title>
    <style>
        *{
            margin: 0;
            padding: 0;
            font-family:'poppins', sans-serif;
            box-sizing:border-box;
        }
        
       .container{ 
       width: 100%;
       height: 100vh;
           background:linear-gradient(145deg , #b339ad,#aa640d) ;
           padding: 10px;
       }
       .todo{
               width: 100%;
               max-height:540px;
               background:#fff;
               margin: 100px  auto  20px;
               padding: 40px 30px 70px ;
               border-radius: 10px;
             }
             .todo h2{
             
                 color:#002765;
                 display:flex;
                 align-items:center;
                 margin-bottom:20px ;
             }
             .todo h2 img{
             height: 30px;
             margin-left:10px;
                 
             }
             .row{
                 display:flex; 
                 align-item:center;
                 justify-content:                     space-between;
                 background:#edeef0;
                 border-radius: 30px;
                 padding-left:20px;
                 marginbottom: 25px;
             }
             input{
                 flex:1;
                 border:none;
                 outline:none;
                 background: transparent;
                 padding: 10px;
                 
             }
             button{
                 border:none;
                 outline:none;
                 padding: 16px 50px;
                 background: #87CEEB;
                 color:#fff;
                 font-size:16px;
                 cursor: pointer;
                 border-radius:40px;
             }
             ul,li{
                 list-style:none;
                 font-size:19px;
                 padding:12px 8px 12px 50px;
                 user-select:none;
                 cursor:pointer;
                 position:relative;
             }
             ul li :: before {
                 content:'';
                 postion: absolute;
                 height:28px;
                 width: 28px;
                 border-radius:50%;
                 background-image: url('content://com.android.providers.media.documents/document/image%3A1000122338');
                 background-size: cover; 
                 background-posotion:center ;
                   top 12px;
                   left 8px;
            }
            ul li.checked{
                color:#555;
                text-decoration:line-through;
                background-color: rgba(255, 255, 155, 0.25);

            }
            ul li.checked::before{
                             background-image: url('content://com.android.providers.media.documents/document/image%3A1000122338');
            }
            ul li span{
                position: absolute;
                right:0;
                top 5px;
                width:40px;
                height:40px;
                font-size:22px;
                color:#555;
                line-height:40px;
                text-align:center;
                border-radius: 50%;
               }
               ul li span:hover{
                   background:#aaaa;
               }
               footer{
                   text-align:center;
                   background:transparent;
               }
                 
    </style>
</head>
<body>
    <div class="container">
           <div class=" todo ">
              <center> <h2> TO-Do-LIST <img src="https://static.thenounproject.com/png/671961-200.png" alt=""></h2> </center>
               <div class="row">
                   <input type="text" id="input-box" placeholder ="ADD YOUR TEXT">
                   <button onclick="addTask()"> ADD</button>
               </div>
               <ul id="list-dabba">
                 <!--   <li class="checked">
                        TASK 1</li>
                   <li> TASK 2</li>
                   <li> TASK 3</li> -->
                   
               </ul>
           </div>
    </div>
    <script>
        const inputBox = document.getElementById("input-box");
const listDabba = document.getElementById("list-dabba");

function addTask() {
    if (inputBox.value === '') {
        alert("You must write something");
    } else {
        let li = document.createElement("li");
        li.innerHTML = inputBox.value;
        listDabba.appendChild(li);
        let span = document.createElement("span");
        span.innerHTML = "\u00d7";
        li.appendChild(span);
    }
    inputBox.value = "";
    saveData();
}
listDabba.addEventListener("click", function(e) {
    if (e.target.tagName === "LI") {
        e.target.classList.toggle("checked");
        saveData();
    } else if (e.target.tagName === "SPAN") {
        e.target.parentElement.remove();
        saveData();
    }
}, false);
function saveData() {
    localStorage.setItem("data",listDabba.innerHTML)
}
function showTask() {
    listDabba.innerHTML = localStorage.getItem("data");
}
 showTask();



    </script>
    <footer>
        <h1> made by @rushikesh Dhenge</h1>
    </footer>
      
</body>
</html>

