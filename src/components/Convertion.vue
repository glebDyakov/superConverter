<template>
  <div class="hello">
    <div>
      <div class="whatConvert">
        <select class="form-select">
          <option value="Масса">Масса</option>
        </select>
      </div>
    </div>
    <div class="convertion">
    <div class="convertion">
        <input placeholder="Из какой единицу конвертировать" class="form-control" value="" type="text" v-model="outputFromConversion" @input="convert()" />
        <select class="form-select" v-model="fromConversion" @input="convert()">
          <option class="dropdown-menu-item" value="Тонна">Тонна</option>
          <option value="Киллограмм">Киллограмм</option>
          <option value="Грамм">Грамм</option>
        </select>
      </div>
      <p class="equal">&nbsp; = &nbsp;</p>
      <div class="convertion">
        <input disabled placeholder="В какую единицу конвертировать" class="form-control" value="" type="text" v-model="outputToConversion"  @input="convert()" />
        <select class="form-select" v-model="toConversion" @input="convert()">
          <option value="Тонна">Тонна</option>
          <option value="Киллограмм">Киллограмм</option>
          <option value="Грамм">Грамм</option>
        </select>
      </div>
    </div>  
  </div>
</template>

<script>
export default {
  name: 'Convertion',
  data:() => ({
    toConversion:'',
    fromConversion:'',
    outputFromConversion:'',
    outputToConversion:'',
  }),
  methods:{
    convert(){

      if(this.fromConversion == "Киллограмм"){
        
        //this.toConversion = 'Тонна'
        if(this.toConversion == "Киллограмм"){
          //this.outputToConversion = this.outputFromConversion
        } else if(this.toConversion == "Тонна"){
          this.outputToConversion = this.outputFromConversion / 1000 
        } else if(this.toConversion == "Грамм"){
          this.outputToConversion = this.outputFromConversion * 1000 
        }
      }else if(this.fromConversion == "Тонна"){
        if(this.toConversion == "Киллограмм"){
          this.outputToConversion = this.outputFromConversion / 1000
        } else if(this.toConversion == "Тонна"){
          //this.outputToConversion = this.outputFromConversion
        } else if(this.toConversion == "Грамм"){
          this.outputToConversion = this.outputFromConversion / 1000000 
        }
      }
      else if(this.fromConversion == "Грамм"){
        if(this.toConversion == "Киллограмм"){
          this.outputToConversion = this.outputFromConversion / 1000
        } else if(this.toConversion == "Тонна"){
          this.outputToConversion = this.outputFromConversion / 1000000
        } else if(this.toConversion == "Грамм"){
          //this.outputToConversion = this.outputFromConversion
        }
      }
      console.log(this.outputFromConversion)
      console.log(this.fromConversion)
      console.log(this.outputToConversion)
      console.log(this.toConversion)
    }
  }
}
</script>
<style scoped>
  select{
    width:250px;

  }
  .whatConvert{
    display:flex;
    width:100%;
    justify-content:center;
  }
  *{
    margin:0;
    padding:0;

  }
  .equal{
    font-weight:bold;
    font-size:48px;
  }
  .convertion{
    display:flex;
    justify-content:space-between;
    flex-direction:row;
  }
</style>
