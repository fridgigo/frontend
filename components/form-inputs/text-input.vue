<template>
  <div :class="divClass">
    <label :for="id">{{title}}</label>
    <input
      :type="type"
      :id="id"
      :class="className"
      :placeholder="placeholder"
      :required="required"
      :value="value"
      @input="$emit('input', $event.target.value)"
    />
  </div>
</template>

<script>
export default {
  name: "TextInput",
  props: [
    "divClass",
    "id",
    "className",
    "placeholder",
    "required",
    "value",
    "type",
    "title"
  ],
};
</script>
