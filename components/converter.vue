<template>
    <v-container>
    <v-layout
    row
    wrap
    >
      <v-flex xs4>
        <v-btn 
        color="info"
        @click="convert"
        >
          Convert
        </v-btn>
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
          v-model='type'
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
          :value='result'
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
        inputvalue:"",
        items: ['Magnet', 'Baidupan', 'Youtube'],
        type:'',
        result:''
      }
    },
    props:{
        "label":{
            default:"label"
        }
    },
    mounted () {
      this.type = this.items[0]
    },
    methods: {
      clear: function (){
        this.inputvalue=""
      },
      convert: function (){
        let _type = this.type
        let _input = this.inputvalue.split("\n")
        let _result = new Array()
        for (var i=0;i<_input.length;i++){
          let temp = Array()
          if(_type==this.items[0]){
            temp.push("magnet:?xt=urn:btih:")
          }
          else if(_type==this.items[1]){
            if(_input[i].substring(0,3)=="/s/"){
              _input[i]=_input[i].slice(3)
            } 
            temp.push("https://pan.baidu.com/s/")
          }
          else if(_type==this.items[2]){
            temp.push("https://www.youtube.com/watch?v=")
          }
          temp.push(_input[i])
          _result[i]=temp.join("")
        }
        this.result=_result.join("\n")
      }
    }
}
</script>