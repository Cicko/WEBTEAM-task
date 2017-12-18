<template>
  <form>
    <v-text-field
      label="Name"
      v-model="name"
      :error-messages="nameErrors"
      :counter="10"
      @input="$v.name.$touch()"
      @blur="$v.name.$touch()"
      required
    ></v-text-field>
    <v-text-field
      label="E-mail"
      v-model="email"
      :error-messages="emailErrors"
      @input="$v.email.$touch()"
      @blur="$v.email.$touch()"
      required
    ></v-text-field>
    <v-text-field
      label="Message"
      v-model="message"
      :error-messages="messageErrors"
      @change="$v.message.$touch()"
      @blur="$v.message.$touch()"
      required
    ></v-text-field>
    <v-btn @click="submit">submit</v-btn>
    <v-btn @click="clear">clear</v-btn>
  </form>
</template>

<script>
  import { validationMixin } from 'vuelidate'
  import { required, maxLength, email } from 'vuelidate/lib/validators'

  export default {
    mixins: [validationMixin],
    validations: {
      name: { required, maxLength: maxLength(10) },
      email: { required, email },
      message: { required },
    },
    data () {
      return {
        name: '',
        email: '',
        message: '',
      }
    },
    methods: {
      submit () {
        this.$v.$touch()
      },
      clear () {
        this.$v.$reset()
        this.name = ''
        this.email = ''
        this.message = ''
      }
    },
    computed: {
      messageErrors () {
        const errors = []
        if (!this.$v.message.$dirty) return errors
        !this.$v.message.required && errors.push('Message is required')
        return errors
      },
      nameErrors () {
        const errors = []
        if (!this.$v.name.$dirty) return errors
        !this.$v.name.maxLength && errors.push('Name must be at most 10 characters long')
        !this.$v.name.required && errors.push('Name is required.')
        return errors
      },
      emailErrors () {
        const errors = []
        if (!this.$v.email.$dirty) return errors
        !this.$v.email.email && errors.push('Must be valid e-mail')
        !this.$v.email.required && errors.push('E-mail is required')
        return errors
      }
    }
  }
</script>
