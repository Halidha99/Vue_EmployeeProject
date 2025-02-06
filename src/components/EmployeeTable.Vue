<template>
      <div id="employee-table">
        <table>
            <thead>
                <tr>
                    <th>Employee Name</th>
                    <th>Employee Email</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="employee in employees" :key="employee.id">
                    <td>{{employee.name}}</td>
                    <td>{{employee.email}}</td>
                    <td>
                    <button>Edit</button>
                    <button @click="$emit('delete:employee',employee.id)">Delete</button>
                </td>
                </tr>
                
                
            </tbody>
        </table>
    </div>
</template>

<script>
export default {
    name: 'employee-tables',
    // data format
    props:{
       employees: Array
    }
}
</script>

<style>
button{
    margin: 0 0.5rem 0 0;
}

</style>
