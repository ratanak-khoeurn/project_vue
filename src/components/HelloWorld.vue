<template>
  <div class="container">
    <h1>Booking Ticket Form</h1>
    <div class="table mb-3">
      <hr>
      <table class="ticket">
        <thead>
          <tr>
            <th scope="col">#</th>
            <th scope="col">Name</th>
            <th scope="col">Price</th>
            <th scope="col">Quantity</th>
            <th scope="col">Total Price</th>
          </tr>
        </thead>
        <tbody>
            <tr v-for="(ticket,index) in tickets" :key="ticket">
              <th scope="row">{{ index +1 }}</th>
              <td>{{ ticket.name }}</td>
              <td>{{ ticket.price }}</td>
              <td>{{ ticket.quantity }}</td>
              <td>{{ ticket.totalPrice }}</td>
            </tr>
       
        </tbody>
      </table>
    </div>
    <hr>
    <div class="form">
      <div class="firstName mb-3">
        <input class="form-control" type="text" id="fname" placeholder="First Name" v-model="firstName"/>
      </div>
      <div class="lastName mb-3">
        <input class="form-control" type="text" id="lname" placeholder="Last Name" v-model="lastName"/>
      </div>
      <div class="email mb-3">
        <input class="form-control" type="text" id="email" placeholder="Email" v-model="email"/>
      </div>
      <div class="age mb-3">
        <input class="form-control" type="number" id="age" placeholder="Age" v-model="age"/>
      </div>
      <div class="password mb-3">
        <input class="form-control" type="password" id="pass" placeholder="Password" v-model="password"/>
      </div>
      <div class="ticketNumber mb-3" v-if="showTicketNumberInput">
        <input class="form-control" type="number" id="ticketNumber" placeholder="Ticket Number" v-model="ticketNumber"/>
      </div>
    </div>
    <div class="allInfo card mb-3">
      <img src="../assets/logo.png " alt="profile" style="width: 100px; border-radius: 100%; border: 1px solid green;margin-left: 46%; margin-top: 10px;margin-bottom: 10px;">
      <div class="information">
        <p>{{fullName}}</p>
        <p>{{email}}</p>
        <p>{{age}}</p>
        <p>{{password}}</p>
        <p>{{ticketNumber}}</p>
      </div>
    </div>
    <button class="btn btn-primary mb-3" @click="submit">Submit</button>
  </div>
</template>

<script>
export default {
  name: "BookingTicketForm",
  methods: {
    submit() {
      confirm("Are you sure you want to book this ticket");
    },
  },
  data() {
    return {
      firstName: "",
      lastName: "",
      email: "",
      age: "",
      password: "",
      tickets: [ // Array to hold ticket information
        { name: "Ticket 1", price: "100$", quantity: 1, totalPrice: "100$" },
        { name: "Ticket 2", price: "100$", quantity: 1, totalPrice: "100$" },
        { name: "Ticket 3", price: "100$", quantity: 1, totalPrice: "100$" }
      ],
    };
  },
  computed:{
    fullName(){
      return this.firstName + " " + this.lastName;
    },
    getemail(){
      return this.firstName + this.lastName + "@gmail.com";
    },
    getAge(){
      return this.age;
    },
    getPassword(){
      return this.password;
    },
    getTicketNumber(){
      return this.ticketNumber;
    },

  }

};
</script>
