<template>
  <div class="text-center">
    <div class="circle-badge" style="background:#c4d735">
      <strong style="font-family: 'Oswald', sans-serif;  font-size: 28px;  font-weight: bold;" >{{ value }}</strong>
    </div>
    <div>
      <small class="mtitle">{{ title }}</small>
    </div>
  </div>
</template>

<script>
import MQS from 'mongodb-querystring'
import clone from 'clone'
export default {
  props: ['query', 'title', 'mode'],
  mounted () {
    // const self = this
    // self.reload()
    this.$nextTick(this.reload)
  },
  data () {
    return {
      value: 0
    }
  },
  methods: {
    reload (done) {
      const self = this
      const qry = {
      }
      const url = window.location.protocol
      .concat('//')
      .concat(window.location.host)
      .concat('/' + self.query)
      .concat('&' + MQS.stringify(qry, {}))
      self.$http.get(url).then(function (response) {
        if (self.mode === 'value') {
          self.value = clone(response.data[0].value)
        }
        else {
          self.value = clone(response.data.length)
        }
      })
    }
  }
}
</script>
<style>
.mtitle {
  font-family: 'Oswald', sans-serif;
  font-size: 14px;
  text-transform: uppercase;
}
</style>
