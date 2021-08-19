<template>
<div class="w-100">
  <img :src="requestImg(componente.imagens[0].imgUrl)" alt="" class="w-100"/>
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
  data(){
    return{
      mobile:false
    }
  },
  methods: {
    requestImg(img) {
      if (this.SITE_STATICO === false && this.componente.imagens !== undefined && img!==null && img!==undefined) {
          return this.API_URL + "/images/" + img;
          
       }// else return require("~/assets/imagens/" + img);
    },
  },
};
</script>