<template>
  <h1>Customer List:</h1>
  <div class="buttonstyle">
    
    <button class="btn1" v-on:click="switchView()">List view</button>
    <br />
    <button class="btn2" v-on:click="switchgrid()">Card view</button>
  </div>
  <div v-if="list" class="listdiv">
    <!-- <List :name="books[0].Name" :email="books[0].Email" /> -->
    <List>
      <ul style="stylelist">
        <li v-for="item in books">
          <!-- <h3>Id : {{ item.Id }}</h3> -->
          <h3>{{ item.Name }}</h3>
          <!-- <h2>Email : {{ item.Email }}</h2> -->
          <!-- <h2>Phone : {{ item.Phone }}</h2> -->
          <!-- <h2>College : {{ item.College_Name }}</h2> -->
        </li>
      </ul>
    </List>
  </div>
  <div v-if="grid" class="griddiv">
    <Grid>
      <ul class="stylegrid">
        <li v-for="item in books">
          <img
            :src="item.ImagePath"
            :alt="item.Name"
            width="50px"
            height="50px"
          />
          <h4>Id : {{ item.Id }}</h4>
          <p>{{ item.Name }}</p>
          <p>Email : {{ item.Email }}</p>
          <p>Phone : {{ item.Phone }}</p>
          <p>College : {{ item.College_Name }}</p>
        </li>
      </ul>
    </Grid>
  </div>
</template>

<script>
import List from "./components/list.vue";
import Grid from "./components/Grid.vue";

export default {
  name: "App",
  components: { List, Grid },
  data() {
    return {
      books: [
        {
          Id: 1,
          Name: "Rajkumar Patel",
          Email: "rajpatel@gmail.com",
          Phone: "9876543210",
          College_Name: "Harvard University",
          ImagePath: "./assets/images/a.jpg",
        },
        {
          Id: 2,
          Name: "Sagar Patel",
          Email: "spatel@gmail.com",
          Phone: "9876543210",
          College_Name: "Harvard University",
          ImagePath: "./assets/images/b.jpg",
        },
        {
          Id: 3,
          Name: "Rana gautam",
          Email: "rgautam@gmail.com",
          Phone: "9876543210",
          College_Name: "Harvard University",
          ImagePath: "./assets/images/c.jpg",
        },
        {
          Id: 4,
          Name: "Nenu Chacko",
          Email: "nchacko@gmail.com",
          Phone: "9876543210",
          College_Name: "Harvard University",
          ImagePath: "./assets/images/d.jpg",
        },
        {
          Id: 5,
          Name: "Sonal Katiyar",
          Email: "skatiyar@gmail.com",
          Phone: "9876543210",
          College_Name: "Harvard University",
          ImagePath: "./assets/images/e.jpg",
        },
      ],
      list: false,
      grid: false,
    };
  },

  methods: {
    switchView: function () {
      this.list = !this.list;
    },
    switchgrid: function () {
      this.grid = !this.grid;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f6f9fa;
  margin-top: 60px;
  background: rgb(49, 165, 49);
}
.buttonstyle {
  position: relative;
}
.btn1 {
  position: absolute;
  top: 50%;
  left: 0;
  width: 120px;
  padding: 10px 10px;
}
.btn2 {
  position: absolute;
  top: 50%;
  left: 125px;
  width: 120px;
  padding: 10px 10px;
}
.listdiv {
  text-align: left;
}
li {
  list-style-type: none;
  background: rgb(39, 90, 39);
}
.stylegrid {
  display: grid;
  grid-template-columns: auto auto auto;
  margin: 20px 20px;
  padding: 20px 20px;
  grid-column-gap: 30px;
  grid-row-gap: 80px;
}
.griddiv {
  text-align: left;
}
.stylelist {
  display: grid;
  grid-row-gap: 20px;
}
</style>
