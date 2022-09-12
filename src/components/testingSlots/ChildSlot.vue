<template>
  <ul >
    <li v-if="!items.length">...loading</li>
    <li v-for="item in items" :key="item.id">
        <!--{{item}}-->
        <!--donde va {{item}} pongo un slot tag con un name y binding el item que voy a utilizar en el parent-->
        <slot name="item" v-bind="item"></slot>

    </li>
  </ul>
</template>

<script lang="ts">
import { defineComponent } from 'vue'


export default defineComponent({
    name: 'child-slot-component',
    data() {
    return {
        items: [] as { id: number, body: string, username: string, likes: number }[]
    }
  },
    mounted() {
        setTimeout(() => {
            this.items = [
                { id: 1 ,body: 'Scoped Slots Guide', username: 'Evan You', likes: 20 },
                { id: 2, body: 'Vue Tutorial', username: 'Natalia Tepluhina', likes: 10 }
            ]
        }, 1000)
    },
})
</script>

<style  scoped>
    ul{
        list-style-type: none;
    }

</style>