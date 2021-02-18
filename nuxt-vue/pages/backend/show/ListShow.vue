<template>
  <b-container fluid>
    <b-row class="row">
      <div class="col-sm-12">
        <div class="iq-card">
          <div class="iq-card-header d-flex justify-content-between">
            <div class="iq-header-title">
              <h4 class="card-title">
                Show Lists
              </h4>
            </div>
            <div class="iq-card-header-toolbar d-flex align-items-center">
              <nuxt-link to="/backend/show/AddShow" class="btn btn-primary">
                Add Show
              </nuxt-link>
            </div>
          </div>
          <div class="iq-card-body">
            <div class="table-view">
              <table class="data-tables table movie_table " style="width:100%">
                <thead>
                  <tr>
                    <th>Show</th>
                    <th>Quality</th>
                    <th>Category</th>
                    <th>Language</th>
                    <th style="width:20%">
                      Description
                    </th>
                    <th>Action</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(show,index) in showList" :key="index">
                    <td>
                      <div class="media align-items-center">
                        <div class="iq-movie">
                          <a href="javascript:void(0);"><img
                            :src="show.file"
                            class="img-border-radius avatar-40 img-fluid"
                            alt=""
                          ></a>
                        </div>
                        <div class="media-body text-white text-left ml-3">
                          <p class="mb-0">
                            {{ show.name }}
                          </p>
                        </div>
                      </div>
                    </td>
                    <td>{{ show.quality }}</td>
                    <td>{{ show.category }}</td>
                    <td>{{ show.lang }}</td>
                    <td>
                      <p>{{ show.description }}</p>
                    </td>
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
                          to="/backend/show/AddShow"
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
      </div>
    </b-row>
  </b-container>
</template>
<script>
import { core } from '../../../assets/app/app'
export default {
  layout: 'BackendLayout',
  name: 'ListShow',
  data () {
    return {
      showList: [
        {
          id: '1',
          name: 'Arrival 1999',
          category: 'Thriller',
          quality: 'Full HD',
          lang: 'English',
          file: require('../../../assets/images/show-thumb/08.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '2',
          name: 'Day of Darkness',
          category: 'Drama',
          quality: 'Full HD',
          lang: 'English',
          file: require('../../../assets/images/show-thumb/10.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '3',
          name: 'My True Friends',
          category: 'Action',
          quality: 'Full HD',
          lang: 'Hindi',
          file: require('../../../assets/images/show-thumb/07.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '4',
          name: 'Day of Darkness',
          category: 'Horror',
          quality: 'Full HD',
          lang: 'English',
          file: require('../../../assets/images/show-thumb/01.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '5',
          name: 'Night Mare',
          category: 'Thriller',
          quality: 'Full HD',
          lang: 'English',
          file: require('../../../assets/images/show-thumb/03.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '6',
          name: 'Arrival 1999',
          category: 'Thriller',
          quality: 'Full HD',
          lang: 'English',
          file: require('../../../assets/images/show-thumb/08.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '7',
          name: 'Day of Darkness',
          category: 'Drama',
          quality: 'Full HD',
          lang: 'English',
          file: require('../../../assets/images/show-thumb/10.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '8',
          name: 'My True Friends',
          category: 'Action',
          quality: 'Full HD',
          lang: 'Hindi',
          file: require('../../../assets/images/show-thumb/07.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '9',
          name: 'Day of Darkness',
          category: 'Horror',
          quality: 'Full HD',
          lang: 'English',
          file: require('../../../assets/images/show-thumb/01.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        },
        {
          id: '10',
          name: 'Night Mare',
          category: 'Thriller',
          quality: 'Full HD',
          lang: 'English',
          file: require('../../../assets/images/show-thumb/03.jpg'),
          banner: '',
          description: 'Lorem ipsum dolor sit amet',
        }
      ]
    }
  },
  mounted () {
    core.initDataTable()
  },
  methods: {
  }
}
</script>
