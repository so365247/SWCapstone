<template>
    <v-container fluid>
      <v-app-bar>
        <img src="@/assets/입체 로고.png" alt="Logo" class="logo" />
        <v-btn>계정 관리</v-btn>
        <v-btn>CCTV 관리</v-btn>
        <v-btn>사용자 관리</v-btn>
      </v-app-bar>
      <div>
        <h3>기상정보</h3>
        <div class="weather-info-card">
            <p class="letter">온도:<span class="wether-info">20</span></p>
            <p class="letter">습도:<span class="wether-info">62%</span></p>
            <p class="letter">풍량:<span class="wether-info">200</span></p>
            <p class="letter">강수량:<span class="wether-info">210mm</span></p>
        </div>
      </div>

      <div>
        <h3>화재 위험 지역 정보</h3>
        <div class="local-info-card">

        </div>
      </div>

      <div>
          <h3>지도</h3>
          <div id="map" class="map" style="width: 560px; height: 768px; border-radius: 13px;"></div>
      </div>
    </v-container>
  </template>
  
  <script>
export default {
  mounted() {
    console.log("Vue mounted");

    if (typeof kakao === 'undefined') {
      console.log("카카오 지도 스크립트 로드 시작");

      const script = document.createElement('script');
      script.src = "//dapi.kakao.com/v2/maps/sdk.js?appkey=7287e30fdbe7200a54db305e55034cce&autoload=false";
      script.onload = () => {
        console.log("카카오 스크립트 로드 완료");
        kakao.maps.load(() => {
          console.log("카카오 맵 로드 완료, initMap 실행");
          this.initMap();
        });
      };
      document.head.appendChild(script);
    } else {
      console.log("이미 로드됨, initMap 실행");
      this.initMap();
    }
  },
  methods: {
    initMap() {
      const container = document.getElementById('map');
      const options = {
        center: new kakao.maps.LatLng(37.532600, 127.024612),
        level: 3
      };
      new kakao.maps.Map(container, options);
    }
  }
};
</script>

  

<style>
html, body {
    margin: 0;
    padding: 0;
    height: 100vh;
}

.v-application {
    margin: 0 !important;
    padding: 0 !important;
}

.v-app-bar {
    background-color: #A30505 !important;
}

.logo {
    margin-left: 14px;
    width: auto;
    height: 35px;
}

.v-container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background-color: #FBFBFB;
}

.weather-info-card{
    width: 300px;
    height: 400px;
    padding: 20px;
    background-color: #FFFFFF;
    border-radius: 13px;
    display: flex;
    justify-content: center;
    flex-direction: column;
    text-align: center;
    margin-right: 20px;
    box-shadow: 0px 4px 11px -3px rgba(0, 0, 0, 0.31);
}
.map{
    box-shadow: 0px 4px 11px -3px rgba(0, 0, 0, 0.31);
}

h3{
    color: black;
}

.letter{
    text-align: center;
    white-space: pre-line;
    color: black;
    font-size: 20px;
    font-weight: bold;
    margin-right: 10px;
}

.wether-info {
    margin-left: 20px;
    color: cadetblue;
    font-size: 20px;
    font-weight: 300;
}

.local-info-card {
    height: 400px;
    width: 300px;
    display: flex;
    justify-content: center;
    flex-direction: column;
    text-align: center;
    margin-right: 20px;
    border-radius: 13px;
    background-color: #FFFFFF;
    box-shadow: 0px 4px 11px -3px rgba(0, 0, 0, 0.31);
}


</style>

<script>

</script>