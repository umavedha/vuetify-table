<template>
  <div id="app">
    <v-app id="inspire">
      <v-container>
        <v-row
          ><v-btn @click="add">ADD</v-btn
          ><v-btn @click="remove">REMOVE</v-btn></v-row
        >
        <v-data-table :headers="headers" :items="screens">
          <template v-slot:body="props">
            <tr
              v-for="(item, i) in props.items"
              :key="i"
            >
              <td v-for="(header, index) in headers" :key="index">
                <div v-if="index" class="checkbox-wrapper">
                   <div>
                  <label for="">C</label>
                  <div>
                    <input type="checkbox" />
                  </div>
                  
                </div>
                <div>
                  <label for="">R</label>
                  <div>
                    <input type="checkbox" />
                  </div>
                </div>
                <div>
                  <label for="">U</label>
                  <div>
                    <input type="checkbox" />
                  </div>
                </div>
                <div>
                  <label for="">D</label>
                  <div>
                    <input type="checkbox" />
                  </div>
                </div>
                </div>
                <!-- <span v-if="index">{{ item.cols[index - 1] }}</span> -->
                <span v-else>{{ item }}</span>
              </td>
            </tr>
          </template>
        </v-data-table>
      </v-container>
    </v-app>
  </div>
</template>
<script src="https://cdnjs.cloudflare.com/ajax/libs/vue/1.0.18/vue.min.js"></script>
<script>

export default {
  name: "HelloWorld",
  data() {
    return {
      index: -1,
      roles:[],
      screens:[],
      headers: [
        {
          text: "Screens",
          align: "start",
          sortable: true,
          value: "name",
        },
        // { text: "Head of Sales", value: "headOfSales", align: "start" },
      ],
      data: [
    {
      "id": 17,
      "roleName": "Head of Sales",
    },
    {
      "id": 16,
      "roleName": "TMO Reviewer",
    },
    {
      "id": 15,
      "roleName": "TMO User",
    },
    {
      "id": 14,
      "roleName": "O2C Head",
    },
    {
      "id": 13,
      "roleName": "O2C User",
    },
    {
      "id": 12,
      "roleName": "Business Finance Head",
    },
    {
      "id": 11,
      "roleName": "Business Finance User",
    },
    {
      "id": 10,
      "roleName": "Delivery partner User",
    },
    {
      "id": 9,
      "roleName": "Account manager",
    },
    {
      "id": 8,
      "roleName": "Delivery Partner Head",
    },
     {
      "id": 7,
      "roleName": "Client partner Head",

    },
    {
      "id": 6,
      "roleName": "Client partner user",

    },
    {
      "id": 5,
      "roleName": "Legal Head",

    },
    {
      "id": 4,
      "roleName": "Legal Reviewer",

    },
    {
      "id": 3,
      "roleName": "Legal User",

    },
    {
      "id": 2,
      "roleName": "CG Team",

    },
    {
      "id": 1,
      "roleName": "CG Head",

    }

  ],
  screenData:[
    {
      "id": 1,
      "screenName": "Clients",

    },
    {
      "id": 2,
      "screenName": "Menu",

    },
    {
      "id": 3,
      "screenName": "Contract Repository",

    },
    {
      "id": 4,
      "screenName": "MSA Indexation",

    },
    {
      "id": 5,
      "screenName": "MSA Synopsis",

    },
    {
      "id": 6,
      "screenName": "Services Agreed",

    },
    {
      "id": 7,
      "screenName": "Amendments",

    },
    {
      "id": 8,
      "screenName": "SOW Synopsis",

    },
    {
      "id": 9,
      "screenName": "Commitment & Obligations",

    },
    {
      "id": 10,
      "screenName": "Contract Change Request",

    },
    {
      "id": 11,
      "screenName": "Contract Closure",

    },
    {
      "id": 12,
      "screenName": "Client Masters",

    },
    {
      "id": 13,
      "screenName": "Legal Entity",

    },
    {
      "id": 14,
      "screenName": "Delivery Unit",

    },
    {
      "id": 15,
      "screenName": "Client Category",

    },
    {
      "id": 16,
      "screenName": "Role",

    },
    {
      "id": 17,
      "screenName": "Obligation Category",

    },
     {
      "id": 18,
      "screenName": "Obligation Sub Category",

    },
     {
      "id": 19,
      "screenName": "Approval Workflow",

    },
     {
      "id": 20,
      "screenName": "User",

    },
     {
      "id": 21,
      "screenName": "Service Line",

    },
     {
      "id": 22,
      "screenName": "Insurance",

    },
     {
      "id": 23,
      "screenName": "Billing Type",

    },
    {
      "id": 24,
      "screenName": "Contract Clause",

    },
    {
      "id": 25,
      "screenName": "Clause Category",

    },
    {
      "id": 26,
      "screenName": "Policy Master",

    },
     {
      "id": 27,
      "screenName": "Commitment & Obligations Report",

    },
     {
      "id": 28,
      "screenName": "Reports",

    },

    
  ],
      desserts: [
        {
          name: "Dashboard",
          cols: [0],
        },
      ],
    };
  },
  mounted() {
    this.index = this.headers.length;
    this.roles=this.data.map((e)=>e.roleName)
    this.screens=this.screenData.map((e)=>e.screenName)
    console.log(this.roles,'rolessss');
  },
  methods: {
    
    add() {
      //    this.desserts.push({
      //   name:'dsaf',
      //   cols:[7]
      // })
      console.log(this.index);
      this.desserts.forEach((item) => {
        item.cols.push("val" + this.index);
      });
      this.headers.push({ text: this.roles[this.index-1], value: "sddss" });

      this.index++;
    },
    remove() {
      this.headers.pop();
      this.desserts.forEach((item) => {
        item.cols.pop();
      });
      this.index--;
    },
  },
};
</script>
<style lang="css" scoped>
.checkbox-wrapper{
  display: flex;
}
.checkbox-wrapper > div {
  margin-left: 8px;
} 
.v-data-table > .v-data-table__wrapper > table > thead > tr > th{
  padding: none !important;
}
.v-data-table >.v-data-table__wrapper >table >thead >tr:last-child>th  {
  border: 1px solid #dedede !important;
  
}
.v-data-table >.v-data-table__wrapper>tr:last-child>td  {
  border: 1px solid #dedede !important;
  
}
td {
    border: 1px solid #dedede;
    padding-left: 13px;
}
.v-btn:not(.v-btn--round).v-size--default {
    height: 36px;
    min-width: 64px;
    padding: 0 16px;
    margin-bottom: 30px;
    margin-left: 15px;
    margin-top: 13px;
}
</style>
