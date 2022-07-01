<template>
  <div v-for="elem in elements" :key="elem">
    <element-carousel :elem="elem"/>
  </div>
</template>

<script>
import {defineComponent} from "vue"
import ElementCarousel from "@/components/ElementCarousel";

export default defineComponent({
  name: "elem-list",
  components: {ElementCarousel},
  data() {
    return {
      elements: []
    }
  },
  async mounted() {
    const csv = await (await fetch("/exercice_lekaba.csv")).text()

    const lines = csv.split("\n")

    if (lines.length >= 1) {
      const keys = lines.shift()?.split(",")
      console.log(keys)

      for (const line of lines) {
        if (line !== "") {
          let items = line.split(",");
          items.pop()

          let data = {}
          for (let i = 0; i < items.length; i++) {
            data[keys[i]] = items[i].indexOf('|') > -1 ? items[i].split('|') : items[i]
          }
          this.elements.push(data)
        }
      }
    }
  }

})
</script>
