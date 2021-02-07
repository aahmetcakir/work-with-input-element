<template>
  <div class="container">
    <form>
      <div class="row" v-if="!isSubmit">
        <div
          class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3"
        >
          <form action="">
            <div class="panel-body">
              <!-- <p>
                Tam Ad: <br />
                <input type="text" v-model="user.name" />
              </p> -->
              <name v-model="fullname"></name>
              <p>
                E-mail: <br />
                <input type="text" v-model="mail" />
              </p>
              <p>
                Şifre: <br />
                <input type="password" v-model="password" />
              </p>
              <p>
                Cinsiyet: <br />
                erkek
                <input type="radio" value="erkek" v-model="gender" /> kadin
                <input type="radio" value="kadin" v-model="gender" />
              </p>
            </div>
            <button @click.prevent="submit">Gönder</button>
          </form>

          <!-- Soru 3 -->
          <!-- Yukarıdaki uygulamayı düzenleyerek Tam Ad (Ad + Soyad) alanı için bir Form Kontrol Elemanı üretiniz -->
        </div>
      </div>
    </form>
    <hr />
    <div class="row" v-if="isSubmit">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-info">
          <div class="panel-heading">
            <h4>Girdiğiniz Bilgier</h4>
          </div>
          <div class="panel-body">
            <p>Tam Ad: {{ fullname }}</p>
            <p>E-mail: {{ mail }}</p>
            <p>Şifre: {{ password }}</p>
            <p>Cinsiyet: {{ gender }}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import name from "./components/name";

export default {
  components: { name },
  data() {
    return {
      isSubmit: false,
        fullname: "",
        mail: "",
        password: "",
        gender: 0,
    };
  },
  methods: {
    submit() {
      this.isSubmit = true;
    },
  },
};
</script>

<style>
</style>
