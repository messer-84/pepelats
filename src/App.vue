<template>
	<div>
		<top-menu v-show="currentRouter != '/'"></top-menu>
		<router-view></router-view>
	</div>
</template>

<script>
  import topMenu from './components/topMenu.vue'
  import {router} from './app'

  export default {
    data(){
      return {
        currentRouter: router.currentRoute.path
      }
    },
    components: {
      topMenu
    },
    watch: {
      '$route' (to, from) {
        this.currentRouter = to.path
      }
    }
  }

</script>

<style>

</style>
