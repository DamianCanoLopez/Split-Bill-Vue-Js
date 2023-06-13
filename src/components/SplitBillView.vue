<script setup>
import InputForm from './InputForm.vue';
import PeopleView from './PeopleView.vue';

</script>

<template>
    <div class="container">
        <div class="input-container">
            <InputForm />
        </div>
        <div class="people-container">
            <PeopleView />
        </div>
    </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
}

.input-container {
  flex: 1 1 100%;
  max-width: 100%;
}

.people-container {
  flex: 1 1 100%;
  max-width: 100%;
}
</style>