<template>
    <section>
    <form action="" @submit.prevent="addhadiah">
        <div class="modal-card">
          <header class="modal-card-head">
            <p class="modal-card-title">add Agen</p>
          </header>
          <section class="modal-card-body">
            <b-field label="Nama Agent">
              <b-input type="text" v-model="form.namaagen" placeholder="Nama Agen" required>
              </b-input>
            </b-field>

            <b-field label="Alamat">
              <b-input type="text" v-model="form.alamat" placeholder="Alamat" required>
              </b-input>
            </b-field>

            <b-field label="Kota">
              <b-input v-model="form.kota" type="text" placeholder="Kota" required>
              </b-input>
            </b-field>

            <b-field label="Nomor Telephone">
              <b-input v-model="form.nomortelp" type="text" placeholder="No Hp" required>
              </b-input>
            </b-field>

            <b-field label="Email">
              <b-input v-model="form.email" type="text" placeholder="Email" required>
              </b-input>
            </b-field>

          </section>
          <footer class="modal-card-foot is-pulled-right move-right">
            <div class="control is-grouped is-pulled-right move-right">
              <button class="button is-primary">Simpan</button>
            </div>
          </footer>
        </div>
      </form>
    </section>
</template>

<script>
  // import Datatable from '~/components/Datatable.vue'
  const qs = require('querystring')
  const data = []
  export default {
    layout: "application",
    components: {
      // Datatable
    },
    data() {
      return {
        data,
        form: [],
      }
    },
    created() {
      // this.loadPostsData()
    },
    methods: {
      addhadiah() {
        console.log('sdagjhgs');
        const config = {
          headers: {
            Accept: 'application/json, text/plain, */*',
            "Content-Type": "application/json"
          },
          params:  {
            command: "ADD_AGEN",
            namaagen: this.form.namaagen,
            alamat: this.form.alamat,
            kota: this.form.kota,
            nomortelp: this.form.nomortelp,
            email: this.form.email
          }
        };
        const json = JSON.stringify({
            command: "ADD_AGEN",
            namaagen: this.form.namaagen,
            alamat: this.form.alamat,
            kota: this.form.kota,
            nomortelp: this.form.nomortelp,
            email: this.form.email
          });
        
        const data = {
            command: "ADD_AGEN",
            namaagen: this.form.namaagen,
            alamat: this.form.alamat,
            kota: this.form.kota,
            nomortelp: this.form.nomortelp,
            email: this.form.email
          };
        console.log("Res =>",config);
        this.$axios.post("http://165.22.61.192:9911",config)
          .then((response) => {
            let getData = response.data
            console.log(getData);
          })
      }
    },
  }
</script>