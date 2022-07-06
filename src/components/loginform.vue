<template>
  <form @submit.prevent="onSubmit">
    <BaseInput label="Email" type="email" v-model="email" :error="emailError"></BaseInput>
    <BaseInput
      label="password"
      type="password"
      v-model="password"
      :error="passwordError"
    ></BaseInput>
    <button type="button">Submit</button>
  </form>
</template>
<script>
import BaseInput from "./BaseInput.vue";
import { useField, useForm } from "vee-validate";
export default {
  setup() {
    function onSubmit() {
      alert("Submitted");
    }
    const validations = {
      email: (value) => {
        if (!value) return "this field is required";

        const regex = /^(([^<>()\[\]\\.,;:\s@"]+(\.[^<>()\[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/;
        if (!regex.test(String(value))) return "Please enter a valid email address";

        return true;
      },
      password: (value) => {
        if (value === undefined || value === null) return "this field is required";
        if (!value.length) return "this field is required";
        return true;
      },
    };

    useForm({
      validationSchema: validations,
    });
    const { value: email, errorMessage: emailError } = useField("email");
    const { value: password, errorMessage: passwordError } = useField("password");

    return {
      onSubmit,
      email,
      emailError,
      password,
      passwordError,
    };
  },
  components: {
    BaseInput,
  },
};
</script>
