<template>
  <div id="app">
    <v-app id="inspire">
      <v-container>
        <v-row
          ><v-btn @click="add">ADD</v-btn
          ><v-btn @click="remove">REMOVE</v-btn></v-row
        >
        <v-data-table :headers="headers" :items="desserts">
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
                <span v-else>{{ item.name }}</span>
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
      index: 0,
      headers: [
        {
          text: "Name",
          align: "start",
          sortable: true,
          value: "name",
        },
        { text: "Head of Sales", value: "headOfSales", align: "start" },
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
    }
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
  },
  methods: {
  
    add() {
      //    this.desserts.push({
      //   name:'dsaf',
      //   cols:[7]
      // })
      this.desserts.forEach((item) => {
        item.cols.push("val" + this.index);
      });
      this.headers.push({ text: this.data.map((e)=>e.roleName), value: "sddss" });

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
  padding: none;
}



</style>
