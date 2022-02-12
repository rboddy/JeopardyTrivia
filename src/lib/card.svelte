<script>
  export let title;

  export let text;
</script>

<div class="card">
  <div class="card-header">
    <h2>{title}</h2>
  </div>
  <p>{text}</p>
</div>

<style>
  h2 {
    font-family: "Bebas Neue", cursive;
    letter-spacing: 1px;
    text-decoration: underline;
    padding: 3px;
  }
  .card {
    height: 300px;
    width: 200px;
    border-radius: 15px;
    border: 1px solid black;
    padding: 0 15px 15px 15px;
    box-shadow: 2px 4px 4px rgba(0, 0, 0, 0.25);
  }
  .card-header {
    background-color: #eff67a;
  }
  p {
    font-family: "Open Sans", sans-serif;
  }
</style>
