<template>
  <!-- <div class="profile-data"> -->
  <div class="profile">
    <div class="user-detail">
    <div class="user">
      <img src="../assets/img/amber.png" alt="" />
      <h3>Amber West</h3>
    </div>
    <div class="icon-bar">
      <a href="#"><img src="../assets/img/employee.svg" alt="">Employee</a>
      <a @click="showThis" class="active" href="#"><img src="../assets/img/personal.svg" alt="">Personal</a>
      <a href="#"><img src="../assets/img/notes.svg" alt="">Notes</a>
      <a href="#"><img src="../assets/img/documents.svg" alt="">Documents</a>
      <a href="#"><img src="../assets/img/assets.svg" alt="">Assets</a>
      <a href="#"><img src="../assets/img/training.svg" alt="">Training</a>
      <a href="#"><img src="../assets/img/emergency.svg" alt="">Emergency contacts</a>
      <a href="#"><img src="../assets/img/tasks.svg" alt="">Tasks</a>
      <a href="#"><img src="../assets/img/onboarding.svg" alt="">Onboarding</a>
      <a href="#"><img src="../assets/img/reports.svg" alt="">Reports</a>
      <a href="#"><img src="../assets/img/turnoff.svg" alt="">Time off</a>
      <a href="#"><img src="../assets/img/compensation.svg" alt="">Compensation</a>
    </div>
  </div>
  <div class="userData">
    <h3>Personal</h3>
    <div class="table-content">
      <h4>Personal Information</h4>
      <table>
          <tr>
            <th>Date of birth</th>
            <th>Street</th>
            <th>City</th>
            <th>State</th>
            <th>Postcode</th>
          </tr>
          <tr>
            <td>15/07/1992</td>
            <td>Mariotteplein 199</td>
            <td>Amsterdam</td>
            <td>Amsterdam</td>
            <td>1090</td>
   
          </tr>
        <tr>
          <th>Country</th>
          <th>Nationality</th>
          <th>Home Phone</th>
          <th>Home Phone</th>
          <th>Personal Email</th>
        </tr>
        <tr>
          <td>London</td>
          <td>British</td>
          <td>441873740607</td>
          <td>441873740607</td>
          <td>amber@vavoip.com</td>
   
        </tr>
        <tr>
          <th>Gender</th>
          <th>Material Status</th>
        </tr>
        <tr>
          <td>Female</td>
          <td>Single</td>   
        </tr>
      </table>
</div>
    <div class="notesTable">
    <div>
      <h4>Notes</h4>
      <p>“This section allows keeping notes & attachments related to employees. Employees by default don’t have access to this section,unless explicitly given the permission”</p>
    </div>
    <div>
      <button><img src="../assets/img/btn-icon.svg">Add New</button>
    </div>
  </div>
  <div>
    <table>
        <tr>
          <td>FIRST/LAST NAME</td>
          <td>USERNAME/EMAIL</td>
          <td>ROLE</td>
          <td>STATUS</td>
        </tr>

        <tr v-for="item in list" :key="item.id">
          <td>{{item.id}}</td>
          <td>{{item.title}}</td>
          <td>{{item.body}}</td>
          <td>{{item.userId}}</td>
        </tr>
      </table>
  </div>
  <dataFetch/>
  </div>
  
</div>
  
</template>


<script>
  import dataFetch from './dataFetch.vue'
  import Vue from 'vue'
  import axios from 'axios'
  import VueAxios from 'vue-axios'
  Vue.use(VueAxios,axios)
  export default {
  name: "ProfileNavbar",
  components:{
    dataFetch
  },
  methods: {
    showThis(){
      
    }
  },
  data()
  {
    return {list:undefined}
  },
  mounted(){
   fetch('https://jsonplaceholder.typicode.com/posts/?_limit=3')
  .then(resp => resp.json())
  .then(data => this.list = data)
  }
  
}
</script> 