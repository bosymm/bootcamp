<template>
  <div>
    <div>
      <input type="checkbox" id="html" value="HTML" v-model="favriteLang" />
      <label for="html">Html</label>
    </div>
    <div>
      <input type="checkbox" id="css" value="CSS" v-model="favriteLang" />
      <label for="css">CSS</label>
    </div>
    <div>
      <input type="checkbox" id="js" value="JS" v-model="favriteLang" />
      <label for="js">JS</label>
    </div>
    <div>선택한 언어 : {{ favriteLang }}</div>
  </div>
</template>
<script>
export default {
  // name:'',
  components: {},
  data() {
    return {
      favriteLang: ['CSS']
    }
  },
  setup() {},
  created() {},
  mounted() {},
  unmounted() {},
  methods: {}
}
</script>
