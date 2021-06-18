<template>
  <q-page padding class="container">
    <header><h2>Usuários</h2></header>
    <div class="row q-gutter-lg">
    	<div class="col col-md-2" v-for="usuario in usuarios" :key="usuario.id">
    		<q-card class="p-pa-md">
		      	<q-card-section>
		      		<q-item-section avatar>
		      			<q-avatar>
		      				<img src="https://cdn.quasar.dev/img/avatar2.jpg">
		      			</q-avatar>
		      		</q-item-section>
		        	<div class="text-h6 text-indigo-9">{{ usuario.name }}</div>
		        	<div class="tex-subtitle2">{{ usuario.email }}</div>
		     	</q-card-section>
		     	<q-separator insert />
		      	<q-card-section class="q-pt-none">
		      		<p class="text-h6">Endereço</p>
		      		<p>{{ usuario.address.street }}, {{ usuario.address.suite }}, <br/>{{ usuario.address.city }}</p>
		      	</q-card-section>
		    </q-card>
    	</div> <!-- /.col -->
    </div> <!-- /.row -->
  </q-page>
</template>

<script>
export default {
  name: 'Usuarios',
  data(){
  	return{
  		usuarios: []
  	}
  },
  methods: {
  	viewUsuarios (){
  		this.$axios.get('https://jsonplaceholder.typicode.com/users').then(response=>{
  			this.usuarios = response.data
  		})
  	}
  },
  beforeMount () {
  	this.viewUsuarios()
  }
}
</script>
