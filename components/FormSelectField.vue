<template>
  <div>
    <label class="block text-gray-700 text-sm font-bold mb-2 xl:text-base" :for="selectFieldId">{{
      label
    }}</label>
    <div class="relative">
      <select
        :id="selectFieldId"
        class="block appearance-none w-full bg-white border border-gray-400 hover:border-gray-500 px-2 py-2 pr-8 rounded shadow leading-tight focus:outline-none focus:shadow-outline text-sm xl:text-base"
      >
        <template v-for="(option, i) in options">
          <option :key="i" :value="option.value"> {{ option.text }}</option>
        </template>
      </select>
      <div
        class="pointer-events-none absolute inset-y-0 right-0 flex items-center px-2 text-gray-700"
      >
        <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20">
          <path d="M9.293 12.95l.707.707L15.657 8l-1.414-1.414L10 10.828 5.757 6.586 4.343 8z" />
        </svg>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';

export default Vue.extend({
  props: {
    label: {
      type: String,
      required: true,
    },
    selectFieldId: {
      type: String,
      required: true,
    },
    options: {
      type: Array as () => Array<any>,
      required: true,
    },
  },
});
</script>
