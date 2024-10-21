<script type="module">
  import { Runtime, Inspector } from "@observablehq/runtime";
  import define from "@fil/druidjs-worker";

  const notebook = new Runtime().module(define, (name) => {
    return ["result"].includes(name);      
  });

  $: result = null;

  notebook.value("result").then((value) => {
    result = value;
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
