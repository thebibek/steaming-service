<template>
  <ValidationObserver ref="form">
    <form class="mt-4" novalidate>
      <ValidationProvider v-slot="{ errors }" vid="email" name="E-mail" >
        <div class="form-group">
          <input
            id="emailInput"
            v-model="user.email"
            type="email"
            :class="'form-control mb-0' +(errors.length > 0 ? ' is-invalid' : '')"
            aria-describedby="emailHelp"
            placeholder="Enter email"
            required
          >
          <div class="invalid-feedback">
            <span>{{ errors[0] }}</span>
          </div>
        </div>
      </ValidationProvider>
      <ValidationProvider v-slot="{ errors }" vid="password" name="Password">
        <div class="form-group">
          <input
            id="passwordInput"
            v-model="user.password"
            type="password"
            :class="'form-control mb-0' +(errors.length > 0 ? ' is-invalid' : '')"
            placeholder="Password"
            required
          >
          <div class="invalid-feedback">
            <span>{{ errors[0] }}</span>
          </div>
        </div>
      </ValidationProvider>
      <div class="sign-info">
        <button type="submit" class="btn btn-hover">
          Sign in
        </button>
        <div class="custom-control custom-checkbox d-inline-block">
          <input :id="formType" type="checkbox" class="custom-control-input">
          <label class="custom-control-label" :for="formType">Remember Me</label>
        </div>
      </div>
    </form>
  </ValidationObserver>
</template>

<script>
export default {
  name: 'SignIn1Form',
  props: ['formType', 'email', 'password'],
  data: () => ({
    user: {
      email: '',
      password: ''
    }
  }),
  mounted () {
    this.user.email = this.$props.email
    this.user.password = this.$props.password
  },
  methods: {
  }
}
</script>
