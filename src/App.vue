<template>
  <elem-list class="elem-list"/>
  <google-map class="google-map"/>
</template>

<script>

import ElemList from "@/components/ElemList.vue"
import GoogleMap from "@/components/GoogleMap"

export default {
  components: {
    GoogleMap,
    ElemList
  },
  data() {
    return {}
  }
}
</script>

<style lang="scss">
#app {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  grid-template-rows: 1fr;
  grid-gap: 0;
}

.elem-list {
  display: flex;
  flex-direction: column;
}

.google-map {

}
</style>
