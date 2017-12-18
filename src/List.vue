<template>
  <v-list three-line>
            <v-subheader v-text="'List of messages'"></v-subheader>
            <template v-for="message in messages">
              <v-divider v-if="message.divider" v-bind:inset="message.inset"></v-divider>
              <v-list-tile v-else v-bind:key="message.name" @click="">
                <v-list-tile-content>
                  <v-list-tile-title v-text="message.name + ' - ' + message.email"></v-list-tile-title>
                  <v-list-tile-sub-title v-text="message.date.toString()"></v-list-tile-sub-title>
                  Message: {{message.message}}
                </v-list-tile-content>
              </v-list-tile>
            </template>
      </v-list>
</template>

<script>
  export default {
    props: ['messages'],
    data () {
      return {
        messages: this.messages
      }
    },
  }
</script>
