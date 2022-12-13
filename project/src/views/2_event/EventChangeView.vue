<template>
  <div>
    <!-- <select name="" id="" @change="changeCity" v-model="selectedCity"></select> -->
    <select
      name=""
      id=""
      v-on:change="changeCity($event)"
      v-model="selectedCity"
    >
      <option value="">==도시선택체인지이벤트==</option>
      <option
        :value="city.cityCode"
        :key="city.cityCode"
        v-for="city in cityList"
      >
        {{ city.title }}
      </option>
    </select>
    <select name="" id="">
      <option value="">==동선택==</option>
      <option
        :value="dong.dongCode"
        :key="dong.dongCode"
        v-for="dong in selectedDongList"
      >
        {{ dong.dongTitle }}
      </option>
    </select>
    <p></p>
    <select name="" id="" v-model="selectedCity">
      <option value="">==도시선택내부함수==</option>
      <option
        :value="city.cityCode"
        :key="city.cityCode"
        v-for="city in cityList"
      >
        {{ city.title }}
      </option>
    </select>
    <select name="" id="">
      <option value="">==동선택2==</option>
      <option
        :value="dong.dongCode"
        :key="dong.dongCode"
        v-for="dong in dongList.filter(
          (dong) => dong.cityCode === selectedCity
        )"
      >
        {{ dong.dongTitle }}
      </option>
    </select>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      cityList: [
        { cityCode: '02', title: '서울' },
        { cityCode: '051', title: '부산' },
        { cityCode: '064', title: '제주' }
      ],
      dongList: [
        { cityCode: '02', dongCode: '1', dongTitle: '화곡1동' },
        { cityCode: '02', dongCode: '2', dongTitle: '화곡2동' },
        { cityCode: '02', dongCode: '3', dongTitle: '화곡3동' },
        { cityCode: '02', dongCode: '4', dongTitle: '화곡4동' },
        { cityCode: '02', dongCode: '5', dongTitle: '화곡5동' },
        { cityCode: '051', dongCode: '1', dongTitle: '해운대' },
        { cityCode: '051', dongCode: '2', dongTitle: '광안리' },
        { cityCode: '064', dongCode: '1', dongTitle: '월정리' }
      ],
      selectedCity: '',
      selectedDongList: []
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    changeCity(e) {
      console.log(e.target.tagName)
      this.selectedDongList = this.dongList.filter(
        (dong) => dong.cityCode === this.selectedCity
      )
    }
  }
}
</script>
