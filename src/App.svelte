<script>
  import Login from "./Login.svelte";
  let is_logged = false;
  function show_register() {
    is_registered = true;
    show_login();
  }
  function show_login() {
    is_logged = true;
  }
  function hide_login() {
    is_logged = false;
    is_registered = false;
  }
  let is_registered = false;
</script>

<main>
  <div class="banner">
    <img class="h1" src="../Poze/Logo.jpg" alt="Logo" />
    <img class="Carte" src="../Poze/Carti.png" alt="Cardati" />
  </div>
  <div class="top_line">
    <label for="search" class="search">Cautare : <input type="search" /></label>
    <button class="register_btn" on:click={show_register}>Register</button>
    <button class="login_btn" on:click={show_login}>Login</button>
    {#if is_logged}
      <Login {is_registered} on:closeIt={hide_login} />
    {/if}
  </div>
  <div class="side-bar">
    
  </main>

<style>
  .search {
    position:absolute;
    color: rgb(255, 255, 255);
    float: left;
    margin-left: 30px;
    top: 0;
    font-style: italic;
    height: 40px;  
    z-index: 1;
  }
  .side-bar{
    position: absolute;
    height: 100vw;
    width: 200px;
    left: 0%;
    background-color: rgb(197, 192, 192);
    top: 236px;
    border-right:solid 6px black;
    z-index: 0;
  }
  .Carte {
    position: fixed;
    top: 60px;
    left: 20%;
    height: 140px;
    z-index: 1;
  }
  .h1 {
    position: fixed;
    top: 60px;
    left: 40%;
    z-index: 1;
    border: solid 3px rgb(0, 0, 0);
  }
  .login_btn {
    position:relative;
    float: right;
    border: solid 3px rgb(0, 0, 0);
    top: 0;
    font-style: italic;
    height: 40px;
    width: 80px;
    z-index: 1;
  }
  .register_btn {
    position:relative;
    border: solid 3px rgb(0, 0, 0);
    float: right;
    margin-left: 80;
    top: 0;
    font-style: italic;
    height: 40px;
    width: 80px;
    z-index: 1;
  }
  .banner {
    position: absolute;
    top: 0;
    left: 0;
    filter: contrast(75%) brightness(100%);
    background-image: url("../Poze/Fundal.jpg");
    border-bottom: 6px solid rgb(3, 3, 3);
    width: 100vw;
    height: 230px;
    z-index: 1;
  }
  .top_line {
    position: absolute;
    top: 0;
    left:0;
    border-bottom: 6px solid rgb(3, 3, 3);
    background-color: rgb(56, 55, 55);
    width: 100vw;
    height: 40px;
    z-index: 1;
  }
</style>
