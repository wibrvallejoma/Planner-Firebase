<template>
  <v-container>
    <h1>Login page</h1>
    <v-row>
      <form @submit.prevent="pressed">
        <v-col cols="12">
          <label for="email">Email</label>
          <v-text-field type="email" name="email" v-model="email"></v-text-field>
        </v-col>
        <v-col cols="12">
          <label for="password">Password</label>
          <v-text-field type="password" name="password" v-model="pass"></v-text-field>
        </v-col>
        <v-col cols="12">
          {{ err.message }}
        </v-col>
        <v-btn type="submit">Log in</v-btn>
      </form>
    </v-row>

  </v-container>
</template>

<script>
import firebase from 'firebase/app';
import 'firebase/auth';

export default {
  data() {
    return {
      email: '',
      pass: '',
      err: '',
    }
  },
  methods: {
    pressed() {
      firebase.auth().signInWithEmailAndPassword(this.email, this.pass)
        .then(data => {
          console.log(data);
          this.$router.push('/secret');
        })
        .catch(err => {
          this.err = err
        });
    }
  },
}
</script>
