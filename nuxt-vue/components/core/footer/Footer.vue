<template>
  <footer class="mb-0">
    <div class="container-fluid">
      <div class="block-space">
        <div class="row">
          <div class="col-lg-3 col-md-4">
            <slot name="column1" />
          </div>
          <div class="col-lg-3 col-md-4">
            <slot name="column2" />
          </div>
          <div class="col-lg-3 col-md-4">
            <slot name="column3" />
          </div>
          <div class="col-lg-3 col-md-12 r-mt-15">
            <slot name="icons" />
          </div>
        </div>
      </div>
    </div>
    <div class="copyright py-2">
      <div class="container-fluid">
        <p class="mb-0 text-center font-size-14 text-body">
          {{ copyrighttext }}
        </p>
      </div>
    </div>
  </footer>
</template>
<script>

export default {
  name: 'Footer',
  props: {
    copyrighttext: { type: String, default: 'STREAMIT - 2020 All Rights Reserved' }
  }
}
</script>
