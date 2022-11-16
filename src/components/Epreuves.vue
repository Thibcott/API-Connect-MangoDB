<script>
  import axios from 'axios';
  export default {
    name: 'Epreuves',
    data() {
      return {
        epreuves: null,
      };
    },
    created: function() {
      axios
        .get('http://localhost:3000/')
        .then(res => {
          this.epreuves = res.data;
          console.log(res.data)
        })
    }
  }
</script>
<template>
    <div class="container">
      <h3>Epreuves :  <input type="text"> </h3>
     
      <table class="table">
        <thead>
          <tr>
            <!-- <th scope="col">Id</th> -->
            <th scope="col">Branche</th>
            <th scope="col">Nom de l'epreuve</th>
            <th scope="col">Date</th>
            <th scope="col">Note</th>
            <th scope="col">Nom</th>
            <th scope="col">Prenom</th>
            <th scope="col">Visa</th>
            <th scope="col">Prof</th>
            <th scope="col">Classe</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="epreuve in epreuves" v-bind:key="epreuve._id"> 
            <td>{{epreuve.branche}}</td>
            <td>{{epreuve.examen}}</td>
            <td>{{epreuve.date}}</td>
            <td>{{epreuve.note}}</td>
            <td>{{epreuve.nom.toUpperCase()}}</td>
            <td>{{epreuve.prenom}}</td>
            <td>{{epreuve.visa.toUpperCase()}}</td>
            <td>{{epreuve.prof.toUpperCase()}}</td>
            <td>{{epreuve.classe}}</td>            
          </tr>
        </tbody>
      </table> 
    </div> 
</template>
<style>
table {
  font-family: Arial, Helvetica, sans-serif;
  border-collapse: collapse;
  width: 100%;
}

table td,  th {
  border: 1px solid #ddd;
  padding: 8px;
  text-align: left;
}

table tr:nth-child(even){background-color: #f2f2f2;}
table tr:nth-child(odd){background-color: white;}

table tr:hover {background-color: #ddd;}

table th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #04AA6D;
  color: white;
}
.container{
  text-align:left;
  background-color: rgb(229, 245, 199);
  border-radius: 10px;
  padding: 10px;
  margin-top:10px;
}
</style>