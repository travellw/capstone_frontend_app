 <template>
   
   
   <div class="container">
     <button class="waves-effect waves-teal btn-flat" v-on:click="openForm()" >+</button>
     <button class="waves-effect waves-teal btn-flat" v-on:click="openForm()" >-</button>
     <button class="waves-effect waves-teal btn-flat" v-on:click="openForm()" >Key</button>
    <div>
      
      <div class='nav'>
      <button class="button-login">Dashboard</button>
      <button class="button-about">About</button>
      <button class="button-documentation">Documentation</button>
      <button class="button-support">Support</button>
      <button class="button-login">Logout</button>
      </div>
      
    <div class="google-toolbar">
    <ul>
    <li class="waves-effect waves-teal btn-flat" id="doc">
      <a href="https://docs.google.com/document/create" target="_blank">
        <img src="https://image.flaticon.com/icons/svg/300/300213.svg" width="32" height="32">
        <span class="label">
          New Document
        </span>
      </a>
    </li>
    <li class="waves-effect waves-teal btn-flat" id="sheet">
      <a href="https://docs.google.com/spreadsheet/ccc?new" target="_blank">
        <img src="https://image.flaticon.com/icons/svg/300/300232.svg" width="32" height="32">
        <span class="label">
          New Spreadsheet
        </span>
      </a>
    </li>
    <li class="waves-effect waves-teal btn-flat" id="prez">
      <a href="https://docs.google.com/presentation/create" target="_blank">
        <img src="https://image.flaticon.com/icons/svg/300/300233.svg" width="32" height="32">
        <span class="label">
          New Presentation
        </span>
      </a>
    </li>
    <li class="waves-effect waves-teal btn-flat" id="draw">
      <a href="https://docs.google.com/drawings/create?usp=drive_web" target="_blank">
        <img src="https://miro.medium.com/max/417/1*VEP0ecJ7cnjzHdPoiIs-ag.png" width="32" height="32">
        <span class="label">
          New Drawing
        </span>
      </a>
    </li>
    <li class="waves-effect waves-teal btn-flat" id="form">
      <a href="https://docs.google.com/forms/create" target="_new">
        <img src="https://image.flaticon.com/icons/svg/300/300231.svg" width="32" height="32">
        <span class="label">
          New Form
        </span>
      </a>
    </li>
  </ul>
  </div>
  <div id="status">
  </div>
  </div>
     

     <div class="wrapper">
    <div class="waitingTickets">
    <div class="waiting-box" v-for="ticket in waitingTickets" v-bind:key="ticket.id">
      <p>ID: {{ ticket.id }}</p>
      <p>TITLE: {{ ticket.title }}</p>
      <button class="waves-effect waves-light btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light btn" v-on:click="openupdateForm(ticket)">Update</button>
      <button class="waves-effect waves-light btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <div v-if= "ticket === currentTicket">
      <p>Status: {{ticket.status}} </p>
      <p>Created: {{ ticket.created }}</p>
      <p>Originator: {{ ticket.originator }}</p>
      <p>User: {{ ticket.user_id }}</p>
      <p>Issue: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
    </div>
    </div>  
  
  <div class="openTickets">
    <div class="open-box" id="some-div" draggable=true v-for="ticket in openTickets" v-bind:key="ticket.id">
      <p>ID: {{ ticket.id }}</p>
      <p>TITLE: {{ ticket.title }}</p>
      <button class="waves-effect waves-light btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light btn" v-on:click="openupdateForm(ticket)">Update</button>
      <button class="waves-effect waves-light btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <span id="some-element">
      <div v-if= "ticket === currentTicket">
      <p>Status: {{ticket.status}} </p>
      <p>Created: {{ ticket.created }}</p>
      <p>Originator: {{ ticket.originator }}</p>
      <p>User: {{ ticket.user_id }}</p>
      <p>Issue: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
      </span>
    </div>  
  </div>


  <div class="emergencyTickets"> 
    <div class="emergency-box" v-for="ticket in emergencyTickets" v-bind:key="ticket.id">
      <p>ID: {{ ticket.id }}</p>
      <p>TITLE: {{ ticket.title }}</p>
      <button class="waves-effect waves-light btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light btn" v-on:click="openupdateForm(ticket)">Update</button>
      <button class="waves-effect waves-light btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <div v-if= "ticket === currentTicket">
      <p>Status: {{ticket.status}} </p>
      <p>Created: {{ ticket.created }}</p>
      <p>Originator: {{ ticket.originator }}</p>
      <p>User: {{ ticket.user_id }}</p>
      <p>Issue: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
    </div> 
    </div> 

    

    <div class="pendingTickets">
    <div class="pending-box"  v-for="ticket in pendingTickets" v-bind:key="ticket.id">
      <p>ID: {{ ticket.id }}</p>
      <p>TITLE: {{ ticket.title }}</p>
      <button class="waves-effect waves-light btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light btn" v-on:click="openupdateForm(ticket)">Update</button>
      <button class="waves-effect waves-light btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <div v-if= "ticket === currentTicket">
      <p>Status: {{ticket.status}} </p>
      <p>Created: {{ ticket.created }}</p>
      <p>Originator: {{ ticket.originator }}</p>
      <p>User: {{ ticket.user_id }}</p>
      <p>Issue: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
    </div> 
    </div>
    </div>


