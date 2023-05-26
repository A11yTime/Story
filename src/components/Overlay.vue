<template>
<div>
    <transition name="modal">
         <div v-if="isOpen" class="overlay">
            <div class="modal">
               <h2>Modal title</h2>
               <p>Modal dialog with vue.js</p>
               <div>
                <Close @close-btn="modalOpen" ></Close>
               </div>
            </div>
         </div>
    </transition>
    <button @click="modalOpen" ref="openModal">Open Modal</button>
</div>
</template>
<script>
import Close from './Close.vue';
 export default{
    name: 'Overlay',
    components: {
      Close,
    },
    
    data(){
        return{
          isOpen: false,
        }
    },
    methods: {
        modalOpen(){
            this.isOpen = !this.isOpen;
            if(!this.isOpen){
              this.focusOnEditButton()
            }
            
        },
        focusOnEditButton() {
          this.$nextTick(() => {
            const editButtonRef = this.$refs.openModal;
            editButtonRef.focus();
      });
    },
    }
 }
</script>
<style scoped>
.modal{
    width: 500px;
    margin: 0px auto;
    padding: 20px;
    background-color: #fff;
    border-radius: 2px;
    box-shadow: 0px 2px 8px 3px;
    transition: all 0.2 ease-in;
    font-family: Arial, Helvetica, sans-serif;
}
.overlay{
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
    background: #00000094;          
    z-index: 9999;
    transition: opacity 0.2ms ease;
}
button {
  padding: 7px;
  margin-top: 10px;
  background-color: green;
  color: white;
  font-size: 1.1rem;
}

.fadeIn-enter {
  opacity: 0;
}
.fadeIn-leave-active {
  opacity: 0;
  transition: all 0.2s step-end;
}

.fadeIn-enter .modal,
.fadeIn-leave-active.modal {
  transform: scale(1.1);
}
</style>