<template>
  <div class="mt-4">
    <label class="block">
      <Label :label="label" />

      <select
        :name="name"
        :multiple="multiple"
        :disabled="disabled"
        v-bind="$attrs"
        v-on="listenersWithoutInput"
        v-model="model"
        ref="select"
        class="
          block
          w-full
          rounded-md
          border-gray-300
          shadow-sm
          focus:border-indigo-300
          focus:ring
          focus:ring-indigo-200
          focus:ring-opacity-50
          disabled:opacity-50
        "
        :class="{ 'mt-1': label }"
      >
        <slot>
          <SelectChild
            v-for="(option, key) in mappedOptions"
            :key="key"
            :option="option"
          />
        </slot>
      </select>
    </label>

    <Error v-if="errorMessage" :message="errorMessage" />
  </div>
</template>

<script>
import {
  Select,
  SelectChild,
} from "@bradyrenting/form-components-pro-vue3-core";
import Label from "./Label.vue";
import Error from "./Error.vue";

export default {
  components: {
    Error,
    Label,
    SelectChild,
  },

  mixins: [Select],
};
</script>
