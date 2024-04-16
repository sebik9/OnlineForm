<template>
  <head>
    <title>Ticketino</title>
  </head>
  <body>
    <header>
      <h1>Ticketino</h1>
    </header>
    <form>
      <div class="bgc">
        <div class="row">
          <div class="field">
            <label for="first-name" class="name">First Name</label>
            <input type="text" id="first-Name" v-model="firstName" @input="validateForm" />
          </div>
          <div class="field">
            <label for="last-name" class="name">Last Name</label>
            <input type="text" id="last-name" v-model="lastName" @input="validateForm" />
          </div>
        </div>
        <div class="row">
          <div class="field-email">
            <label for="email">Email</label>
            <input type="text" id="email" v-model="email" @input="validateForm" />
          </div>
        </div>
        <div class="row">
          <div class="field">
            <label for="ticket-quantity">Ticket Quantity</label>
            <select id="ticket-quantity" v-model="ticketQuant">
              <option value="1">1</option>
              <option value="2">2</option>
              <option value="3">3</option>
              <option value="4">4</option>
              <option value="5">5</option>
              <option value="6">6</option>
            </select>
          </div>
          <div class="field">
            <legend>Ticket Type</legend>
            <div>
              <input type="radio" id="standard" value="standard" v-model="ticketType" />
              <label for="standard">standard</label>
            </div>
            <div>
              <input type="radio" id="vip" value="vip" v-model="ticketType" />
              <label for="vip">VIP</label>
            </div>
          </div>
        </div>
        <div class="row checkbox">
          <fieldset>
            <legend>How did you hear about this Event?</legend>
            <div>
              <input type="checkbox" id="friend" value="friend" v-model="referral" />
              <label for="friend">From a friend</label>
            </div>
            <div>
              <input type="checkbox" id="television" value="television" v-model="referral" />
              <label for="television">On television</label>
            </div>
            <div>
              <input type="checkbox" id="social-media" value="socialMedia" v-model="referral" />
              <label for="social-media">Social Media</label>
            </div>
          </fieldset>
        </div>
        <div class="row">
          <div class="field-email">
            <label for="special" class="special-label">Special requests:</label>
            <textarea id="special" v-model="specialRequest"></textarea>
          </div>
        </div>
        <div class="row">
          <fieldset>
            <legend>Purchase Agreement</legend>
            <p class="agree-text">
              I, PH, wish to buy {{ ticketType }} ticket. I understand tha all ticket sales are
              final.
            </p>
            <input
              type="checkbox"
              name="agreement"
              id="agree"
              v-model="agreementBox"
              @change="validateForm"
            />
            <label for="agree">I Agree</label>
          </fieldset>
        </div>
        <div class="row">
          <button type="reset" class="reset-btn" @click="formReset">Reset</button>
          <button type="submit" class="confirm-btn" :disabled="!isValid">Confirm order</button>
        </div>
      </div>
    </form>
  </body>

  <div>
    Dev pane data test<br />
    firstname: {{ firstName }}<br />
    lastname {{ lastName }}<br />
    e-mail: {{ email }}<br />
    ticketcount: {{ ticketQuant }}<br />
    ticketType: {{ ticketType }}<br />
    referal: {{ referral }}<br />
    special: {{ specialRequest }}<br />
    agreeBox: {{ agreementBox }}<br />
    fullname: {{ fullName }}<br />
    valid? {{ isValid }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
      ticketQuant: 1, //default value of 1
      ticketType: 'standard', // or VIP
      referral: [],
      specialRequest: '',
      agreementBox: false, //default value of false user has to agree manualy
      isValid: false
    }
  },
  computed: {
    fullName() {
      return this.firstName.trim() + ' ' + this.lastName.trim()
    }
  },
  methods: {
    validateForm() {
      if (this.firstName && this.lastName && this.email && this.agreementBox) {
        this.isValid = true
      } else {
        this.isValid = false
      }
    },
    formReset() {
      this.firstName = ''
      this.lastName = ''
      this.email = ''
      this.ticketQuant = 1
      this.referral = []
      this.specialRequest = ''
      this.agreementBox = false
      this.validateForm()
    }
  }
}
</script>

<style scoped>
body {
  max-width: 800px;
}

header {
  background-color: #4c7ef3;
  align-items: center;
  height: 60px;
  min-width: 280px;
}

h1 {
  letter-spacing: 0.3px;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 1.5rem;
  font-weight: 700;
  color: white;
  max-width: 200px;
  padding: 15px;
}

form {
  background-color: #f9f9f9;
  display: flex;
  flex-direction: column;
  padding: 1.86rem 20%;
  min-width: 200px;
}

.row {
  display: flex;
  flex-direction: row;
  margin-top: 5px;
  margin-bottom: 5px;
}

.field {
  width: 50%;
}

.field-email {
  width: 100%;
}

#email {
  width: calc(100% - 70px);
}

#special {
  width: calc(100% - 6px);
  max-width: calc(100% - 47px);
  max-height: 90px;
  min-height: 30px;
  margin-top: 5px;
}

input {
  margin-right: 15px;
  padding: 0.71rem;
  margin-top: 5px;
}

fieldset {
  border: none;
  margin-left: -12px;
}

select {
  display: flex;
  flex-direction: row;
  width: 80%;
  height: 39px;
  margin-top: 5px;
  min-width: 196px;
}

.reset-btn {
  width: 100%;
}

.confirm-btn {
  width: 100%;
}

.agree-text {
  max-width: 440px;
}

@media (max-width: 734px) {
  .row {
    flex-direction: column;
    width: 100%;
  }
  .field {
    width: 100%;
  }
  .name {
    width: 100%;
    float: left;
  }

  select {
    width: 100%;
  }

  .field-email {
    width: calc(100% - 27px);
  }

  #email {
    width: 100%;
    min-width: 169px;
  }

  #special {
    width: calc(100% + 21px) !important;
    max-width: calc(100% + 21px);
  }
}
</style>
