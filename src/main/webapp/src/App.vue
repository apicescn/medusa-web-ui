<template>
  <a-config-provider>
    <router-view></router-view>
  </a-config-provider>
</template>
<script>
import {computed, defineComponent, ref} from "vue";
import {useStore} from "vuex";
// import {useI18n} from 'vue-i18n/index';
export default defineComponent({
  name: 'App',
  setup() {
    const store = useStore()
    const defaultLang = computed(() => store.getters['app/language'])
    const color = computed(() => store.getters.color);

    // const antdLocal = ref(
    //   computed(() => {
    //     const { getLocaleMessage } = useI18n({ useScope: 'global' })
    //     return  getLocaleMessage(defaultLang.value).antdLocal
    //   })
    // )

    // return {
    //   antdLocal
    // }
  }
})
</script>
<style>
#app, body, html {
  height: 100%;
}
</style>