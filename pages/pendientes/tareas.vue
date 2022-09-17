<template>
  <v-row align="center">
    <v-col cols="12">
      <v-select
        v-model="consultUser"
        @select="loadContacts"
        :menu-props="{ top: true, offsetY: true }"
        label="Label"
        
      ></v-select>
    </v-col>
  </v-row>
</template>

<script>
  export default{
    data(){
      return {
        consultUser:{}
      }
    },
    methods:{
      name(){
        return localStorage.getItem('name')
      }
    }
  };
</script>