<div class="form-popup" id="myForm">
  <div class="form-container">
    <h1></h1>
   
     Title: 
     <input type="text" v-model="newTicketTitle" />
     Originator: 
     <input type="text" v-model="newTicketOriginator" />
     User: 
     <input type="text" v-model="newTicketUser_ID" />
     Issue: 
     <input type="text" v-model="newTicketIssue" />
     Resolution: 
     <input type="text" v-model="newTicketResolution" />
     Status: 
    <p>
      <label>
        <input v-model="newTicketStatus" type="radio" value="open" />
        <span>Open</span>
      </label>
    </p>
    <p>
      <label>
        <input v-model="newTicketStatus" type="radio" value="pending" />
        <span>Pending</span>
      </label>
    </p>
    <p>
      <label>
        <input v-model="newTicketStatus" type="radio" value="waiting"  />
        <span>Waiting</span>
      </label>
    </p>
    <p>
      <label>
        <input v-model="newTicketStatus" type="radio" value="emergency" />
        <span>Emergency</span>
      </label>
    </p>
    <p>
      <label>
        <input v-model="newTicketStatus" type="radio" value="closed" />
        <span>Closed</span>
      </label>
    </p>
    <button class="waves-effect waves-light btn" v-on:click="createTicket()">Submit</button>
    <button type="button" class="btn cancel" v-on:click="closeForm()">Close</button>
  </div>
</div>

<div class="form-popup" id="myupdateForm">
  <div class="form-container">
    <h1></h1>
      ID:
      <input type="id" v-model="currentTicket.id" />
     Title: 
     <input type="text" v-model="currentTicket.title" />
     Originator: 
     <input type="text" v-model="currentTicket.originator" />
     User: 
     <input type="text" v-model="currentTicket.user_id" />
     Issue: 
     <input type="text" v-model="currentTicket.issue" />
     Resolution: 
     <input type="text" v-model="currentTicket.resolution" />
     Status: 
      <p>
      <label>
        <input v-model="currentTicket.status" type="radio" value="open" />
        <span>Open</span>
      </label>
    </p>
    <p>
      <label>
        <input v-model="currentTicket.status" type="radio" value="pending" />
        <span>Pending</span>
      </label>
    </p>
    <p>
      <label>
        <input v-model="currentTicket.status" type="radio" value="waiting"  />
        <span>Waiting</span>
      </label>
    </p>
    <p>
      <label>
        <input v-model="currentTicket.status" type="radio" value="emergency" />
        <span>Emergency</span>
      </label>
    </p>
    <p>
      <label>
        <input v-model="currentTicket.status" type="radio" value="closed" />
        <span>Closed</span>
      </label>
    </p>
     <!-- <input type="text" v-model="newTicketStatus" /> -->
    <button class="waves-effect waves-light btn" v-on:click="updateTicket(currentTicket)">Submit</button>
    <button type="button" class="btn cancel" v-on:click="closeupdateForm()">Close</button>
  </div>
</div>

</div>


</template>

<style>


.wrapper {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
}

.createBox{
  grid-column: 1;
  grid-row: 1;
  text-align: center;
}

.deleteBox{
  grid-column: 2;
  grid-row: 1;
  text-align: center;
}

.keyBox{
  grid-column: 3;
  grid-row: 1;
  text-align: center;
}

.waitingTickets {
  grid-column: 4;
  grid-row: 2;
  text-align: center;
}

.openTickets {
  grid-column: 1;
  grid-row: 2;
  text-align: center;
}

.pendingTickets {
  grid-column: 2;
  grid-row: 2;
  text-align: center;
}

.emergencyTickets {
  grid-column: 3;
  grid-row: 2;
  text-align: center;
}

.open-box {
  border: 2px solid lightgreen;
  font-size: 20px; 
  background-color: lightgreen;
  border-collapse: separate;
  border-spacing: 2px;
}

.some-element {
  border: 1px solid #ccc;
  display: none;
  font-size: 10px;
  margin-top: 10px;
  padding: 5px;
  text-transform: uppercase;
}

.some-div:hover #some-element {
  display: block;
}

.waiting-box {
  border: 10px solid lightyellow;
  font-size: 20px; 
  background-color: lightyellow;
}

.pending-box {
  border: 10px solid lightblue;
  font-size: 20px; 
  background-color: lightblue;
  opacity: 1px;
}

