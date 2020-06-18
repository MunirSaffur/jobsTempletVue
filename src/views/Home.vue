<template>
  <b-container class="bv-example-row">
  <b-row>
   <jobcart v-for="job in displayJobs" :key="job.id" :name="job.name "/>
  </b-row>
   <b-pagination
      v-model="currentPage"
      :total-rows="rows"
      :per-page="perPage"
      first-text="First"
      prev-text="Prev"
      next-text="Next"
      last-text="Last"
      @input="paginate(currentPage)"
    ></b-pagination> 
</b-container>
</template>

<script>
import jobcart from '@/components/jobCart.vue'

export default {
  name: "Home",
  data() {
    return {
      jobs : [],
      displayJobs : [],
      rows: 1,
      perPage: 3,
      currentPage: 1
    }
  },
  mounted(){
    this.fetchData();
  },
  methods: {
    async fetchData(){
      const res = await fetch("jobs.json");
      const val = await res.json();
      this.jobs = val
      this.rows= this.jobs.length;  
      this.displayJobs = val.slice(0 ,3); 
      console.log(val)
    },
    paginate(currentPage){
    const start = (currentPage - 1) * this.perPage;
    this.displayJobs = this.jobs.slice(start, start +3)
},
  },
  
  components: {
    jobcart
  }
};
</script>
 
 <style>
 .sidebar{
   position: fixed;
    top: 10px;
    left: 10px;
 }
 </style>