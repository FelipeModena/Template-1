<template>
<div class="map-responsive w-100">
    <div class="my-4 mb-2 container w-100 "  v-html="componente.urlBotao1" ></div>

</div>
</template>

<script>
export default {
  props: {
    componente: {
      type: Object,
      default: () => {},
    },
  },
}
</script>

<style scoped>
.map-responsive{
        position: relative;
        padding-bottom: 75%; 
        height: 0;
        overflow: hidden;

}

.map-responsive iframe{
        position: absolute;
        top: 0;
        left: 0;
        width: 100% !important;
        height: 100% !important;

}
</style>