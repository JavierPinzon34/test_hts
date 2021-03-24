<template>
  <div class="container">
    <div class="row justify-content-center">
      <div class="col-md-8">
        <div class="card">
          <div class="card-header">Registro</div>

          <div class="card-body">
            <form @submit.prevent="sendData">
              <div class="form-group">
                <label for="name">Nombres:</label>
                <input
                  type="text"
                  v-model="form.name"
                  class="form-control"
                  id="name"
                />
              </div>
              <div class="form-group">
                <label for="lastname">Apellidos:</label>
                <input
                  type="text"
                  v-model="form.lastname"
                  class="form-control"
                  id="lastname"
                />
              </div>
              <div class="form-group">
                <label for="age">Edad:</label>
                <input
                  type="number"
                  v-model="form.age"
                  class="form-control"
                  id="age"
                />
              </div>
              <div class="form-group">
                <label for="profession">Profesión:</label>
                <input
                  type="text"
                  v-model="form.profession"
                  class="form-control"
                  id="profession"
                />
              </div>
              <button type="submit" class="btn btn-primary">Enviar</button>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        name: null,
        lastname: null,
        age: 0,
        profession: null
      }
    };
  },

  methods: {
    sendData() {
      axios.post('register',this.form)
      .then(res => {
        console.log(res)
      })
      .catch(err => {
        console.error(err);
      })
    }
  },
};
</script>
