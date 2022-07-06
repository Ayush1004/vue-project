<template>
  <form
    method="post"
    action="https://www.google.com"
    onSubmit="return validate(this);"
    name="login"
  >
    <input type="email" id="email" required />
    <input type="password" id="password" required />
    <input type="submit" value="Submit" />
  </form>
</template>
<script>
export default {
  methods: {
    validate(form) {
      var ck_email = /^([\w-]+(?:\.[\w-]+)*)@((?:[\w-]+\.)*\w[\w-]{0,66})\.([a-z]{2,6}(?:\.[a-z]{2})?)$/i;
      var email = form.email.value;
      var password = form.password.value;
      var errors = [];
      if (!ck_email.test(email)) {
        errors[errors.length] = "You must enter a valid email address.";
      }
      if (password == "") {
        errors[errors.length] = "You must enter the password ";
      }
      if (errors.length > 0) {
        reportErrors(errors);
        return false;
      }
      return true;
    },
    reportErrors(errors) {
      var msg = "Please Enter Valide Data...\n";
      for (var i = 0; i < errors.length; i++) {
        var numError = i + 1;
        msg += "\n" + numError + ". " + errors[i];
      }
      alert(msg);
    },
  },
};
</script>
