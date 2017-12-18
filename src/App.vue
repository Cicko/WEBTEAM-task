<template>
  <v-app>
    <v-toolbar fixed app>
    </v-toolbar>
    <v-content>
      <my-form class="mx-5">
      </my-form>
    </v-content>
  </v-app>
</template>

<script>
import myForm from './Form.vue'
  export default {
    components: {
      myForm,
    },
    data () {
      return {
      }
    }
  }
</script>
