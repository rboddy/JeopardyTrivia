<script>
  import { revealed } from "/src/routes/stores.js";

  function reveal() {
    revealed.update((n) => !n);
  }
</script>

<button on:click|preventDefault|once={reveal}>Reveal Answer</button>

<style>
  button {
    display: block;
    margin: 0 auto;
    margin-top: 50px;
    border: 1px solid black;
    background-color: #eff67a;
    font-family: "Open Sans", sans-serif;
    padding: 10px;
    border-radius: 15px;
    font-size: 1.1em;
    box-shadow: 2px 4px 4px rgba(0, 0, 0, 0.25);
  }
  button:hover {
    cursor: pointer;
  }
</style>
