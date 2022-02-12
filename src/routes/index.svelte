<script context="module">
  export async function load({ url }) {
    const query = fetch("https://jservice.io/api/random")
      .then((response) => response.json())
      .then((data) => {
        return data;
      });
    let triviaData = await query;
    return {
      props: {
        trivia: triviaData[0],
      },
    };
  }
</script>

<script>
  import Card from "$lib/card.svelte";
  import RevealBtn from "$lib/revealBtn.svelte";
  import { revealed } from "./stores.js";

  export let trivia;

  let answer;

  revealed.subscribe((value) => {
    answer = value;
  });
</script>

<h1>Trivia</h1>

<div class="card-deck">
  <Card title="Question" text={trivia.question} />
  {#if answer}
    <Card title="Answer" text={trivia.answer} />
  {/if}
</div>

<RevealBtn />

<style>
  h1 {
    font-family: "Bebas Neue", cursive;
    letter-spacing: 1px;
    text-align: center;
  }
  .card-deck {
    max-width: 700px;
    margin: 0 auto;
    display: grid;
    /* gap: 30px; */
    row-gap: 30px;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    place-items: center;
  }
</style>
