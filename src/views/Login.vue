<template>
  <form @submit.prevent="handleSubmit" >
    <label>Username</label>
    <input type="text" required v-model="userName" />

    <label>Password</label>
    <input type="password" required v-model="password" />
    <div v-if="passwordError" class="error">{{ passwordError }}</div>

    <div class="terms">
      <input type="checkbox" required v-model="terms" />
      <label>Accept Terms and Conditions</label>
    </div>

    <div class="submit">
      <button>Create an Account</button>
    </div>

    <p>Not Already a Member?<label class="link">Sign Up</label></p>

  </form>
</template>

<script>
export default {
  data () {
    return {
      userName: 'someone',
      password: '123test',
      terms: false,
      passwordError: '',
      verifiedUser: false
    }
  },
  methods: {
    handleSubmit() {
      console.log('submit')
    }
  }
}
</script>

<style>
form {
  max-width: 420px;
  margin: 30px auto;
  background: rgb(238, 198, 198);
  text-align: left;
  padding: 40px;
  border-radius: 10px;
}
label {
  color:#aaa;
  display: inline-block;
  margin: 25px 0 15px;
  font-size: 0.6em;
  text-transform: uppercase;
  letter-spacing: 1px;
  font-weight: bold;
}
input, select {
  display: block;
  padding: 10px 6px;
  width: 100%;
  box-sizing: border-box;
  border: none;
  border-bottom: 1px solid #ddd;
  color: rgb(85, 85, 85);
}
input[type="checkbox"] {
  display: inline-block;
  width: 16px;
  margin: 0 10px 0 0;
  position: relative;
  top: 2px;
}
.pill {
  display: inline-block;
  margin: 20px 10px 0 0;
  padding: 6px 12px;
  background: #eee;
  border-radius: 20px;
  font-size: 12px;
  letter-spacing: 1px;
  font-weight: bold;
  color: #777;
  cursor: pointer;  
}
button {
  background: #0b6dff;
  border: 0;
  padding: 10px 20px;
  margin-top: 20px;
  color: white;
  border-radius: 20px;
  cursor: pointer;
}
.submit {
  text-align: center;
}
.error {
  color: #ff0062;
  margin-top: 10px;
  font-size: 0.8em;
  font-weight: bold;
}
.link {
  cursor: pointer;
}
</style>