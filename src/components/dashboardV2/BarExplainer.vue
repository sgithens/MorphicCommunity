<template>
  <div id="barExplainer" class="bg-silver rounded mt-3 ml-3 p-3">
    <p>
      <b-icon-info-circle-fill></b-icon-info-circle-fill>&nbsp;
      <span v-if="barDetails.name === 'Default'">The <b>Starter Bar</b> is the first bar that an invited community member will see.</span>
    </p>
    <b-embed
      type="iframe"
      aspect="16by9"
      src="https://www.youtube.com/embed/hMWnf65uicc"
      allowfullscreen
    ></b-embed>
    <p class="mt-3 mb-0">Learn how to customize the <b>{{ barDetails.name === 'Default' ? 'Starter Bar' : barDetails.name }}</b> to fit the needs of your community.</p>
  </div>
</template>

<style lang="scss">
  #barExplainer {
    font-size: .85rem;
    .b-icon {
      font-size: 2rem;
    }
  }
</style>

<script>

export default {
  name: 'BarExplainer',
  props: {
    barDetails: Object
  }
}
</script>
