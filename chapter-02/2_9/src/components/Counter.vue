<template>
  <div>
    <fieldset>
      <legend>{{ formattedNumber }}</legend>
      <button @click="increase">
        Increase
      </button><button @click="decrease">
        Decrease
      </button>
    </fieldset>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import Component from 'vue-class-component';
import componentMount from '../decorators/componentMount';

@Component
@componentMount
export default class Counter extends Vue {
  valueNumber: number = 0;

  debug: boolean = true;

  get formattedNumber() {
    return `Your total number is: ${this.valueNumber}`;
  }

  increase() {
    this.valueNumber += 1;
  }

  decrease() {
    this.valueNumber -= 1;
  }
}
</script>
