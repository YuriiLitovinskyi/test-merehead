<template>
  <div class="home">
    <h2>Users</h2>
    <table align="center">
    	<tr>
    		<th>ID</th>
    		<th>Name</th>
    		<th>Surname</th>
    		<th>Description</th>
    	</tr>
    	<tr v-bind:key="user.id" v-for="user in usersPerPage">
    		<td>{{ user.id }}</td>
    		<td>{{ user.name }}</td>
    		<td>{{ user.surname }}</td>
    		<td>{{ user.desc }}</td>
    	</tr>
    </table>
    <div>
    	<button v-bind:key="page" v-for="page in this.pagination.pages" v-on:click.prevent=setPage(page)>{{ page }}</button>
    </div>
    
  </div>
</template>


<script>

export default {
  name: 'home',
  components: {
    
  },
  computed: {
  	users() {
  		return this.$store.state.users;  		
  	},
    numberOfItems() {
      return this.$store.state.numberOfItems;
    },
    pagination() {
      return this.$store.state.pagination;
    },
  	usersPerPage() {
  		return this.paginate(this.users);
  	}  	
  },
  methods: {
  	setPage(page) {
  		this.$store.commit('SetPagination', this.paginator(this.users.length, page));   
  	},
  	paginate(data) {
  		return data.slice(this.pagination.startIndex, this.pagination.endIndex + 1);
  	},
  	paginator(numberOfUsers, currentPage) {
  		let startIndex = (currentPage - 1) * this.numberOfItems;
  		let endIndex = startIndex + this.numberOfItems - 1;
  		return {
  			currentPage,
  			startIndex,
  			endIndex,  			
  			pages: Array.from(new Array(Math.ceil(numberOfUsers / this.numberOfItems)), (x,i) => i+1)
  		}
  	}
  },
  created() {
  	this.setPage(1);
  }
}
</script>
