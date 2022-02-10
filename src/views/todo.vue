<template>
<v-container>
  <br>
  <center><h1><font color=#C51162>Assignment</font></h1></center>
  <br>
  <v-row justify="center">
      <v-col
        cols="12"
        sm="10"
        md="8"
        lg="6"
        
      >
  <v-form ref="form" v-model="valid" lazy-validation >
    <v-select
      v-model="dataList.subject"
      :items="items1"
      :rules="[(v) => !!v || 'Item is required']"
      label="Course"
      required
  >
    </v-select>
    <v-row
    justify="center"
    align="center"
      
  > 
    <v-btn :disabled="!valid" color="purple lighten-3"  @click="save" width="100">
      SUBMID
    </v-btn>
  </v-row>
    <br>
    <br>
    
  </v-form>
    </v-col>
</v-row>

  <v-card max-width="800" class="mx-auto">
    <v-toolbar color="pink lighten-2" dark>
      <v-app-bar-nav-icon></v-app-bar-nav-icon>

      <v-toolbar-title>TODO</v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>
    <v-list>
      <v-list-item v-for="(item,index) in List" :key="index">
        <v-list-item-content>
          <v-list-item-title v-text="item.name"></v-list-item-title>
        </v-list-item-content>
        <v-btn @click="Del(index)" color="blue lighten-2">Delete</v-btn>
      </v-list-item>
    </v-list>
  </v-card>
</v-container>
</template>

<script>
export default {
  data: () => ({
    valid: true,
    dataList: {
      subject: "",
    },
    List: [
      {
        name: "Course",
      },
    ],
    items1: ["Course 1", "Course 2", "Course 3", "Course 4"],
  }),
  methods: {
    save() {
      this.List.push({
        name: this.dataList.subject,
      });
    },
    Del(n){
        this.List.splice(n,1);
        }
  },
};
</script>

<style></style=c>
