<template>
  <ValidationObserver ref="form" >
    <form class="mt-4" novalidate >
      <ValidationProvider v-slot="{ errors }" vid="name" name="Full Name" rules="required">
        <div class="form-group">
          <input
            id="name"
            v-model="user.name"
            type="text"
            :class="'form-control mb-0' +(errors.length > 0 ? ' is-invalid' : '')"
            aria-describedby="emailHelp"
            placeholder="Enter Full Name"
          >
          <div class="invalid-feedback">
            <span>{{ errors[0] }}</span>
          </div>
        </div>
      </ValidationProvider>
      <ValidationProvider v-slot="{ errors }" vid="name" name="Email" rules="required|email">
        <div class="form-group">
          <input
            id="email"
            v-model="user.email"
            type="email"
            :class="'form-control mb-0' +(errors.length > 0 ? ' is-invalid' : '')"
            aria-describedby="emailHelp"
            placeholder="Enter email"
          >
          <div class="invalid-feedback">
            <span>{{ errors[0] }}</span>
          </div>
        </div>
      </ValidationProvider>
      <ValidationProvider v-slot="{ errors }" vid="password" name="Password" rules="required">
        <div class="form-group">
          <input
            id="password"
            v-model="user.password"
            type="password"
            :class="'form-control mb-0' +(errors.length > 0 ? ' is-invalid' : '')"
            placeholder="Password"
          >
          <div class="invalid-feedback">
            <span>{{ errors[0] }}</span>
          </div>
        </div>
      </ValidationProvider>
      <div class="custom-control custom-checkbox mb-3">
        <input :id="formType" type="checkbox" class="custom-control-input">
        <label class="custom-control-label" :for="formType">I accept <a href="javascript:void(0)" class="text-primary">Terms and Conditions</a></label>
      </div>
      <button type="submit" class="btn btn-hover">
        Sign Up
      </button>
    </form>
  </ValidationObserver>
</template>

<script>
export default {
  name: 'SignUp1Form',
  props: ['formType'],
  data: () => ({
    user: {
      email: '',
      password: ''
    }
  }),
  methods: {}
}
</script>
