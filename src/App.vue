<template>
  <v-app>
    <v-toolbar fixed app>
    </v-toolbar>
    <v-content>
      <v-container grid-list-md text-xs-center>
        <v-layout row wrap>
          <v-flex v-if="view_inx === 0 || view_inx === 1"
            :class="view_inx === 0 ? 'xs6' : 'xs12'">
            <my-form class="mx-5">
            </my-form>
          </v-flex>
          <v-flex v-if="view_inx === 0 || view_inx === 2"
            :class="view_inx === 0 ? 'xs6' : 'xs12'">
            <my-list class="mx-5">
            </my-list>
          </v-flex>
        </v-layout>
      </v-container>
      <div class="text-xs-center">
        <v-btn primary @click="switchView">{{actual_view}}</v-btn>
      </div>
    </v-content>
  </v-app>
</template>

<script>
import myForm from './Form.vue'
import myList from './List.vue'

const Views = [
  'Form + List',
  'Only Form',
  'Only List'
]

export default {
  components: {
    myForm,
    myList,
  },
  data () {
    return {
      views: Views,
      view_inx: 0,
      actual_view: Views[0],
    }
  },
  methods: {
    switchView () {
      this.view_inx = ++this.view_inx % Views.length
      this.actual_view = Views[this.view_inx]
    },
  }
}
</script>
