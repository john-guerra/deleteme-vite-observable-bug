<script type="module">
  import { Runtime, Inspector } from "@observablehq/runtime";
  import define from "@fil/druidjs-worker";
  import { onMount } from "svelte";
  const notebook = new Runtime().module(define, (name) => {
    return ["result"].includes(name);      
  });

  $: result = null;

  onMount(async () => {
    result = await notebook.value("result");
  });
   

  

  
</script>

<div id="observablehq-result-a0a5b4b3">${JSON.stringify(result)}</div>
<p>
  Credit: <a href="https://observablehq.com/@fil/druidjs-worker"
    >DruidJS worker by Fil</a
  >
</p>

<link
  rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/@observablehq/inspector@5/dist/inspector.css"
/>
