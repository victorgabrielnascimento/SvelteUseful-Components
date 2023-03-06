<script>
  import { onMount } from "svelte";

  async function generatePopUp() {
    const getChartInformations = async () => {
      const resJson = await res.json();
      return resJson;
    };
  }

  let popupActive = false;

  onMount(generatePopUp);

  function togglePopup() {
    popupActive = !popupActive;
  }
</script>

<div class="pai">
  <div class="trash"><i class="fas fa-trash" on:click={togglePopup} /></div>
</div>

<div class="popup-wrapper" class:hidden={!popupActive}>
  <div class="popup">
    <div class="popup-content">
      <h2>ATENÇÃO!</h2>

      <p>Você realmente deseja excluir o dispositivo?</p>

      <p>[Name]</p>
      <div class="pai2">
        <button><h1>DESATIVAR</h1></button>
      </div>
    </div>
    <div class="popup-close" on:click={togglePopup}>
      <i class="fas fa-times" />
    </div>
  </div>
</div>

<style>
  i {
    cursor: pointer;
  }
  .pai {
    background-color: transparent;
    width: 6%;
    margin-left: 47%;
    margin-top: 20%;
  }

  .pai2 {
    background-color: rebeccapurple;
    width: 40%;
  }

  .trash {
    font-size: 100px;
    color: #9b9b9bd3;
    text-align: center;
  }

  .trash:hover {
    transition: 0.3s;
    text-shadow: 1px 1px 20px #ff00006e;
  }

  .popup-wrapper {
    background-color: #00000080;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: 999999;
    display: flex;
  }

  .popup {
    width: 50%;
    height: 40%;
    margin: 16% auto;
    padding: 60px;
    background-color: rgb(255, 255, 255);
    position: relative;
    border-radius: 15px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .popup-content h2 {
    text-align: center;
    font-family: "Montserrat", sans-serif;
    font-weight: bolder;
    line-height: 65px;
  }

  .popup-content p {
    text-align: center;
    font-family: "Montserrat";
    font-size: 28px;
  }

  button {
    display: flex;
    width: 180px;
    height: 6vh;
    border-radius: 4px;
    background-color: #dd3e3e;
    border: none;
    cursor: pointer;
    align-items: center;
    justify-content: center;
    margin-left: 14%;
  }

  button h1 {
    font-family: "Montserrat";
    font-weight: lighter;
    font-size: 20px;
    color: white;
    padding-top: 4%;
  }

  .popup-close {
    font-family: "Montserrat";
    font-size: 40px;
    position: absolute;
    top: 1px;
    right: 18px;
    cursor: pointer;
    font-weight: bolder;
  }

  .hidden {
    display: none;
  }
</style>
