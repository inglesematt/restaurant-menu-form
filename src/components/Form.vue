<template>
  <form v-on:reset="resetFields" v-on:submit.prevent="submitForm">

      <label class="required">First Name:</label>
      <input type="text" required  v-model="firstName">
      <label class="required">Last Name:</label>
      <input type="text" required v-model="lastName">
      <label>Company:</label>
      <input type="text" required v-model="company">
      <label class="required">Email:</label>
      <input type="email" required v-model.trim="email" v-bind:style="[touchedEmailStyles,invalidEmailStyles]">
      <label>Enquiry:</label>
      <select v-model="role" placeholder="Enquiry type">
      <option value="general">General Enquiry</option>
      <option value="order">Order from the menu</option>
      <option value="allergies">Enquiry about food allergies</option>
      <option value="allergies">Review our service</option>
      <option value="allergies">Complaints</option>
      </select>
      <label>Message:</label>
      <div>
      <textarea v-model="message" placeholder="add enquiry here" ></textarea>    
      </div>

      <div class="terms">
          <input type="checkbox" v-model="terms" required>
          <label class="required">Accept terms and conditions</label>
      </div>
<div id="submitMessage">
        <button type="reset" class="reset">Reset</button>
        <button type="submit" v-bind:disabled="!formIsValid" v-bind:style="submitButtonStyles" @click="say('Contact form has been submitted successfully')">Submit enquiry</button>
      </div>
  </form>

</template>

<script>
export default {
    data() {
        return {
        firstName: '',
        lastName: '',
        company: '',
        email: '',
        password: '',
        role: '',
        message: '',
        terms: false
    }
    },
      methods: {
    resetFields: function() {
      this.firstName = '',
      this.lastName = '',
      this.company = '',
      this.email = '',
      this.message = '',
      this.terms = false
    },
   say(message) {
      alert(message)
      .mount('#inline-handler')
    }
  },
    computed: {
      touchedEmailStyles: function() {
  if (this.email) {
    return {
      'border-color': '#bdbcbc',
      'border-width': '2px'
    }
  } else {
    return {
      'border-color': '#e0e0e0',
      'border-width': '2px'
    }
  }
},
        
    emailIsValid: function (email) {
      var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
      return re.test(this.email);
    },
    invalidEmailStyles: function() {
  if (this.email && !this.emailIsValid) {
    return {
      'background-color': '#ffeded',
      'border-color': '#da5252'
    }
    }
    },
           formIsValid: function() {
      return this.firstName && this.lastName && this.emailIsValid && this.terms;
    },
    submitButtonStyles: function() {
      if (this.formIsValid) {
        return {
          'background-color': '#75abe0',
          'color': 'white',
          cursor: 'pointer'
        }
      } else {
        return {
          'background-color': '#eee',
          cursor: 'default'
        }
      }
    }
  }
}
</script>

<style>

form {
    max-width:420px;
    margin: 5px auto;
    background: white;
    text-align: left;
    padding: 10px 10px 80px 10px;
    border-radius: 10px;
}

label {
    color: #aaa;
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
    color: #555;
}
input[type="checkbox"] {
    display: inline-block;
    width: 16px;
    margin: 0 10px 0 0;
    position: relative;
    top: 2px;
}

  .required:after {
    content:" *";
    color: red;
}

textarea {
   
    display: inline-block;
    max-width: 100%;
    min-width:95%;
    min-height:200px;
    margin: 5px auto;
    background: #ccc;
    text-align: left;
    padding: 5px;
    border-radius: 10px;
      font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
   
}

button {
    border-radius: 5px;
        margin: 2px;
      font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
}


button.reset {
  background-color: #75abe0;
   color: white;
}

button.reset:hover {
  background-color: #2567f7;
}


.invalid {
  border: 1px solid #fa4359;
}



</style>