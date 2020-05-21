 <template class="background">
   
   <div class="container">
    <div>
  
      
   
     

     <div class="wrapper">
    <div class="waitingTickets">
       <div>Waiting Tickets</div>
    <div class="waiting-box" v-for="ticket in waitingTickets" v-bind:key="ticket.id">
      <p>ID: {{ ticket.id }}</p>
      <p>TITLE: {{ ticket.title }}</p>
      <button class="waves-effect waves-light orange lighten-4 btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light orange lighten-4 btn" v-on:click="openupdateForm(ticket)">Update</button>
      <button class="waves-effect waves-light orange lighten-4 btn" v-on:click="destroyTicket(ticket)">Delete</button>  
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
     <div>Open Tickets</div>
    <div class="open-box" id="some-div" draggable=true v-for="ticket in openTickets" v-bind:key="ticket.id">
      <p>ID: {{ ticket.id }}</p>
      <p>TITLE: {{ ticket.title }}</p>
      <button class="waves-effect waves-light deep-orange lighten-5 btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light deep-orange lighten-5 btn" v-on:click="openupdateForm(ticket)">Update</button>
      <button class="waves-effect waves-light deep-orange lighten-5 btn" v-on:click="destroyTicket(ticket)">Delete</button>  
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
    <div>Emergency Tickets</div>
    <div class="emergency-box" v-for="ticket in emergencyTickets" v-bind:key="ticket.id">
      <p>ID: {{ ticket.id }}</p>
      <p>TITLE: {{ ticket.title }}</p>
      <button class="waves-effect waves-light brown btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light brown btn" v-on:click="openupdateForm(ticket)">Update</button>
      <button class="waves-effect waves-light brown btn" v-on:click="destroyTicket(ticket)">Delete</button>  
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
       <div>Pending Tickets</div>
    <div class="pending-box"  v-for="ticket in pendingTickets" v-bind:key="ticket.id">
      <p>ID: {{ ticket.id }}</p>
      <p>TITLE: {{ ticket.title }}</p>
      <button class="waves-effect waves-light deep-orange lighten-4 btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light deep-orange lighten-4 btn" v-on:click="openupdateForm(ticket)">Update</button>
      <button class="waves-effect waves-light deep-orange lighten-4 btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <div v-if= "ticket === currentTicket">
      <p>Status: {{ticket.status}} </p>
      <!-- <p>Created: {{ ticket.created }}</p> -->
      <p>Originator: {{ ticket.originator }}</p>
      <!-- <p>User: {{ ticket.user_id }}</p> -->
      <p>Issue: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
    </div> 
    </div>
    </div>

 <div class="nav">
    <ul>
    <li class="new-ticket" id="doc">
        <img src="https://png2.cleanpng.com/sh/902291eef34d49b71342bc4c0f51dcf7/L0KzQYm3VsIyN6tBepH0aYP2gLBuTcIxOWkyfNH0b33sPbT2jgB2fJZ3Rdtsb372PcXwgBtmfF5rgd52LXnmf7A0hPV0cZhzRadrMnLmQYXoWcJnO5QARqY9M0K3QYWCUcUzQWYATKMDNkazQYq1kP5o/kisspng-2018-dokomi-computer-icons-ticket-film-icon-design-5b2bc14a92f3c9.4432414915295941866019.png" width="32" height="32">
    <span class="label" v-on:click="openForm()" >New Ticket</span>
    </li>
    <li class="new-ticket" id="doc">
      <a href="https://docs.google.com/document/create" target="_blank">
        <img src="https://image.flaticon.com/icons/svg/300/300213.svg" width="32" height="32">
        <span class="label">
          New Document
        </span>
      </a>
    </li>
    <li class="new-ticket" id="sheet">
      <a href="https://docs.google.com/spreadsheet/ccc?new" target="_blank">
        <img src="https://image.flaticon.com/icons/svg/300/300232.svg" width="32" height="32">
        <span class="label">
          New Spreadsheet
        </span>
      </a>
    </li>
    <li class="new-ticket" id="prez">
      <a href="https://docs.google.com/presentation/create" target="_blank">
        <img src="https://image.flaticon.com/icons/svg/300/300233.svg" width="32" height="32">
        <span class="label">
          New Presentation
        </span>
      </a>
    </li>
    <li class="new-ticket" id="draw">
      <a href="https://docs.google.com/drawings/create?usp=drive_web" target="_blank">
        <img src="https://miro.medium.com/max/417/1*VEP0ecJ7cnjzHdPoiIs-ag.png" width="32" height="32">
        <span class="label">
          New Drawing
        </span>
      </a>
    </li>
    <li class="new-ticket" id="form">
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

