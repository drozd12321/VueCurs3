<template>
  <small v-if="errName && nameInp === 'Имя'">{{ errName }}</small>
  <div :class="{ formgr: true, invalid: errName }">
    <label :for="id"
      ><strong>{{ nameInp }}:&nbsp;</strong>
    </label>
    <input
      :id="id"
      :type="type"
      :value="modelValue"
      :placeholder="placeholder"
      @input="change"
    />
  </div>
</template>
<script>
export default {
  emits: ["update:modelValue"],
  props: {
    errName: String,
    nameInp: String,
    placeholder: String,
    type: String,
    modelValue: [String, Number],
  },
  data() {
    return {
      id: "input-" + Math.random(),
    };
  },
  methods: {
    change(e) {
      let val = e.target.value;
      if (this.type === "number") {
        val = Number(val);
      }
      this.$emit("update:modelValue", val);
    },
  },
};
</script>
<style>
.formgr {
  display: flex;
  align-self: center;
  align-items: center;
  margin-bottom: 20px;
  width: 500px;
}
.invalid input {
  border: 1px solid red;
}
input {
  width: 500px;
  border-radius: 5px;
  outline: none;
  border: none;
  padding: 5px;
}
small {
  color: rgb(255, 2, 2);
  font-weight: 500;
  font-size: 15px;
}
</style>
