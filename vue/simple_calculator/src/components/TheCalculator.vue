 <template>
  <div class="calculator">
    <h1>Simple Calculator</h1>
    <input type="text" v-model="enteredNumber"/>
    <simple-button
      @addNumbers="addNumbers"
      @subNumbers="subNumbers"
      @mulNumbers="mulNumbers"
      @divNumbers="divNumbers"
      @calculate="calculate"
    ></simple-button>
</div>
</template>

<script>
import SimpleButton from './SimpleButton.vue';

export default {
  name: 'App',
  components: {
    SimpleButton
  },

  data(){
  return{
      enteredNumber: '',
      calculatorValue: '',
      result: '',
      operator: 0,
  }
},

  methods: {
    addNumbers(){
      this.calculatorValue=this.enteredNumber;
      this.enteredNumber='';
      this.operator=1;
    },

    subNumbers() {
      this.calculatorValue=this.enteredNumber;
      this.enteredNumber='';
      this.operator=2;
    },

    mulNumbers() {
      this.calculatorValue=this.enteredNumber;
      this.enteredNumber='';
      this.operator=3;
    },

    divNumbers() {
      this.calculatorValue=this.enteredNumber;
      this.enteredNumber='';
      this.operator=4;
    },

    calculate() {
      if(this.operator==1){
        this.result= parseInt(this.calculatorValue) + parseInt(this.enteredNumber);
        console.log(this.result);
        this.enteredNumber=this.result;
      }else if(this.operator==2){
        this.result= parseInt(this.calculatorValue) - parseInt(this.enteredNumber);
        console.log(this.result);
        this.enteredNumber=this.result;
      }else if(this.operator==3){
        this.result= parseInt(this.calculatorValue) * parseInt(this.enteredNumber);
        console.log(this.result);
        this.enteredNumber=this.result;
      }else if(this.operator==4){
        this.result= parseInt(this.calculatorValue) / parseInt(this.enteredNumber);
        console.log(this.result);
        this.enteredNumber=this.result;
      }
    }
  }
}
</script>

<style>
.calculator {
    height: 500px;
    width: 1000px;
    background-color: orange;
    margin: auto;
    box-shadow: -10px -10px 5px silver;
}

h1{
    display: flex;
    justify-content: center;
    padding-top: 2rem;
    font-size: 3rem;
    color: darkblue;
}

input {
    text-align: center;
    height: 5rem;
    width: 865px ;
    margin-left: 65px;
}
</style>