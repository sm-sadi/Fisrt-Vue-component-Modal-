<template>
    <div class="backdrop" @click.self="closemodal">
        <div class="modal" :class="{ sale : theme === 'sale' } ">
            <h1>{{header}}</h1>
            <p>{{text}}</p>
            <slot name="links">

            </slot>
            
         
        </div>
    </div>


</template>
<script>
export default {
    props : ['header', 'text' , 'theme'],
    methods : {
        closemodal(){
            this.$emit('close')
        }
    }
}
</script>

<style>
 .modal{
     width: 400px;
     padding:20px;
     margin: 100px auto;
     background:white;
     border-radius: 10px;
 }
 .backdrop{
     top: 0;
     position: fixed;
     background-color: rgb(236 232 232 / 58%);
     width: 100%;
     height: 100%;
 }
 .modal.sale{
     background: crimson;
     color: white;
 }
 .modal.h1{
     color:white;
 }
 .modal a{
    text-decoration :none;
    color: white;
    background-color: rgb(18, 38, 216);
    padding: 5px 5px;
    border-radius: 4px;
  }
</style>