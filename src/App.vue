<template>
  <div id="div-1">
    <div class="warna1">arayasan badminton's</div>
    <b-container class="tempat-1">
      <div>
        <b-row class="counter-utama" style="margin: 7px">
          <b-row>
            <b-col
              class="araya1 borad-5 font-custom"
              @click="angkaSatuTambahsatu()"
              >{{ angkaSatu }}</b-col
            >
            <b-col
              class="araya2 borad-5 font-custom"
              @click="angkaDuaTambahsatu()"
              >{{ angkaDua }}</b-col
            >
          </b-row>
          <b-row style="margin-top: 20px">
            <b-col
              class="araya3 borad-5 font-custom1"
              @click="angkaSatuKurangsatu()"
              >-1</b-col
            >
            <b-col
              class="araya4 borad-5 font-custom1"
              @click="angkaDuaKurangsatu()"
              >-1</b-col
            >
          </b-row>
        </b-row>

        <b-row class="row-3">
          <b-col
            class="araya5 borad-5 font-custom2"
            @click="orangSatupindah()"
            >{{ orangSatu }}</b-col
          >
          <b-col
            class="araya6 borad-5 font-custom2"
            @click="orangDuapindah()"
            >{{ orangDua }}</b-col
          >
          <div class="warna1">serve</div>
        </b-row>
        <b-row class="row-4">
          <b-col
            class="araya7 borad-5"
            @click="$bvModal.show('modal-kon-doang')"
            ><b-icon icon="arrow-repeat" font-scale="3"></b-icon
          ></b-col>
          <b-col class="araya8 borad-5"
            ><b-icon icon="arrow-left-right" font-scale="3" @click="pindah()">
            </b-icon></b-col
        ></b-row>
      </div>
    </b-container>
    <b-modal
      id="modal-kon-doang"
      hide-header
      centered
      ok-title="Ya, reset"
      ok-variant="danger"
      cancel-title="tidak jadi"
      @ok="mengulang()"
    >
      Apakah anda yakin ingin reset??</b-modal
    >
  </div>
</template>

<script>
export default {
  name: "App",
  components: {},
  data: function () {
    return {
      angkaSatu: 0,
      angkaDua: 0,
      orangSatu: "1st",
      orangDua: "",
    };
  },

  methods: {
    angkaSatuTambahsatu() {
      if (this.angkaSatu < 30) {
        return (this.angkaSatu = this.angkaSatu + 1);
      }
    },
    angkaDuaTambahsatu() {
      if (this.angkaDua < 30) {
        return (this.angkaDua = this.angkaDua + 1);
      }
    },
    angkaSatuKurangsatu() {
      if (this.angkaSatu > 0) {
        return (this.angkaSatu = this.angkaSatu - 1);
      }
    },
    angkaDuaKurangsatu() {
      if (this.angkaDua > 0) {
        return (this.angkaDua = this.angkaDua - 1);
      }
    },
    orangSatupindah() {
      this.orangDua = "";
      if (this.orangSatu === "1st") {
        return (this.orangSatu = "2nd");
      } else this.orangSatu = "1st";
    },
    orangDuapindah() {
      this.orangSatu = "";
      if (this.orangDua === "1st") {
        return (this.orangDua = "2nd");
      } else this.orangDua = "1st";
    },
    mengulang() {
      this.angkaSatu = 0;
      this.angkaDua = 0;
      this.orangSatu = "1st";
      this.orangDua = "";
    },
    pindah() {
      let sementara = this.orangSatu;
      this.orangSatu = this.orangDua;
      this.orangDua = sementara;

      let sementara1 = this.angkaSatu;
      this.angkaSatu = this.angkaDua;
      this.angkaDua = sementara1;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;700&family=Quicksand:wght@500&display=swap");
#div-1 {
  background-color: rgb(4, 88, 4);
  min-height: 100vh;
  font-family: "Montserrat", sans-serif;
}
.araya1 {
  background-color: rgb(0, 0, 0);
  color: white;
  margin-right: 4px;
  padding-top: 20px;
  padding-bottom: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.araya2 {
  background-color: rgb(0, 0, 0);
  text-align: center;
  color: white;
  margin-left: 4px;
  padding-top: 20px;
  padding-bottom: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.araya3 {
  background-color: rgb(0, 0, 0);

  color: white;
  margin-right: 4px;
  padding-top: 10px;
  padding-bottom: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.araya4 {
  background-color: rgb(0, 0, 0);

  color: white;
  margin-left: 4px;
  padding-top: 10px;
  padding-bottom: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.araya5 {
  background-color: rgb(0, 0, 0);

  color: white;
  margin-right: 4px;
  padding-top: 30px;
  padding-bottom: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.araya6 {
  background-color: rgb(0, 0, 0);

  color: white;
  margin-left: 4px;
  padding-top: 30px;
  padding-bottom: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.araya7 {
  background-color: rgb(0, 0, 0);

  color: white;
  margin-right: 4px;
  padding-top: 30px;
  padding-bottom: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.araya8 {
  background-color: rgb(0, 0, 0);

  color: white;
  margin-left: 4px;
  padding-top: 30px;
  padding-bottom: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.counter-utama {
  background-color: rgb(2, 59, 2);
  padding: 12px 0px 12px 0px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 5%;
}

.warna1 {
  color: white;
  font-style: italic;
}
.row-3 {
  padding: 30px;
  padding-top: -300px;
}
.row-4 {
  padding: 30px;
  padding-top: -300px;
}

.borad-5 {
  border-radius: 5%;
}

.font-custom {
  font-size: 70px;
  font-style: italic;
}
.font-custom1 {
  font-size: 20px;
  font-style: italic;
}
.font-custom2 {
  font-size: 40px;
  font-style: italic;
}
</style>
