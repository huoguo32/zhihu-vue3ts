<template>
  <div class="dropdown">
  <a href="#" class="btn btn-outline-light my-2 dropdown-toggle" >
    {{title}}
  </a>
  <ul class="dropdown-menu" aria-labelledby="dropdownMenuLink">
    <li><a class="dropdown-item" href="#">Action</a></li>
    <li><a class="dropdown-item" href="#">Another action</a></li>
    <li><a class="dropdown-item" href="#">Something else here</a></li>
  </ul>
  </div>
</template>
<script lang='ts'>
import { reactive, toRefs, onBeforeMount, onMounted, defineComponent, ref } from 'vue'
export default defineComponent({
  name: 'Drop-down',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup () {
    console.log('Drop-down setup')
  }
})

</script>
<style lang="scss" scoped>

</style>
