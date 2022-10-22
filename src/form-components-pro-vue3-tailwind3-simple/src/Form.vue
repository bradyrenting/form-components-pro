<template>
  <form v-bind="$attrs" :method="method">
    <fieldset :disabled="isProcessing">
      <slot />
    </fieldset>
  </form>
</template>

<script>
import { Form } from "@bradyrenting/form-components-pro-vue3-core";

export default Form;
</script>
