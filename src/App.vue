<template>
  <head>
    <title>Ticketino</title>
  </head>
  <body>
    <header>
      <h1>Ticketino</h1>
    </header>
    <form>
      <div class="row">
        <div class="field">
          <label for="first-name" class="name">First Name</label>
          <input type="text" id="first-Name" />
        </div>
        <div class="field">
          <label for="last-name" class="name">Last Name</label>
          <input type="text" id="last-name" />
        </div>
      </div>
      <div class="row">
        <div class="field-email">
          <label for="email">Email</label>
          <input type="text" id="email" />
        </div>
      </div>
      <div class="row">
        <div class="field">
          <label for="ticket-quantity">Ticket Quantity</label>
          <select id="ticket-quantity">
            <option>1</option>
            <option>2</option>
            <option>3</option>
            <option>4</option>
            <option>5</option>
            <option>6</option>
          </select>
        </div>
        <div class="field">
          <legend>Ticket Type</legend>
          <div>
            <input type="radio" id="standard" value="standard" v-model="ticketType" />
            <label for="standard">Standard</label>
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
            <input type="checkbox" id="friend" value="friend" />
            <label for="friend">From a friend</label>
          </div>
          <div>
            <input type="checkbox" id="television" value="television" />
            <label for="television">On television</label>
          </div>
          <div>
            <input type="checkbox" id="social-media" value="socialMedia" />
            <label for="social-media">Social Media</label>
          </div>
        </fieldset>
      </div>
      <div class="row">
        <label for="special">Special requests</label>
        <textarea id="special"></textarea>
      </div>
      <div class="row">
        <fieldset>
          <legend>Purchase Agreement</legend>
          <p>I, PH, wish to buy PH. I understand tha all ticket sales are final.</p>
          <input type="checkbox" name="agreement" id="agree" />
          <label for="agree">I Agree</label>
        </fieldset>
      </div>
      <div class="row">
        <button type="reset" class="reset-btn">Reset</button>
        <button type="submit" class="confirm-btn">Confirm order</button>
      </div>
    </form>
  </body>
</template>

<script>
export default {
  data() {
    return {
      firstName: '',
      lastName: '',
      email: '',
      ticketQuant: 1, //default value of 1
      ticketType: 'Standard', // or VIP
      referral: [],
      specialRequest: '',
      agreementBox: false //default value of false user has to agree manualy
    }
  },
  computed: {},
  methods: {}
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

  background-color: pink;
  margin-top: 5px;
  margin-bottom: 5px;
}

.field {
  width: 50%;
  background-color: red;
}

.field-email {
  width: 100%;
  background-color: palegreen;
}

#email {
  width: calc(100% - 26px);
  background-color: purple;
}

input {
  background-color: blue;
  margin-right: 15px;
  padding: 0.71rem;
  margin-top: 5px;
}

fieldset {
  border: none;
}

select {
  display: flex;
  flex-direction: row;
  width: 80%;
  height: 39px;
  margin-top: 5px;
}

.reset-btn {
  width: 100%;
}

.confirm-btn {
  width: 100%;
}

@media (max-width: 734px) {
  .row {
    flex-direction: column;
  }
  .field {
    width: 100%;
  }
  .name {
    width: 100%;
    background-color: yellow;
    float: left;
  }
}
</style>
