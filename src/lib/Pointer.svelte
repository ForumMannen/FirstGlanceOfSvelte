<script>
  let mousePosition = { x: 0, y: 0 };
</script>

<div on:pointermove={(e) => (mousePosition = { x: e.clientX, y: e.clientY })}>
  <p>The mouse position is at x:{mousePosition.x} y:{mousePosition.y}</p>
</div>

<style>
  div {
    position: fixed;
    min-height: 100vh;
    width: 100%;
    left: 0;
    top: 0;
  }
</style>
