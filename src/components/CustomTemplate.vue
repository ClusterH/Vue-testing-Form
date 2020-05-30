<template>
  <div class="hello" style="display:flex; justify-content:center;">
    <!-- <b-card bg-variant="info" text-variant="white" header="Info" class="text-center" style = "max-width: 80rem;  ">
        <b-card-text>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</b-card-text>
    </b-card> -->

    <b-card bg-variant="info" text-variant="white" no-body class="overflow-hidden" style="max-width: 1200px; min-height: 500px; padding: 20px;" >
      <b-row no-gutters class="mt-2 mr-3">
        <b-col md="4" class="fist_row">
          <b-form-group
            label-cols-sm="5"
            label-cols-lg="4"
            label-align-sm="right"
            label="Category:"
            label-for="input-horizontal"
            label-class="pl-0"
          >
          <b-form-input id="input-horizontal" v-model="category" class="ipt-category"></b-form-input>
        </b-form-group>
        </b-col>
        <b-col md="4" class="fist_row">
          <b-form-group
            label-cols-sm="5"
            label-cols-lg="4"
            label-align-sm="right"
            label="Priority:"
            label-for="input-horizontal"
          >
          <b-form-input id="input-horizontal" v-model="priority" class="ipt-priority"></b-form-input>
        </b-form-group>
        </b-col>
        <b-col md="4" class="fist_row">
          <b-form-group
            label-cols-sm="5"
            label-cols-lg="4"
            label-align-sm="right"
            label="Status:"
            label-for="input-horizontal"
          >
          <b-form-input id="input-horizontal" v-model="status" class="ipt-status"></b-form-input>
        </b-form-group>
        </b-col>
      </b-row>

      <b-row no-gutters class="mt-2 mr-3">
        
        <b-col md="4" class="fist_row">
          <b-form-group
            label-cols-sm="5"
            label-cols-lg="4"
            label-align-sm="right"
            label="Org:"
            label-for="input-horizontal"
          >
          <b-form-input id="input-horizontal" v-model="org" class="ipt-org"></b-form-input>
        </b-form-group>
        </b-col>
        <b-col md="4" class="fist_row">
          <b-form-group
            label-cols-sm="5"
            label-cols-lg="4"
            label-align-sm="right"
            label="Equip:"
            label-for="input-horizontal"
          >
          <b-form-input id="input-horizontal" v-model="equip" class="ipt-equip"></b-form-input>
        </b-form-group>
        </b-col>
        <b-col md="4" class="fist_row">
          <b-form-group
            label-cols-sm="5"
            label-cols-lg="4"
            label-align-sm="right"
            label="Tech:"
            label-for="input-horizontal"
          >
          <b-form-input id="input-horizontal" v-model="tech" class="ipt-tech"></b-form-input>
        </b-form-group>
        </b-col>
      </b-row>

      <b-row no-gutters class="mt-2">
        
        <b-col md="3" align-self="center" class="thd-description" style="text-align: center">
          <b-form-group
            label-cols-sm="12"
            label-cols-lg="12"
            label-align-sm="right"
            label-class="pr-3"
            label="Description:"
            label-for="input-horizontal"
          >
        </b-form-group>
        </b-col>
        <b-col md="6"  align-self="center" class="thd-description" style="text-align: center">
          <b-form-group>
          <b-form-input id="input-horizontal" v-model="description" class="ipt-description"></b-form-input>
          </b-form-group>
        </b-col>
        
      </b-row>
      <b-row no-gutters class="mt-2">
        
        <b-col md="3" class="label-note">

          <b-form-group
            label-cols-sm="12"
            label-cols-lg="12"
            label-align-sm="right"
            label="Notes:"
            label-class="pr-3"
            label-for="input-horizontal">
          </b-form-group>
        </b-col>
        <b-col md="6" class="label-note">

          <b-form-group>
            <b-form-input id="input-horizontal" v-model="note" class="ipt-notes"></b-form-input>
          </b-form-group>
        </b-col>
        <b-button variant="success" @click="addUser" class="btn-add">Add</b-button>
      </b-row>

      <b-row no gutters class="mt-2">
        <b-col  md="10" sm="12" lg="10" offset-md="1" offset-lg="1">
          <b-table responsive  :items="items" :fields="fields" :tbody-tr-class="rowClass" ></b-table>
        </b-col>
      </b-row>
    </b-card>
  </div>
</template>

<script>
export default {
  name: 'CustomTemplate',
  props: {
    msg: String
    // rowcount: 0,
    // userArr:{}
  },

  data() {
      return {
        fields: [
          {key: 'date', label: 'Dates', class: 'md-3 lg-3', variant: 'none', width: '30%', tdClass:'align-centers'},
          {key: 'note', label: 'Note', class: 'sm-4 lg-4', variant: 'none', width: '40%'},
          {key: 'user', label: 'User', class: 'sm-3 lg-3', variant: 'none', width: '30%'}
        ],
        category:'',
        priority:'',
        status:'',
        org:'',
        equip:'',
        tech:'',
        description:'',
        note:'',
        items: []

      }
  },
  methods:{
    addUser:function(){
      let mydate = new Date();
      let year = mydate.getFullYear()
      let month = mydate.getMonth() + 1
      let date = mydate.getDate()
      let currentDate = month + "/" + date + "/" + year
      let item = {date: currentDate, note: this.note,  user: this.priority}
      this.items.push(item)
      
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.align-center{
  text-align: left;
}
.first_row {
  margin-left: 20px;
  margin-right: 20px;
}
.btn-add {
  width: 100px;
  height: 40px;
  margin-left: 10px;
}
/* .label-note {
  width: 50px;
} */
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
.thead1{
  width: 30% !important;
  text-align: center !important;
}
.thead2{
  width: 40% !important;
  text-align: center !important;
}
.thead3{
  width: 30% !important;
  text-align: center !important;
}
</style>
