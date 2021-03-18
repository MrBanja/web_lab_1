<template>
  <div id="app">
    <template v-if="formNum === 1"><FirstForm/></template>
    <template v-if="formNum === 2"><SecondForm/></template>
    <template v-if="formNum === 3"><ThirdForm/></template>
    <button type="submit" class="btn btn-primary" @click="nextForm()">Submit</button>
  </div>
</template>

<script>
import FirstForm from './components/FirstForm.vue'
import SecondForm from "@/components/SecondForm";
import ThirdForm from "@/components/ThirdForm";

export default {
  name: 'App',
  data() {
    return {
      formNum: 1
    }
  },
  methods: {
    nextForm() {
      this.formNum++;
      if (this.formNum > 3)
        this.formNum = 1;
    }
  },
  components: {
    FirstForm,
    SecondForm,
    ThirdForm
  }
}
</script>

<style>
@import 'https://cdn.jsdelivr.net/npm/bootstrap@4.5.3/dist/css/bootstrap.min.css';
</style>
