<template>
  <b-container fluid>
    <b-row class="row">
      <b-col sm="12">
        <div class="iq-card">
          <div class="iq-card-header d-flex justify-content-between">
            <div class="iq-header-title">
              <h4 class="card-title">
                Movie Lists
              </h4>
            </div>
            <div class="iq-card-header-toolbar d-flex align-items-center">
              <nuxt-link to="/backend/movie/AddMovie" class="btn btn-primary">
                Add Movie
              </nuxt-link>
            </div>
          </div>
          <div class="iq-card-body">
            <div class="table-view">
              <table class="data-tables table movie_table " style="width:100%">
                <thead>
                  <tr>
                    <th>Movie</th>
                    <th>Quality</th>
                    <th>Category</th>
                    <th>Release Year</th>
                    <th>Language</th>
                    <th style="width: 20%;">
                      Description
                    </th>
                    <th>Action</th>
                  </tr>
                </thead>
                <tbody>
                  <tr v-for="(movie,index) in movieList" :key="index">
                    <td>
                      <div class="media align-items-center">
                        <div class="iq-movie">
                          <a href="javascript:void(0);"><img
                            :src="movie.file"
                            class="img-border-radius avatar-40 img-fluid"
                            alt=""
                          ></a>
                        </div>
                        <div class="media-body text-white text-left ml-3">
                          <p class="mb-0">
                            {{ movie.name }}
                          </p>
                          <small>{{ movie.duration }}</small>
                        </div>
                      </div>
                    </td>
                    <td>{{ movie.quality }}</td>
                    <td>{{ movie.category }}</td>
                    <td>{{ movie.releseDate }}</td>
                    <td>{{ movie.lang }}</td>
                    <td>
                      <p>
                        {{ movie.description }}
                      </p>
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
                          to="/backend/movie/AddMovie"
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
  name: 'MovieList',
  data () {
    return {
      movieList: [
        {
          id: '1',
          name: '1980',
          description: 'Lorem ipsum dolor sit amet',
          category: 'Action',
          quality: 'HD',
          releseDate: '2010',
          lang: 'Hndi',
          duration: '2h 23m',
          video_link: '',
          file: require('../../../assets/images/movie-thumb/07.jpg')
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
