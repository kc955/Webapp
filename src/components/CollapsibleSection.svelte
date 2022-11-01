<script>
    // based on suggestions from:
    // Inclusive Components by Heydon Pickering https://inclusive-components.design/collapsible-sections/
    export let headerText;

    let expanded = false
</script>

<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Roboto:300,400,500,600,700"
/>

<div class="collapsible">
    <h3>
        <button aria-expanded={expanded} on:click={() => expanded = !expanded}>
          {headerText}
          <svg viewBox="0 0 20 20" fill="none" >
            <path class="vert" d="M10 1V19" stroke="black" stroke-width="2"/>
            <path d="M1 10L19 10" stroke="black" stroke-width="2"/>
          </svg>
        </button>
    </h3>
    <div class='contents' hidden={!expanded}>
        <slot></slot>
    </div>
</div>

<style>
  .collapsible {
    border-bottom: 1px solid var(--gray-light, rgb(194, 194, 194));
    width: 20cm;
    font-family: 'Roboto';font-size: 17px;
  }
	
	h3 {
		margin: 0;
	}
	
  button {
    background-color: var(--background, rgb(219, 219, 219));
    color: var(--gray-darkest, #000000);
    display: flex;
		justify-content: space-between;
    width: 100%;
		border: none;
		margin: 0;
		padding: 1em 0.5em;
    font-size: 0.8em;
  }

  .content{
    background-color: rgb(146, 146, 146);
    border: #000000;
  }
  button[aria-expanded="true"] {
    border-bottom: 1px solid var(--gray-light, rgb(225, 225, 225));
  }

    button[aria-expanded="true"] .vert {
        display: none;
    }

    button:focus svg{
        outline: 2px solid;
    }

    button [aria-expanded="true"] rect {
        fill: currentColor;
    }

    svg {
        height: 0.7em;
				width: 0.7em;
    }
</style>