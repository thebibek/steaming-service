<template>
  <b-container fluid>
    <b-row class="row">
      <b-col sm="12">
        <div class="iq-card">
          <div class="iq-card-header d-flex justify-content-between">
            <div class="iq-header-title">
              <h4 class="card-title">
                Category Lists
              </h4>
            </div>
            <div class="iq-card-header-toolbar d-flex align-items-center">
              <nuxt-link to="/backend/category/AddCategory" class="btn btn-primary">
                Add Category
              </nuxt-link>
            </div>
          </div>
          <div class="iq-card-body">
            <div class="table-view">
              <table class="data-tables table movie_table " style="width:100%">
                <thead>
                  <tr>
                    <th style="width:10%;">
                      No
                    </th>
                    <th style="width:20%;">
                      Name
                    </th>
                    <th style="width:40%;">
                      Description
                    </th>
                    <th style="width:10%;">
                      Movie
                    </th>
                    <th style="width:20%;">
                      Action
                    </th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(category,index) in categoryList" :key="index">
                    <td>{{ category.id }}</td>
                    <td>{{ category.name }}</td>
                    <td>
                      <p>{{ category.description }}</p>
                    </td>
                    <td>20</td>
                    <td>
                      <div class="flex align-items-center list-user-action">
                        <a
                          class="iq-bg-warning"
                          data-toggle="tooltip"
                          data-placement="top"
                          title=""
                          data-original-title="View"
                          href="#"
                        ><i class="lar la-eye" /></a>
                        <nuxt-link
                          to="/backend/category/AddCategory"
                          class="iq-bg-success"
                          data-toggle="tooltip"
                          data-placement="top"
                          title=""
                          data-original-title="Edit"
                          href="#"
                        >
                          <i class="ri-pencil-line" />
                        </nuxt-link>
                        <a
                          class="iq-bg-primary"
                          data-toggle="tooltip"
                          data-placement="top"
                          title=""
                          data-original-title="Delete"
                          href="#"
                        ><i
                          class="ri-delete-bin-line"
                        /></a>
                      </div>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
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
  name: 'CategoryList',
  data () {
    return {
      categoryList: [
        { id: '1', name: 'Drama', description: 'Lorem ipsum dolor sit amet', movie: '20' },
        { id: '2', name: 'Comedy', description: 'Lorem ipsum dolor sit amet', movie: '20' },
        { id: '3', name: 'Romance', description: 'Lorem ipsum dolor sit amet', movie: '20' }
      ]
    }
  },
  computed: {
  },
  mounted () {
    // core.index()
    core.initDataTable()
  },
  methods: {
    
  }
}
</script>
