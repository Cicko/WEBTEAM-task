<template>
  <v-app>
    <v-toolbar fixed app>
    </v-toolbar>
    <v-content>
      <my-form class="mx-5">
      </my-form>
      <my-list class="mx-5">
      </my-list>
    </v-content>
  </v-app>
</template>

<script>
import myForm from './Form.vue'
import myList from './List.vue'

export default {
  components: {
    myForm,
    myList,
  },
  data () {
    return {
    }
  }
}
</script>
