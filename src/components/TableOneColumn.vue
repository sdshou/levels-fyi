<template>
  <div class="TableOneColumn">
    <el-button round @click="$emit('del-company', companyName)">{{companyName}}</el-button>
    <div>
      <table>
        <tr width="180" v-for="(level, index) in companyDetails" :key="index">
          <td v-for="(title, index) in level.titles" :key="index">{{title}}</td>
          <td v-if="level.packages !== undefined">{{level.packages[0].salary}}</td>
          <td v-if="level.packages !== undefined">{{level.packages[0].bonus}}</td>
          <td v-if="level.packages !== undefined">{{level.packages[0].stock}}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TableOneColumn',
  props: ['companyDetails', 'companyName'],
  data () {
    return {
    }
  }
}
</script>
console.log('yes', this.companyDetails)
<style scoped>
table {  
    color: #333;
    font-family: Helvetica, Arial, sans-serif;
    font-size: 12px;
    width: 300px; 
    border-collapse: 
    collapse; border-spacing: 0; 
}
td, th {  
    border: 1px solid transparent; /* No more visible border */
    height: 30px; 
    transition: all 0.3s;  /* Simple transition for hover effect */
}

th {  
    background: #DFDFDF;  /* Darken header a bit */
    font-weight: bold;
}

td {  
    background: #FAFAFA;
    text-align: center;
}

/* Cells in even rows (2,4,6...) are one color */        
tr:nth-child(even) td { background: #F1F1F1; }   

/* Cells in odd rows (1,3,5...) are another (excludes header cells)  */        
tr:nth-child(odd) td { background: #FEFEFE; }  

tr td:hover { background: #666; color: #FFF; }  
</style>
