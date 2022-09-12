<template>
  <ChildSlot>
    <!-- En el child utilizo un template con el v-slot relacionado al name, y lo igualo a la variable con los datos que tengo -->
    <template v-slot:item="{body,username,likes}"><!-- #item-->
        <h3>{{body}}</h3>
        <p>by {{username}} | {{likes}} likes</p>
    </template>
  </ChildSlot>
</template>

<script lang="ts">
import ChildSlot from './ChildSlot.vue';
export default {
    name: "parent-slot-component",
    components: { ChildSlot }
}
</script>

<style>

</style>