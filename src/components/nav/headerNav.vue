<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">{{name}}</a>
      <a class="navbar-brand" href="#">{{msg}}</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        </ul>
        <form class="d-flex">
          <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
          <button v-on:click="rename" type="button" >Search</button>
           <button v-on:click="methodsChange()" type="button" >me</button>
        </form>
      </div>
    </div>
  </nav>
</template>
<script lang="ts">
import { defineComponent } from 'vue'
export default defineComponent({
  name: 'navHeader',
  props: {
    msg: {
      type : String,
      required: true,
    },
    name : {
      type : String,
    },
    customs: {
      type: String
    }
  },
  data: function(){
    return {...this.$props}
  },
  methods: {
    methodsChange : function() {
      alert("methodsChange");
    }
  },
   computed:{
    rename: function() {
        alert(this.$data.msg)
        this.$data.msg = "message";
    }
  },
})
</script>