<script>
import CustomChoices from './CustomChoices.vue';
export default {
  components: { CustomChoices },
  data(){
    return {
      msg: "mucho gusto!",
      form: {
        paymentChoices: ['value 1']
      },
    };
  },
};
</script>


<template>
  <div id="app" class="section is-large">
    <div class="container">
      <form>
        <div class="field">
          <CustomChoices v-model="form.paymentChoices" />
        </div>
        <div class="field">
          <button class="button is-primary">
            Submit
          </button>
        </div>
      </form>
    </div>
  </div>
</template>