<div class="form-popup" id="myForm">
  <div class="form-container">
    <h1></h1>
   
     Title: 
     <input type="text" v-model="newTicketTitle" />
     Originator: 
     <input type="text" v-model="newTicketOriginator" />
     <!-- User: 
     <input type="text" v-model="newTicketUser_ID" /> -->
     Issue: 
     <input type="text" v-model="newTicketIssue" />
     Resolution: 
     <input type="text" v-model="newTicketResolution" />
     Attachments:
    <div class="file-field input-field">
      <div class="btn">
        <span>File</span>
        <input type="file">
      </div>
      <div class="file-path-wrapper">
        <input class="file-path validate" type="text">
      </div>
    </div>
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
    <button class="waves-effect waves-light blue-grey btn-small" v-on:click="createTicket()">Submit</button>
    <button class="waves-effect waves-light blue-grey btn-small" v-on:click="closeForm()">Close</button>
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
     <!-- User: 
     <input type="text" v-model="currentTicket.user_id" /> -->
     Issue: 
     <input type="text" v-model="currentTicket.issue" />
     Resolution: 
     <input type="text" v-model="currentTicket.resolution" />
     Attachments:
    <div class="file-field input-field">
      <div class="btn">
        <span>File</span>
        <input type="file">
      </div>
      <div class="file-path-wrapper">
        <input class="file-path validate" type="text">
      </div>
    </div>
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
    <button class="waves-effect waves-light blue-grey btn-small" v-on:click="updateTicket(currentTicket)">Submit</button>
    <button class="waves-effect waves-light blue-grey btn-small" v-on:click="closeupdateForm()">Close</button>
  </div>
</div>

</div>


</template>

<style>


.wrapper {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
  color: black
}


.nav {
  text-align: center;
}

.background {
  background-color: white;
  font-family: 'Roboto Mono', monospace;
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
  margin-top: 2%;
  margin-bottom: 2%;
  font-family: 'Roboto Mono', monospace;
}

.openTickets {
  grid-column: 1;
  grid-row: 2;
  text-align: center;
  margin-top: 2%;
  margin-bottom: 2%;
  font-family: 'Roboto Mono', monospace;
}

.pendingTickets {
  grid-column: 2;
  grid-row: 2;
  text-align: center;
  margin-top: 2%;
  margin-bottom: 2%;
  font-family: 'Roboto Mono', monospace;
}

.emergencyTickets {
  grid-column: 3;
  grid-row: 2;
  text-align: center;
  margin-top: 2%;
  margin-bottom: 2%;
  font-family: 'Roboto Mono', monospace;
}

.open-box {
  border: 2px solid #eee4e1ff;
  font-size: 20px; 
  background-color: #eee4e1ff;
  border-collapse: separate;
  border-spacing: 2px;
  margin-top: 2%;
  margin-bottom: 2%;
  color: black;
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
  border: 10px solid #ffe0b2;
  font-size: 20px; 
  background-color: #ffe0b2;
  margin-top: 2%;
  margin-bottom: 2%;
}

.pending-box {
  border: 10px solid #e6beaeff;
  font-size: 20px; 
  background-color: #e6beaeff;
  opacity: 1px;
  margin-top: 2%;
  margin-bottom: 2%;
  color: black;
}

.emergency-box {
  border: 10px solid #b2967dff;
  font-size: 20px; 
  background-color: #b2967dff;
  margin-top: 2%;
  margin-bottom: 2%;
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
  color: black;
}

.new-ticket {
  background-color: #b0bec5; /* Green */
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

.new-word {
  background-color: yellow; /* Green */
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
  background-color: gray; /* Green */
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
  background-color: gray; /* Green */
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
  background-color: gray; /* Green */
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
  background-color: gray; /* Green */
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
  background-color: gray; /* Green */
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
        setFile: function(event) {
      if (event.target.files.length > 0) {
        this.image = event.target.files[0];
      }
    },

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

