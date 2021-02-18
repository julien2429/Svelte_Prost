<script>
  import Login  from "./Login.svelte";
  let is_logged = false;
  function show_register() {
	is_registered=true;
	show_login();
  }
  function show_login() {
    is_logged = true;
  }
  function hide_login() {
    is_logged = false;
	is_registered= false;
  }
  let is_registered= false;
</script>

<main>
  <div class="box" />
  <div class="top_line" />
  <h1>Referatele grozave</h1>
  
  <button class="register_btn"  on:click={show_register}>Register</button>
  <button class="login_btn" on:click={show_login}>Login</button>
  {#if is_logged}
    <Login {is_registered}  on:closeIt={hide_login} />		
  {/if}
  <img class="Carte" src="../Poze/Carti.png" alt="Cardati">
</main>

<style>
  .Carte{
	position: absolute;
    top: 50px;
	left: 10%;
	height: 140px;
	z-index: 1;
	
  }
  h1 {
    position: absolute;
    text-align: center;
	left: 43%;
	top:70px;
    font-style: italic;
    height: 30vw;
	z-index: 1;
    
  }
  .login_btn {
    position: absolute;
    padding: 0px;
    border: solid 3px rgb(0, 0, 0);
    left: 92%;
    top: 0vw;
	font-style: italic;
    height: 40px;
    width: 80px;
    z-index: 2;
  }
  .register_btn {
    position: absolute;
    padding: 0px;
    border: solid 3px rgb(0, 0, 0);
    left: 85%;
	font-style:italic ;
    top: 0px;
    height: 40px;
    width: 80px;
    z-index: 2;
  }
  .box {
    position: fixed;
    top: 0%;
    left: 0%;
	background-image: url("../Poze/Fundal.jpg");
    border-bottom: 6px solid rgb(3, 3, 3);
    width: 110vw;
    height: 200px;
    z-index: 1;
  }
  .top_line {
    position: fixed;
    top: 0%;
    left: 0%;
    border-bottom: 6px solid rgb(3, 3, 3);
    background-color: rgb(56, 55, 55);
    width: 110vw;
    height: 40px;
    z-index: 1;
  }
</style>
