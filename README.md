<!DOCTYPE html>
<html lang="en">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">

<title>AI Chat Premium Game</title>

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial,sans-serif;
}


body{

    background:
    linear-gradient(-45deg,
    #020617,
    #1e3a8a,
    #0891b2,
    #0f172a);

    background-size:400% 400%;
    animation:bg 15s infinite;

    color:white;
}


@keyframes bg{

0%{
background-position:0% 50%;
}

50%{
background-position:100% 50%;
}

100%{
background-position:0% 50%;
}

}


/* LOGIN */

#loginPage{

height:100vh;
display:flex;
justify-content:center;
align-items:center;

}


.login-box{

background:rgba(255,255,255,.15);
backdrop-filter:blur(15px);

padding:30px;
border-radius:20px;

text-align:center;

}


.login-box input{

padding:12px;
width:250px;

}


button{

padding:10px;
border:none;
border-radius:8px;

cursor:pointer;

}


/* MAIN */

#app{

display:none;

}


/* SIDEBAR */


.sidebar{

position:fixed;

width:250px;
height:100vh;

background:
rgba(255,255,255,.12);

backdrop-filter:blur(15px);

padding:20px;

}


.profile{

text-align:center;

}


.profile img{

width:80px;
border-radius:50%;

}



.sidebar button{

width:100%;
margin-top:12px;

}



/* CHAT */


.chat{

margin-left:250px;

height:100vh;

display:flex;

flex-direction:column;

}


.header{

padding:15px;

background:
rgba(255,255,255,.1);

font-size:22px;

}



.messages{

flex:1;

overflow:auto;

padding:20px;

}



.user{

background:#10b981;

padding:12px;

margin:10px;

border-radius:15px;

max-width:70%;

margin-left:auto;

}



.bot{

background:rgba(255,255,255,.15);

padding:12px;

margin:10px;

border-radius:15px;

max-width:70%;

}



.input{

display:flex;

padding:15px;

gap:10px;

}


.input input{

flex:1;

padding:12px;

border-radius:10px;

border:none;

}


</style>

</head>


<body>



<!-- LOGIN -->

<div id="loginPage">


<div class="login-box">

<h2>
🔒 AI Chat Premium
</h2>


<br>


<input id="pass"
type="password"
placeholder="Password">


<br><br>


<button onclick="login()">
Login
</button>


<p id="error"></p>


</div>


</div>





<!-- APP -->


<div id="app">



<div class="sidebar">


<div class="profile">


<img src="https://cdn-icons-png.flaticon.com/512/4712/4712109.png">


<h3>
AI User
</h3>


</div>



<hr>


<button onclick="clearChat()">
🗑 Clear Chat
</button>


<button onclick="exportChat()">
📄 Export Chat
</button>


<button onclick="openGames()">
🎮 Game Center
</button>


<button onclick="logout()">
🚪 Logout
</button>



</div>





<div class="chat">


<div class="header">

🤖 AI Chat Premium

</div>




<div id="messages"
class="messages">

</div>




<div class="input">


<input id="text"
placeholder="Ask AI...">


<button onclick="voiceInput()">
🎤
</button>


<button onclick="send()">
Send
</button>



</div>



</div>



</div>





<!-- GAME AREA WILL BE ADDED IN PART 2 -->


<div id="games"
style="display:none">


</div>




<script>


const PASSWORD="1234";


function login(){

if(pass.value===PASSWORD){

loginPage.style.display="none";

app.style.display="block";

loadChat();

}

else{

error.innerHTML="Wrong Password";

}

}



function logout(){

location.reload();

}



</script>


</body>
</html>
