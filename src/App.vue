<template>
  <body>
    <form>
      <div class="row">
        <div class="field">
          <label for="first-name">First Name</label>
          <input type="text" id="first-Name" />
        </div>
        <div class="field">
          <label for="last-name">Last Name</label>
          <input type="text" id="last-name" />
        </div>
      </div>
      <div class="row">
        <div class="field">
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

<style scoped></style>
