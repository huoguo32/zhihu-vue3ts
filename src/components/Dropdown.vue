<template>
  <div class="dropdown" ref="dropdownRef">
  <a href="#" class="btn btn-outline-light my-2 dropdown-toggle" @click.prevent="toggleOpen">
    {{title}}
  </a>
  <ul class="dropdown-menu" aria-labelledby="dropdownMenuLink" :style="{display:'block'}" v-if="isOpen">
    <slot></slot>
  </ul>
  </div>
</template>
<script lang='ts'>
import { onMounted, defineComponent, ref, onUnmounted, watch } from 'vue'
import useClickOutside from '../hooks/useClickOutside'
export default defineComponent({
  name: 'Drop-down',
  props: {
    title: {
      type: String,
      required: true
    }
  },
  setup () {
    const isOpen = ref(false)
    const dropdownRef = ref<null | HTMLElement>(null)
    const toggleOpen = () => {
      isOpen.value = !isOpen.value
    }
    const isClickOutside = useClickOutside(dropdownRef)
    watch(isClickOutside, (newvalue) => {
      console.log('666', newvalue)
      if (isOpen.value && isClickOutside.value) {
        isOpen.value = false
      }
    }
    )
    return {
      isOpen,
      toggleOpen,
      dropdownRef
    }
  }
})

</script>
<style lang="scss" scoped>

</style>
