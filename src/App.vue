<template>
  <div class="small-container">
    <h1>Employees</h1>
    <employee-form @add:employee="addEmployee" />
    <employee-table v-bind:employees="employees" @delete:employee="deleteEmployee" />
    
  </div>
 
</template>

<script>
import EmployeeTable from "./components/EmployeeTable.vue";  // ✅ Exact match
import EmployeeForm from "./components/EmployeeForm.vue";

export default {
  name: 'App',
  components: {
    EmployeeTable,
    EmployeeForm
   
  }, 

  data(){
    return{
      employees:[
        {
          id:1,
          name:'Kamala',
          email:'kamala99@gmail.com'
        },
        {
          id:2,
          name:'Danushka ',
          email:'danushka20@gmail.com'
        },
        {
          id:3,
          name:'Fathima Halidha',
          email:'halidha@gmail.com'
        }
      ]
    }
  },
  methods:{
    addEmployee(employee){
      // function parameter

      const lastId= this.employees.length>0?this.employees[this.employees.length-1].id:0;
     
     const id = lastId+1;

    const newEmployee={...employee,id};

     this.employees =[...this.employees,newEmployee];
      
    }
  }
}
</script>

<style>

button{
  background-color: #009435;
  border: 1px solid #009435;
}

.small-container{
  max-width: 680px;
}

</style>
