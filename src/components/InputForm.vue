<script setup>
import {ref} from "vue";
import {store, calculate} from "../store/store"


const total = ref(0);
const tip = ref(0);
const people = ref(0);

function handleSubmit(){
    store.params.total = total;
    store.params.tip = tip;
    store.params.people = people;
    calculate();
}

</script>


<template>
    <form @submit.prevent="handleSubmit">
        <div class="container">
            <div>
                <label for="total">Total</label>
                <input type="number" required v-model="total" />
            </div>

            <div>
                <label for="tip">Tip %</label>
                <input type="number" required v-model="tip" />
            </div>

            <div>
                <label for="people">People</label>
                <input type="number" required v-model="people" />
            </div>

            <div>
                <input class="button" type="submit" value="Calculate" />
            </div>
        </div>
    </form>
</template>

<style scoped>
form {
  width: 100%;
  background-color: rgb(131, 63, 225);
  display: flex;
  align-items: center;
  justify-content: center;
  color: white;
  font-size: 18px;
  padding: 20px;
  box-sizing: border-box;
}

.container {
  width: 100%;
  max-width: 400px;
}

.form-container {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 20px;
}

form label {
  display: block;
}

form input {
  padding: 10px;
  width: 100%;
  box-sizing: border-box;
  font-size: 18px;
}

form .button{
    background-color: rgb(4, 255, 108);
    border-radius: 40%;
    margin-top: 5%;
}

form input:hover{
    border: solid 3px rgb(27, 255, 134);
}

form .button:hover{
    box-shadow: 3px 5px 10px rgb(140, 255, 0);
}

@media (max-width: 600px) {
  form {
    padding: 5px;
  }

  .container {
    max-width: none;
  }
}
</style>