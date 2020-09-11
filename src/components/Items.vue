<template>
  <div class="items">
    <div v-for="(items, index) in itemInfo"
    :class="{'active': index===0}" 
    v-bind:key="items.id" class="carousel-item">
      <Item v-bind:items="items"/>
    </div>
  </div>
</template>

<script>
import Item from './Item'

export default {
  name: "Items",
  components: {
    Item
  },
  props: ["itemInfo"],
};
</script>