.emergency-box {
  border: 10px solid pink;
  font-size: 20px; 
  background-color: pink;
}

.text-wrapper {
  padding: 20px;
  position: Absolute;
  background-color: green;
  color: white;
}

.button {
  grid-column: 3;
  grid-row: 3;
  text-align: center;
}

/* The popup form - hidden by default */
.form-popup {
  display: none;
  position: fixed;
  bottom: 0;
  border: 3px solid #f1f1f1;
  z-index: 9;
  text-align: center;
}

/* Add styles to the form container */
.form-container {
  max-width: 500px;
  padding: 10px;
  background-color: white;
}

/* Full-width input fields */
.form-container input[type=text], .form-container input[type=password] {
  width: 100%;
  padding: 15px;
  margin: 5px 0 22px 0;
  border: none;
  background: #f1f1f1;
}

/* When the inputs get focus, do something */
.form-container input[type=text]:focus, .form-container input[type=password]:focus {
  background-color: #ddd;
  outline: none;
}

/* Set a style for the submit/login button */
.form-container .btn {
  background-color: #4CAF50;
  color: white;
  padding: 16px 20px;
  border: none;
  cursor: pointer;
  width: 100%;
  margin-bottom:10px;
  opacity: 0.8;
}

/* Add a red background color to the cancel button */
.form-container .cancel {
  background-color: red;
}

/* Add some hover effects to buttons */
.form-container .btn:hover, .open-button:hover {
  opacity: 1;
}

.button-login {
  background-color: pink; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 30px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

.button-logout {
  background-color: pink; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 30px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

.button-about {
  background-color: blue; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

.button-documentation {
  background-color: green; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}

.button-support {
  background-color: yellow; /* Green */
  display: block;
  border: none;
  color: black;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
  display: inline-block;
  font-size: 16px;
  opacity: .75;
}





</style>


<script>




 

var axios = require("axios");


export default {
  data: function() {
    return {
      message: "This is Travell's Capstone",
      tickets: [],
      newTicketID: "",
      currentTicket: {},
      newTicketTitle: "",
      newTicketIssue: "",
      newTicketCreated: "",
      newTicketOriginator: "",
      newTicketUser_ID: "",
      newTicketResolution: "",
      newTicketStatus: "", 
    };
  },
  created: function() {
    axios.get("/api/tickets").then(response => {
      this.tickets = response.data;
      console.log("The tickets:", this.tickets);
    });
  },

  methods: {
    
    openForm: function(){
      document.getElementById("myForm").style.display = "block";
    },
    
    closeForm: function(){
      document.getElementById("myForm").style.display = "none";
    },

    openupdateForm: function(ticket){
      this.currentTicket = ticket
      document.getElementById("myupdateForm").style.display = "block";
    },
    
    closeupdateForm: function(){
      document.getElementById("myupdateForm").style.display = "none";
    },


    createTicket: function() {
      var params = {
        title: this.newTicketTitle,
        issue: this.newTicketIssue,
        created: this.newTicketCreated,
        originator: this.newTicketOriginator,
        user_id: this.newTicketUser_ID,
        resolution: this.newTicketResolution,
        status: this.newTicketStatus,
      }; 
      axios.post("/api/tickets", params).then(response => {
        console.log("It Worked.", response.data);
        this.tickets.push(response.data);
        this.closeForm()

      }).catch(error=>console.log(error.response))
    },
    showTicket: function(ticket) {
      if (this.currentTicket === ticket) {
        this.currentTicket = {};
      } else {
        this.currentTicket = ticket;
      }
    },
    updateTicket: function(ticket) {
      var params = {
        id: ticket.id,
        title: ticket.title,
        issue: ticket.issue,
        created: ticket.created,
        originator: ticket.originator,
        user_id: ticket.user_id,
        resolution: ticket.resolution,
        status: ticket.status
    };
    axios.patch("/api/tickets/" + ticket.id, params).then(response => {
      console.log("It Worked.", response.data);
      this.currentTicket = {};
      this.closeupdateForm()
      });
    },
    destroyTicket: function(ticket) {
      axios.delete("/api/tickets/" + ticket.id).then(response => {
        console.log("It Worked.", response.data);
        var index = this.tickets.indexOf(ticket);
        console.log(index)
        this.tickets.splice(index, 1);
      });
    },
  },
  computed: {
    openTickets: function() {
      return this.tickets.filter(ticket => ticket.status.toLowerCase( ) === "open")
    },
    
    waitingTickets: function() {
      return this.tickets.filter(ticket => ticket.status.toLowerCase( ) === "waiting")
    },

    pendingTickets: function() {
      return this.tickets.filter(ticket => ticket.status.toLowerCase( ) === "pending")
    },
    emergencyTickets: function() {
      return this.tickets.filter(ticket => ticket.status.toLowerCase( ) === "emergency")
    },    
  }
};
</script>

