<template>
  <div class="home">
    <Button type="primary" v-on:click="increment()">counter | {{count}}</Button>
    <Button type="warning" v-on:click="callApi">发请求</Button>
  </div>
</template>

<script>
/* eslint-disable */
// @ is an alias to /src
import { mapState, mapMutations, mapActions } from 'vuex'
import { MUTATION } from '../constants'

export default {
  name: 'home',
  components: {
  },
  computed: {
    ...mapState('global', [
      'count',
    ])
  },
  methods: {
    ...mapActions('global', [
      'callApi'
    ]),
    ...mapMutations('global', {
      //onclick中直接使用increment方法名会默认传入event对象到payload
      increment: MUTATION.INCREMENT
    })
  }
}
</script>



<!--
// 直接通过this.$store访问state,getters,mutations,actions
// getName() {
//   // 异步
//   this.$store.dispatch('global/getName')
// },
// tigger() {
//   // 同步
//   this.$store.commit('global/test', {xxx: 23424})
// }
-->


