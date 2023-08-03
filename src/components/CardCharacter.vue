<template>
  <div class="character">
    <img :src="character.image" :alt="character.name">
    <div>
      <h3>{{character.name}}</h3>
      <div>
        <span :class="character.status == 'Alive' ? 'alive':
        character.status == 'Dead' ? 'dead':'default'">{{character.status}}</span>
        <span> {{ character.species }}</span>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['character']
}
</script>

<style lang="scss" scoped>

</style>