<template>
    <!-- this is our modal component -->
    <div  class="backdrop" @click.self="closeModal"> <!-- on the event ofcourse -->
        <div  class="modal" :class="{sale:theme ==='sale'}" >
           <slot>default content</slot> <!-- what ever we enter in the modal tag will be generated into the slot component-->
            <div class="actions">
              <slot name='links'> 

              </slot>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props:['theme'],
        methods:{
            closeModal(){
                this.$emit('close') // emitting an event 
            }
        } // dynamic prompt value, for other data structure we use teh binding

    }
</script>

<style scoped>
    .modal{
        width: 400px;
        
        padding: 20px;
        margin: 90px auto;
        background: white;
        border-radius: 10px;
    }
    .backdrop{
        top: 0;
        position: fixed;
        background: rgba(0, 0, 0, 0.5);
        height: 100%;
        width: 100%;
    }
    h1{
        color: #0078f1;
    }
    p{
        color: #2c3e50;
    }
    .modal.sale{
        color: white;
        background: rgb(194, 73, 73);
    }
    .modal.sale h1{
        color: white;
    }

    .modal.sale .actions a{
        color: white;
        font-style: none;
        padding: 5px 8px;
        border: 1px solid white;
    }

    .modal.sale .actions{
        text-align: center;
        display: flex;
        align-content: center;
        justify-content: center;
        gap: 2rem;
    }
    
</style>

