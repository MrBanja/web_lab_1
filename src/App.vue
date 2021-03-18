<template>
  <div id="app">
    <div class="log-in">
      <div class="container-fluid mt-4">
        <div class="row">
          <div class="col"></div>
          <div class="col justify-content-center">
            <div class="container border p-4">
              <ul class="pagination justify-content-center">
                <li class="page-item" :class="{' active': formNum === 1}"><a class="page-link" href="#" @click="changeFormNum(1)">1</a></li>
                <li class="page-item" :class="{' active': formNum === 2}"><a class="page-link" href="#" @click="changeFormNum(2)">2</a></li>
                <li class="page-item" :class="{' active': formNum === 3}"><a class="page-link" href="#" @click="changeFormNum(3)">3</a></li>
              </ul>
              <template v-if="formNum === 1"><FirstForm/></template>
              <template v-if="formNum === 2"><SecondForm/></template>
              <template v-if="formNum === 3"><ThirdForm/></template>
              <button type="submit" class="btn btn-primary" @click="nextForm()">Submit</button>
            </div>
          </div>
          <div class="col"></div>
        </div>
      </div>
    </div>
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
    },
    changeFormNum(num){
      if (num > 0 && num < 4){
        this.formNum = num;
      }
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
