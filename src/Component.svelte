<svelte:options tag="vl-button" />

<script>
  const { css } = require("@emotion/css");
  import { darken } from "color2k";

  export let color = "";
  export let width = "";
  export let height = "";
  export let fontSize = "";

  let darkcolor = darken(color, 0.21);

  export const button = css`
    background-color: ${color};
    font-size: 1em;
    white-space: nowrap;
    border-radius: 5px;
    max-width: ${width};
    max-height: ${height};
    font-size: ${fontSize};
    color: rgb(63, 63, 63);
    border: none;
    transition: 0.1s;
    cursor: pointer;
    &:hover {
      background: ${darkcolor};
    }
  `;
</script>

<button class={button}><slot /></button>

<style>
  .lg {
    width: 5rem;
    height: 2.75rem;
    font-size: 1.75rem;
  }
  .img {
    height: 1.3rem;
    display: inline;
  }
</style>
