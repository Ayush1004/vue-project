<template>
  <form @submit.prevent="submitForm">
    <label>Enter Employee ID: </label>
    <input id="eid" v-model="Employee.eid" /> <br />
    <label>Enter Employee Name: </label>
    <input id="name" v-model="Employee.name" /> <br />
    <label>Enter Employee Address: </label>
    <textarea id="address" v-model="Employee.address" /> <br />
    <label>Gender: </label> <br />
    <input type="radio" v-model="Employee.gender" :value="1" />
    <label>Male</label>
    <input type="radio" v-model="Employee.gender" :value="0" />
    <label>Female</label> <br />
    <label>Date Of Joining: </label>
    <input type="date" id="date" v-model="Employee.doj" /> <br />
    <label>Hobbies: </label> <br />
    <input type="checkbox" v-model="Employee.hobbies.cricket" />
    <label>Cricket</label> <br />
    <input type="checkbox" v-model="Employee.hobbies.music" />
    <label>Music</label> <br />
    <button class="button" type="submit">Submit</button>
  </form>
  <table v-if="Employees.length">
    <tr v-for="emp in Employees">
      <td>{{ emp.name }}</td>
      <td>{{ emp.eid }}</td>
      <td>{{ emp.address }}</td>
      <td v-if="emp.gender">Male</td>
      <td v-else>Female</td>
      <td>{{ emp.doj }}</td>
      <td v-if="emp.hobbies.cricket && emp.hobbies.music">Cricket and Music</td>
      <td v-else-if="emp.hobbies.cricket">Cricket</td>
      <td v-else-if="emp.hobbies.music">Music</td>
      <td v-else>None</td>
    </tr>
  </table>
  <br />
  <br />
  <br />
  <table v-if="Employees.length">
    <div v-for="emp in Employees">
      <tr v-if="datec(emp)">
        <td>{{ emp.name }}</td>
        <td>{{ emp.eid }}</td>
        <td>{{ emp.address }}</td>
        <td v-if="emp.gender">Male</td>
        <td v-else>Female</td>
        <td>{{ emp.doj }}</td>
        <td v-if="emp.hobbies.cricket && emp.hobbies.music">Cricket and Music</td>
        <td v-else-if="emp.hobbies.cricket">Cricket</td>
        <td v-else-if="emp.hobbies.music">Music</td>
        <td v-else>None</td>
      </tr>
    </div>
  </table>
</template>
<script>
export default {
  data() {
    date: null;
    month: null;
    return {
      Employee: {
        name: "",
        eid: "",
        address: "",
        gender: null,
        doj: null,
        hobbies: {
          cricket: false,
          music: false,
        },
      },
      Employees: [],
    };
  },
  /*
  methods: {
    submitForm() {
      //console.log(this.Employee.doj);
      let emp = {
        name: this.Employee.name,
        eid: this.Employee.eid,
        address: this.Employee.address,
        gender: this.Employee.gender,
        doj: this.Employee.doj,
        hobbies: {
          cricket: this.Employee.hobbies.cricket,
          music: this.Employee.hobbies.music,
        },
      };
      this.Employees.push(emp);
      this.Employee.name = "";
      this.Employee.address = "";
      this.Employee.eid = "";
      this.Employee.gender = null;
      this.Employee.doj = null;
      this.Employee.hobbies.cricket = false;
      this.Employee.hobbies.music = false;
      if (localStorage.getItem("data")) {
        this.data = JSON.parse(localStorage.getItem("data"));
        console.log(this.data);
        this.data.push(emp);
        //console.log("data");
        //console.log(emp);
        localStorage.setItem("data", JSON.stringify(this.data));
      } else {
        localStorage.setItem("data", JSON.stringify(this.Employees));
      }
    },
  },*/
  mounted() {
    if (localStorage.getItem("data")) {
      try {
        this.Employees = JSON.parse(localStorage.getItem("data"));
      } catch (e) {
        localStorage.removeItem("data");
      }
    }
  },
  methods: {
    submitForm() {
      this.date = new Date();
      this.date = this.date.getMonth() + 1;
      this.month = parseInt(this.Employee.doj.substring(5, 7));
      console.log(this.date);
      console.log(this.month);
      let emp = {
        name: this.Employee.name,
        eid: this.Employee.eid,
        address: this.Employee.address,
        gender: this.Employee.gender,
        doj: this.Employee.doj,
        hobbies: {
          cricket: this.Employee.hobbies.cricket,
          music: this.Employee.hobbies.music,
        },
      };
      this.Employees.push(emp);
      this.Employee.name = "";
      this.Employee.address = "";
      this.Employee.eid = "";
      this.Employee.gender = null;
      this.Employee.doj = null;
      this.Employee.hobbies.cricket = false;
      this.Employee.hobbies.music = false;
      localStorage.setItem("data", JSON.stringify(this.Employees));
    },
    datec(emp) {
      this.date = new Date();
      this.date = this.date.getMonth() + 1;
      this.month = parseInt(emp.doj.substring(5, 7));
      if (this.month === this.date) {
        return true;
      }
      return false;
    },
  },
  /*computed: {
    DateOfJoin() {
      let filt = [];
      for (let emp in this.Employees) {
        if (emp.doj) {
          const date = new Date();
          console.log(emp.doj);
          const m = emp.doj.substring(5, 7);
          console.log(m);
          if (m == date.getMonth() + 1) {
            filt.push(emp);
          }
        }
      }
      return filt;
    },
  },*/
};
</script>
