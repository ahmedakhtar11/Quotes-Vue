<template>
  <div id="http">
    <h1>Quotes App - Vue.js</h1>
   
    <b-form-input  type="text" v-model="search" placeholder="search quotes"></b-form-input>
    
    <!-- All Quotes -->
    <div id = "AllQuotes">
      <div class="overflow-auto">
        <b-pagination
          v-model="currentPage"
          :total-rows="rows"
          :per-page="perPage"
          aria-controls="my-table"
        ></b-pagination>
        <p class="mt-3">Current Page: {{ currentPage }}</p>
        <b-table ref="filteredQuotes" show-empty
          id="my-table"
          :items="filteredQuotes"
          :per-page="perPage"
          :current-page="currentPage"
          small>
        </b-table>
        </div> 
      </div>
  </div>
</template>


<script>
export default {
  name: 'Http',

  data() {
    return{
        items: [],
        search: "",
        perPage: 15,
        currentPage: 1
    }
  },

  methods: {

  },

  props: {

  },

  created() {
      this.$http.get('https://raw.githubusercontent.com/ahmedakhtar11/Quotes-Vue/master/quotes.json').then(function(data) {
            console.log(data);
            console.log("hello");
            console.log(data.body[0].theme);
            this.items = data.body;
         })
    
    },

    computed: {

    filteredQuotes: function() {
      return this.items.filter((item) => {
      return item.quote.match(this.search);
      });
    },

    rows() {
      return this.items.length
     
    }

  }

}
</script>


<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- Basic Styling -->
<style scoped>

#http {
    max-width: 800px;
    margin: 0 auto;
}

.is-complete {
  color: red;
  /* display: none; */
}

h3 {
  margin: 40px 0 0;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>