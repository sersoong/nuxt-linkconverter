<template>
    <v-container>
    <v-layout
    row
    wrap
    >
      <v-flex xs4>
        <v-btn color="info">Convert</v-btn>
        <v-btn
        color="info"
        @click="clear"
        >
          Clear
        </v-btn>
      </v-flex>
      <v-flex xs8>
        <v-select
          :items="items"
          label="Type"
          :value="items[0]"
        ></v-select>
      </v-flex>
      <v-flex xs6>
        <v-textarea
          name="converted"
          :label="label"
          v-model="inputvalue"
          hint="A code per line"
          color="blue"
          auto-grow
        ></v-textarea>
      </v-flex>
    <v-flex xs6>
        <v-textarea
          name="convert"
          label="Result"
          value=""
          color="blue"
          hint="A result per line"
          auto-grow
        ></v-textarea>
    </v-flex>
    </v-layout>
    </v-container>
</template>

<script>


export default{
    name:"tab",
    data () {
      return {
        "inputvalue":"",
        items: ['Magnet', 'Baidupan', 'Fizz', 'Buzz']
      }
    },
    props:{
        "label":{
            default:"label"
        }
    },
    methods: {
      clear: function (){
        this.inputvalue=""
      }
    }
}
</script>