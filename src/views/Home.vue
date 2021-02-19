<template>
  <div class="home">
    <h1 :style="colorContador" >{{titulo}}: {{ contador }}</h1>
  </div>
  <div>
    <button @click="accionIncrementar">Incrementar</button>
  </div>
  <div>
    <BtnDisminuir />
  </div>
  <hr>
  <div>
    <BtnAccion :estado="true" />
    <BtnAccion :estado="false" />
  </div>
</template>

<script>

import BtnDisminuir from '../components/BtnDisminuir'
import BtnAccion from '../components/BtnAccion'
import {mapState, mapMutations, mapActions} from 'vuex'

export default {
  name: 'Home',
  components: {
    BtnDisminuir, 
    BtnAccion
  },
  data() {
    return {
      titulo: "Mi contador con Vuex"
    }
  },
  computed: {
    ...mapState(['contador']),
    colorContador(){
      return [this.contador > 100 ? {'color': 'green'} : {'color': 'red'}]
    }
  },
  methods: {
    ...mapMutations(['incrementar']),
    ...mapActions(['accionIncrementar'])
  }
}
</script>
