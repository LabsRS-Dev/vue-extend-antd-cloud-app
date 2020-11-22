<template>
  <div>
    <a-result status="401" title="401" sub-title="Sorry, you don't have access to this page.">
      <template #extra>
        <a-button type="primary" @click="toHome">
          Back Home
        </a-button>
      </template>
    </a-result>
    <EmbedFrame :src="url" @load="onLoad"></EmbedFrame>
  </div>
</template>

<script>

import { EmbedFrame } from '@/components'

export default {
  name: 'Exception401',
  data () {
    return {
      url: 'http://www.bing.com'
    }
  },
  methods: {
    toHome () {
      this.$router.push({ path: '/' })
    },
    onLoad () {
      console.log('------> onload')
    }
  },
  components: {
    EmbedFrame
  }
}
</script>
