<template>
  <div class="container">
    <div class="row">
      <div class="col-md-12">
        <div class="table-responsive">

          <table class="table">
            <thead class="thead-dark">
              <tr>
                <th scope="col">ID</th>
                <th scope="col">Nombre</th>
                <th scope="col">Precio</th>
                <th scope="col">Stock</th>
                <th scope="col">Imagen</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="item in items" v-bind:key="item.id">
                <th scope="row">{{ item.id }}</th>
                <td>{{ item.nombre }}</td>
                <td>{{ item.precio }}</td>
                <td>{{ item.stock }}</td>
                <td><img v-bind:src="'img/' + item.img" class="img-fluid" width="30px" v-bind:alt="item.nombre"></td>
              </tr>
            </tbody>
          </table>

        </div>
      </div>
    </div>
  </div>
</template>

<script>

// Archivo de datos 'postres.json' 
import datos from "../assets/json/postres.json";
  
  export default {
    name: 'Datos',
    
    // Creo un método llamado 'items' y obtengo los datos con el método map() 
    computed: {
      items() {
        return datos.map((item) => {
          return item;
        })
      }
    }
  }

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  /* Estilos */
</style>
