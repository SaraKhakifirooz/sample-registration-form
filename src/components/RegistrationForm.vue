<template>
  <div>
    <h1>{{ getCurrentStepHeader }}</h1>
    <div class="form_section section_c">
      <div v-if="currentStep === 'username'">
        <input type="text" id="username" name="username" v-model="username" placeholder="Enter username">
      </div>
      <div v-else-if="currentStep === 'email'">
        <input type="email" id="email" name="email" v-model="email" placeholder="Enter email">
      </div>
      <div v-else>
        <h2>Review your information:</h2>
        <div>
          <p>Username : {{ username }}</p>
          <p>Email : {{ email }}</p>
        </div>
      </div>
      <button id="btn-prev" @click="prevStep" :disabled="currentStep === 'username'">Prev</button>
      <button id="btn-next" @click="nextStep" :disabled="currentStep === 'review'">Next</button>
    </div>
  </div>
</template>
  
<script>
export default {
  data() {
    return {
      currentStep: 'username',
      username: '',
      email: ''
    };
  },
  computed: {
    getCurrentStepHeader() {
      return 'Step: ' + this.currentStep;
    }
  },
  methods: {
    nextStep() {
      if (this.currentStep === 'username') {
        // Validate username
        if (!this.username.trim()) {
          alert('Please enter a username.');
          return;
        }
        this.currentStep = 'email';
      } else if (this.currentStep === 'email') {
        // Validate email
        if (!this.email.trim() || !this.email.includes('@')) {
          alert('Please enter a valid email address.');
          return;
        }
        this.currentStep = 'review';
      }
    },
    prevStep() {
      if (this.currentStep === 'review') {
        this.currentStep = 'email';
      } else if (this.currentStep === 'email') {
        this.currentStep = 'username';
      }
    }
  }
};
</script>
  

<style scoped>
.form_section {
  background-color: #fff;
  padding: 10px;
  font-size: 15px;
  width: 100%;
}

input {
  font-size: 15px;
  padding: 10px;
}

p {
  font-weight: bold;
}

button {
  padding: 3px 10px;
  font-size: 15px;
  margin: 5px;
}
</style>