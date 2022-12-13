<template>
  <div>
    <input
      type="search"
      name=""
      id=""
      @keyup="checkEnter($event)"
      v-model="searchText"
    />
    <button @click="doSearch($event)">조회</button>
    <p></p>
    <input
      type="search"
      name=""
      id=""
      @keyup.enter="doSearch($event)"
      v-model="searchText"
    />
    <button @click="doSearch($event)">조회keyup.enter 이용</button>
  </div>
</template>
<script>
export default {
  components: {},
  data() {
    return {
      searchText: ''
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {
    doSearch(event) {
      console.log(event.target.tagName)
      console.log(this.searchText)
    },
    checkEnter(event) {
      console.log(event.target.tagName)
      if (event.keyCode === 13) {
        this.doSearch(event)
      }
    }
  }
}
</script>
