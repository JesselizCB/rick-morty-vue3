<template>
  <div>
    <FilterByStatus />
    <FilterByName />
    <section>
      <div v-for="character in characters" :key="character.id">
        <CardCharacter :character="character" />
      </div>
    </section>
  </div>
</template>

<script>
import { computed, onMounted } from 'vue';
import { useStore } from 'vuex';
import CardCharacter from '@/components/CardCharacter.vue';
import FilterByStatus from '@/components/FilterByStatus.vue';
import FilterByName from '@/components/FilterByName.vue';

export default {
  components: {
    CardCharacter,
    FilterByStatus,
    FilterByName
  },
  setup () {
    const store = useStore()
    const characters = computed(() => {
      return store.state.charactersFilter
    })
    onMounted(() => {
      store.dispatch('getCharacters')
    })

    return {characters}
  }
}
</script>

<style lang="scss" scoped>

</style>