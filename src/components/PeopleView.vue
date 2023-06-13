<script setup>
import { store, getGrandTotal } from '../store/store';
import LabelGeneric from './LabelGeneric.vue';
import PersoneGeneric from './PersoneGeneric.vue';

</script>

<template>
    <div class="no-items" v-if="store.people.length === 0">No items</div>
    <div class="people-view" v-if="store.people.length > 0">
        <div class="header">
            <div>
                <LabelGeneric title="Total + Tip: " :value="getGrandTotal()"/>
            </div>

            <div>
                <LabelGeneric title="Remaining: " :value="store.params.remaining"/>
            </div>
        </div>

        <div class="people-container">
            <PersoneGeneric
                v-for="person in store.people"
                :key="person.id"
                :id="person.id"
                :number-of-person="person.numberOfPerson"
                :total-per-person="person.totalPerPerson"
                :paid="person.paid"/>

        </div>
    </div>
</template>

<style scoped>
.no-items {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 28px;
}
.people-view {
  margin: 0 auto;
  display: flex;
  align-items: center;
  flex-direction: column;
}
.people-container {
    width: 100%;
    max-width: 800px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 10px;
}

.header {
  color: white;
  font-weight: bolder;
  padding: 20px 0;
  font-size: 28px;
  display: flex;
  justify-content: space-between;
  gap: 10px;
  flex-direction: column;
}
</style>