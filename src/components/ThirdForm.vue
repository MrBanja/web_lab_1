<template>
  <div class="hello">
    <form action="#">
      <div class="form-group">
        <label for="card">Card number: </label>
        <input type="number" class="form-control" placeholder="1111 2222 3333 4444" id="card">
      </div>
      <div class="form-group">
        <label for="CVV">CVV:</label>
        <input type="password" class="form-control" placeholder="Enter CVV" id="CVV">
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "ThirdForm"
}
</script>

<style scoped>

</style>