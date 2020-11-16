/* eslint-disable */

<template>
  <div class="register">
    <Navbar />
    <ApplicantNav />

    <div class="container">
      <b-form @submit="onSubmit" @reset="onReset" v-if="show">
        <b-form-row>
          <b-form-group
            id="name-group"
            label="Ad"
            label-for="name"
            class="col-md-6"
          >
            <b-form-input
              id="name"
              v-model="form.name"
              type="text"
              required
              placeholder="Ad"
            ></b-form-input>
          </b-form-group>

          <b-form-group
            id="surname-group"
            label="Soyad"
            label-for="surname"
            class="col-md-6"
          >
            <b-form-input
              id="surname"
              v-model="form.surname"
              type="text"
              required
              placeholder="Soyad"
            ></b-form-input>
          </b-form-group>
        </b-form-row>

        <b-form-group id="address-group" label="Adres" label-for="address">
          <b-form-textarea
            id="address"
            v-model="form.address"
            placeholder="İkamet adresiniz"
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
          label="E-posta"
          label-for="email"
          description="E-posta adresiniz sadece başvuru süreci için kullanılacaktır."
        >
          <b-form-input
            id="email"
            v-model="form.email"
            type="email"
            placeholder="İletişim e-posta adresiniz"
            required
          ></b-form-input>
        </b-form-group>

        <b-form-group
          id="birthdate-group"
          label="Doğum yılı"
          label-for="birthdate"
        >
          <b-form-spinbutton
            id="birthdate"
            v-model="form.birthdate"
            min="1960"
            max="2020"
            placeholder="Yıl"
            wrap
            required
          ></b-form-spinbutton>
        </b-form-group>
        <b-card
            header="Yabancı dil"
            class="mt-3"
          >
          <b-form-group
            id="languages-group"
          >
            <b-form-input
              id="languages"
              v-model="form.languages"
              placeholder="Örn. İngilizce, Almanca"
            >
            </b-form-input>
          </b-form-group>
          <button type="button" class="btn btn-success float-right" style="margin-top: auto;">Dil ekle</button>
        </b-card>
        <b-card
          header="Ehliyet"
          class="mt-3"
        >
          <b-form-group
              id="licences-group"
          >
            <b-form-checkbox-group
              id="licences"
              v-model="form.licences"
              :options="licenceSelect"
            >
            </b-form-checkbox-group>

          </b-form-group>
        </b-card>

        <b-card
            header="Eğitim"
            class="mt-3"
        >
          <b-form-group
              id="schoolName-group"
              label="Okul"
              label-for="schoolName"
          >
            <b-form-input
                id="schoolName"
                v-model="form.education.schoolName"
                placeholder="Okul adı"
            ></b-form-input>
          </b-form-group>
          <b-form-group
              id="degree-group"
              label="Tür"
              label-for="degree"
          >
            <b-form-input
              id="degree"
              v-model="form.education.degree"
              placeholder="Örn. Lise, Yüksek Lisans"
            ></b-form-input>
          </b-form-group>
          <b-form-group
            id="profession-group"
            label="Uzmanlık"
            label-for="profession"
          >
            <b-form-input
              id="profession"
              v-model="form.education.profession"
              placeholder="Örn. Sayısal, Endüstri Mühendisliği vb."
            ></b-form-input>
          </b-form-group>
          <b-form-row>
            <b-form-group
              id="startDate-group"
              label="Başlangıç"
              label-for="startDate"
              class="col-md-6"
            >
              <b-form-spinbutton
                id="endDate"
                v-model="form.education.startDate"
                min="1990"
                max="2020"
                wrap
                required
                placeholder="--"
              ></b-form-spinbutton>
            </b-form-group>

            <b-form-group
              id="endDate-group"
              label="Bitiş"
              label-for="endDate"
              class="col-md-6"
            >
              <b-form-spinbutton
                id="endDate"
                v-model="form.education.endDate"
                min="1990"
                max="2020"
                wrap
                required
                placeholder="--"
              ></b-form-spinbutton>
            </b-form-group>
          </b-form-row>

          <button type="button" class="btn btn-success float-right" style="margin-top: auto;">Okul ekle</button>
        </b-card>

        <b-card
          header="İş deneyimi"
          class="mt-3"
        >
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
          <b-form-group
            id="location-group"
            label="Konum"
            label-for="location"
          >
            <b-form-input
              id="location"
              v-model="form.experiences.location"
              placeholder="Firmanın bulunduğu il"
            ></b-form-input>
          </b-form-group>
          <b-form-group
            id="position0rTask-group"
            label="Pozisyon veya Görev"
            label-for="positionOrTask"
          >
            <b-form-input
              id="positionOrTask"
              v-model="form.experiences.positionOrTask"
              placeholder="Görev"
            ></b-form-input>
          </b-form-group>
          <b-form-group
            id="duration-group"
            label="Çalışma süresi"
            label-for="location"
          >
            <b-form-input
              id="duration"
              v-model="form.experiences.duration"
              placeholder="Yıl olarak"
            ></b-form-input>
          </b-form-group>

          <button type="button" class="btn btn-success float-right" style="margin-top: auto;">İş deneyimi ekle</button>
        </b-card>

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
import ApplicantNav from "@/components/ApplicantNav";

export default {
  name: "ApplicantRegistration",
  components: {
    Navbar,
    ApplicantNav
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
        education: [
          {
            id: "",
            schoolName: "",
            degree: "",
            profession: "",
            startDate: '',
            endDate: '',
            avg: ""
          }
        ],
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
