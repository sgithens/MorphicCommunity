<template>
  <Div id="BarsList">
    <ul v-if="orderedBars.length > 0" class="list-unstyled">
      <li v-for="bar in orderedBars" :key="bar.id" :class="{ active: bar.id === activeBarId }">
        <b-link v-if="bar.is_shared" :to="{ name: 'MorphicBar Editor', query: { barId: bar.id } }">
         {{ bar.name === "Default" ? "Starter Bar" : bar.name }}
        </b-link>
      </li>
    </ul>
    <p v-else>
      <i>No bars in the community</i><br>
      Click on the plus button just above to add your first one
    </p>
  </div>
</template>

<style lang="scss">
  #BarsList {
    ul {
      margin: 0 -1rem 1rem -1rem;
      li {
        padding: 0 1rem;
        &.active {
          padding: .25rem 1rem;
          background: green;
          a {
            color: white;
          }
        }
      }
    }
  }
</style>

<script>

export default {
  name: 'BarsList',
  props: {
    bars: Array,
    activeBarId: String
  },
  computed: {
    orderedBars: function () {
      const alphabetical = this.bars
      alphabetical.sort((a, b) => (a.name < b.name) ? 1 : ((a.name > b.name) ? -1 : 0))
      alphabetical.reverse()
      alphabetical.sort((a, b) => a.name === 'Default' ? -1 : b.name === 'Default' ? 1 : 0)
      return alphabetical
    }
  }
}
</script>
