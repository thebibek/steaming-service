<template>
  <b-container fluid>
    <b-row class="row">
      <b-col lg="12">
        <div class="iq-card">
          <div class="iq-card-body">
            Here Add Your Content.....
          </div>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>
<script>
import { core } from '../../../assets/app/app'

export default {
  layout: 'BackendLayout',
  name: 'BlankPage',
  mounted () {
    core.index()
  }
}
</script>
