<template>
  <Button></Button>
  <Overlay></Overlay>
</template>
<script>
import Overlay from './components/Overlay.vue';
import Button from './components/Button.vue';

export default{
    name: 'App',
    components: {
        Overlay,
        Button,
    },
}
</script>
<style>

</style>