<template>
  <ul>
    <li v-for="column in list " :key="column.id">
    <img :src="column.avatar" :alt="column.title">
    <h5>{{column.title}}</h5>
    <p>{{column.description}}</p>
    <a href="#">进入专栏</a>
    </li>
  </ul>
</template>
<script lang="ts">
import {
  reactive,
  toRefs,
  onBeforeMount,
  onMounted,
  defineComponent,
  ref,
  PropType
} from 'vue'
export interface ColumnProps {
  id: number
  title: string
  description: string
  avatar: string
}
export default defineComponent({
  name: 'App',
  props: {
    list: {
      type: Array as PropType<ColumnProps[]>,
      required: true
    }
  },
  setup (props, content) {
    // props.list[0].id
  }
})
</script>
<style lang="scss" scoped></style>
