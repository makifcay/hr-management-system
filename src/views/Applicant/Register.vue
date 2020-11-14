/* eslint-disable */

<template>
  <div class="register">
    <Navbar />
    <div class="container">
      <b-form @submit="onSubmit" @reset="onReset" v-if="show">
        <b-form-group id="name-group" label="Ad" label-for="name">
          <b-form-input
            id="name"
            v-model="form.name"
            type="text"
            required
            placeholder="Ad"
          ></b-form-input>
        </b-form-group>

        <b-form-group id="surname-group" label="Soyad" label-for="surname">
          <b-form-input
            id="surname"
            v-model="form.surname"
            type="text"
            required
            placeholder="Soyad"
          ></b-form-input>
        </b-form-group>

        <b-form-group id="address-group" label="Adres" label-for="address">
          <b-form-textarea
            id="address"
            v-model="form.address"
            placeholder="Adres"
            rows="3"
            required
            no-resize
          ></b-form-textarea>
        </b-form-group>

        <b-form-group id="tel-group" label="Telefon" label-for="tel">
          <b-form-input
            id="tel"
            v-model="form.tel"
            type="tel"
            placeholder="Ülke/alan kodu olmadan"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="email-group"
          label="Email"
          label-for="email"
          description="E-posta adresiniz sadece başvuru sonucu bilgilendirmesi için kullanılacaktır."
        >
          <b-form-input
            id="email"
            v-model="form.email"
            type="email"
            placeholder="Enter email"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="birthdate-group"
          label="Doğum tarihi"
          label-for="birthdate"
        >
          <b-form-datepicker
            id="birthdate"
            v-model="form.birthdate"
            locale="tr-TR"
          ></b-form-datepicker>
        </b-form-group>
        <b-form-group
          id="languages-group"
          label="Yabancı diller"
          label-for="languages"
        >
          <b-form-input
            id="languages"
            v-model="form.languages"
            placeholder="Örn. İngilizce, Almanca"
          >

          </b-form-input>
        </b-form-group>

        <b-form-group
          id="licences-group"
          label="Ehliyetler"
          label-for="licences"
        >
          <b-form-checkbox-group
            id="licences"
            v-model="form.licences"
            :options="licenceSelect"
          >
          </b-form-checkbox-group>

        </b-form-group>
        <b-form-group
          id="companyName-group"
          label="Firma adı"
          label-for="companyName"
        >
          <b-form-input
            id="companyName"
            v-model="form.experiences.companyName"
            placeholder="Firma adı"
          ></b-form-input>
        </b-form-group>

        <b-button type="submit" variant="primary">Gönder</b-button>
        <b-button type="reset" variant="danger">Sıfırla</b-button>
      </b-form>
      <b-card class="mt-3" header="Form Çıktısı">
        <pre class="m-0">{{ form }}</pre>
      </b-card>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "@/components/Navbar.vue";

export default {
  name: "ApplicantRegistration",
  components: {
    Navbar
  },
  data() {
    return {
      form: {
        name: "",
        surname: "",
        address: "",
        tel: "",
        email: "",
        birthdate: "",
        languages: "",
        licences: [],
        education: {
          id: "",
          schoolName: "",
          degree: "",
          profession: "",
          startDate: "",
          endDate: "",
          avg: ""
        },
        experiences: {
          id: "",
          companyName: "",
          location: "",
          positionOrTask: "",
          duration: ""
        }
      },
      licenceSelect: [
        { text: 'M', value: 'm' },
        { text: 'A1', value: 'a1' },
        { text: 'A2', value: 'a2' },
        { text: 'A', value: 'a' },
        { text: 'B1', value: 'b1' },
        { text: 'B', value: 'b' },
        { text: 'BE', value: 'be' },
        { text: 'C1', value: 'c1' },
        { text: 'C1E', value: 'c1e' },
        { text: 'C', value: 'c' },
        { text: 'CE', value: 'ce' },
        { text: 'D', value: 'd' },
        { text: 'D1', value: 'd1' },
        { text: 'D1E', value: 'd1e' },
        { text: 'F', value: 'f' },
        { text: 'G', value: 'g' }
      ],
      show: true
    };
  },
  methods: {
    onSubmit(evt) {
      evt.preventDefault();
      alert(JSON.stringify(this.form));
    },
    onReset(evt) {
      evt.preventDefault();
      // Reset our form values
      this.form.name = "";
      this.form.surname = "";
      this.form.address = "";
      this.form.tel = "";
      this.form.email = "";
      this.form.birthdate = "";
      this.form.languages = "";
      this.form.licences = [];
      // Trick to reset/clear native browser form validation state
      this.show = false;
      this.$nextTick(() => {
        this.show = true;
      });
    }
  }
};
</script>

<style scoped lang="scss">
.container {
  margin: 10px auto;
  width: 40%;
}
</style>
