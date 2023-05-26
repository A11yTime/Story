<template>
    <div>
        <button class="btn" @click="$emit('close-btn')" ref="labelInput">Close</button>
    </div>
</template>
<script>
export default{
    name: 'Close',
    mounted() {
   const labelInputRef = this.$refs.labelInput;
   labelInputRef.focus();
}
}
</script>
<style>
.btn {
  padding: 7px;
  margin-top: 10px;
  background-color: green;
  color: white;
  font-size: 1.1rem;
}
</style>    