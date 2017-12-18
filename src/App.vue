<template>
  <v-app>
    <v-toolbar fixed app>
    </v-toolbar>
    <v-content>
      <v-container grid-list-md text-xs-center>
        <v-layout row wrap>
          <v-flex class="xs6">
            <my-form class="mx-5">
            </my-form>
          </v-flex>
          <v-flex class="xs6">
            <my-list class="mx-5">
            </my-list>
          </v-flex>
        </v-layout>
      </v-container>
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
