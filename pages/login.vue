<!-- Please remove this file from your project -->
<template lang="pug" >
b-container.container.login.d-flex.align-content-center
  b-form(@submit="onSubmit")
    CustomInput(name="name" type="text" label="Name")
    b-form-group#email(label="Email" name="email")
      b-form-input(v-model="form.email", placeholder="Enter email")
    b-form-group#password(name="password", label="Password", )
      b-form-input(v-model="form.password", placeholder="Enter Password")
    b-button(type="submit") {{'Login'}} 
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: "",
        name: "",
      },
      show: true,
    };
  },
  methods: {
    onSubmit(event) {
      event.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(event) {
      event.preventDefault();
      // Reset our form values
      this.form.email = "";
      this.form.name = "";
      this.form.food = null;
      this.form.checked = [];
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    },
  },
};
</script>

<style lang="scss">
#__layout {
  height: 100vh;
  .login {
    height: inherit;
    width: 90%;
    align-items: center;
    justify-content: center;
    form {
      border: 1px solid;
      padding: 10px;
      width: 100%;
      max-width: 500px;
    }
  }
}
</style>