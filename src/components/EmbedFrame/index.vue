<template>
  <div class="embed-responsive" :class="prefixCls" v-if="valid">
    <iframe loading="lazy" sandbox="allow-forms allow-scripts allow-pointer-lock allow-same-origin allow-top-navigation allow-presentation" class="embed-responsive-item" allowfullscreen :src="url"></iframe>
  </div>
</template>

<script>
export default {
  props: {
    prefixCls: { type: String, default: '' },
    src: { type: String },
    params: { type: Object }
  },

  data () {
    return {
      valid: false,
      url: '',
      videos: []
    }
  },

  watch: {
    src (val) {
      this.parse()
    }
  },
  mounted () {
    this.parse()
  },

  methods: {
    parse () {
      if (this.src) {
        this.url = this.src
        this.valid = true
        return
      }

      this.valid = false
    }
  }
}
</script>
