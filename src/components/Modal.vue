<template>
  <teleport to="body">
    <div id="center">
      <h2>modal-teleport</h2>
    </div>
  </teleport>
</template>
<script lang="ts">
export default {};
</script>
<style>
#center {
  width: 200px;
  height: 200px;
  border: 2px solid black;
  background: white;
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate3d(-50%, -50%, 0);
}
</style>