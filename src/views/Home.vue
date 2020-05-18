 <template>
   
   
   <div class="container">
     <button class="waves-effect waves-light btn" v-on:click="openForm()" >+</button>
     <div><ul class="btns">
    <li id="doc">
      <a href="https://docs.google.com/document/create" target="_blank">
        <img src="docs-32.png" width="32" height="32">
        <span class="label">
          New Document
        </span>
      </a>
    </li>
    <li id="sheet">
      <a href="https://docs.google.com/spreadsheet/ccc?new" target="_blank">
        <img src="spreadsheets-32.png" width="32" height="32">
        <span class="label">
          New Spreadsheet
        </span>
      </a>
    </li>
    <li id="prez">
      <a href="https://docs.google.com/presentation/create" target="_blank">
        <img src="presentations-32.png" width="32" height="32">
        <span class="label">
          New Presentation
        </span>
      </a>
    </li>
    <li id="draw">
      <a href="https://docs.google.com/drawings/create?usp=drive_web" target="_blank">
        <img src="drawings-32.png" width="32" height="32">
        <span class="label">
          New Drawing
        </span>
      </a>
    </li>
    <li id="form">
      <a href="https://docs.google.com/forms/create" target="_new">
        <img src="forms-32.png" width="32" height="32">
        <span class="label">
          New Form
        </span>
      </a>
    </li>
  </ul>
  <div id="status">
  </div>
  </div>
     
     <div class="wrapper">
    <div class="waitingTickets">
    <h1> Waiting Tickets</h1>
    <div v-for="ticket in waitingTickets" v-bind:key="ticket.id">
      <h2>Id: {{ ticket.id }}</h2>
      <h3>Title: {{ ticket.title }}</h3>
      <p>Status: {{ticket.status}} </p>
      <button class="waves-effect waves-light btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light btn" v-on:click="updateTicket(ticket)">Update</button>
      <button class="waves-effect waves-light btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <div v-if= "ticket === currentTicket">
      <p>Created: {{ ticket.created }}</p>
      <p>Originator: {{ ticket.originator }}</p>
      <p>User: {{ ticket.user_id }}</p>
      <p>User: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
    </div>
    </div>  
  
  <div class="openTickets">
  <h1> Open Tickets</h1>
    <div  v-for="ticket in openTickets" v-bind:key="ticket.id">
      <h2>Id: {{ ticket.id }}</h2>
      <h3>Title: {{ ticket.title }}</h3>
      <p>Status: {{ticket.status}} </p>
      <button class="waves-effect waves-light btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light btn" v-on:click="updateTicket(ticket)">Update</button>
      <button class="waves-effect waves-light btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <div v-if= "ticket === currentTicket">
      <p>Created: {{ ticket.created }}</p>
      <p>Originator: {{ ticket.originator }}</p>
      <p>User: {{ ticket.user_id }}</p>
      <p>User: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
    </div>  
  </div>


  <div class="emergencyTickets"> 
  <h1> Emergency Tickets</h1>
    <div  v-for="ticket in emergencyTickets" v-bind:key="ticket.id">
      <h2>Id: {{ ticket.id }}</h2>
      <h3>Title: {{ ticket.title }}</h3>
      <button class="waves-effect waves-light btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light btn" v-on:click="updateTicket(ticket)">Update</button>
      <button class="waves-effect waves-light btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <div v-if= "ticket === currentTicket">
      <p>Status: {{ticket.status}} </p>
      <p>Created: {{ ticket.created }}</p>
      <p>Originator: {{ ticket.originator }}</p>
      <p>User: {{ ticket.user_id }}</p>
      <p>User: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
    </div> 
    </div> 

    

    <div class="pendingTickets">
      <h1> Pending Tickets</h1>
    <div  v-for="ticket in pendingTickets" v-bind:key="ticket.id">
      <h2>Id: {{ ticket.id }}</h2>
      <h3>Title: {{ ticket.title }}</h3>
      <button class="waves-effect waves-light btn" v-on:click="showTicket(ticket)">Expand</button>
      <button class="waves-effect waves-light btn" v-on:click="updateTicket(ticket)">Update</button>
      <button class="waves-effect waves-light btn" v-on:click="destroyTicket(ticket)">Delete</button>  
      <div v-if= "ticket === currentTicket">
      <p>Status: {{ticket.status}} </p>
      <p>Created: {{ ticket.created }}</p>
      <p>Originator: {{ ticket.originator }}</p>
      <p>User: {{ ticket.user_id }}</p>
      <p>User: {{ ticket.issue }}</p>
      <p>Resolution: {{ ticket.resolution }}</p>
      <p>Status: {{ ticket.status }}</p>
      </div>
    </div> 
    </div>
    </div>

   

<div class="form-popup" id="myForm">
  <form action="/action_page.php" class="form-container">
    <h1></h1>
    <form>
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
     <input type="text" v-model="newTicketStatus" />
    <button class="waves-effect waves-light btn" v-on:click="createTicket()">Submit</button>
     </form>
    <button type="button" class="btn cancel" v-on:click="closeForm()">Close</button>
  </form>
</div>




  </div>


</template>

<style>


.wrapper {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-gap: 10px;
}

.waitingTickets {
  grid-column: 3;
  grid-row: 1;
}

.openTickets {
  grid-column: 1;
  grid-row: 1;
}

.pendingTickets {
  grid-column: 2;
  grid-row: 1;
}

.emergencyTickets {
  grid-column: 4;
  grid-row: 1;
}


.container {
  font-family: 'DM Mono', monospace;  
}



.button {
  background-color: red;
  border: 1px solid rgba(255, 255, 255, .3);
  width: 200px;
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition: all .05s;
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
      return this.tickets.filter(ticket => ticket.status.toLowerCase( ) === "closed")
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

