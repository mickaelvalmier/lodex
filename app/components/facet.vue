<template>
  <div>
    <hr />
    <h3>{{ title }}</h3>
    <ul class="nav nav-pills nav-stacked">
      <li v-for="item in items" class="">
        <span class="badge pull-right">{{ item.value }}</span><a href="#">{{ item._id }}</a>
      </li>
    </ul>
  </div>
</template>

<script>
import MQS from 'mongodb-querystring'
import clone from 'clone'
export default {
  props: ['field', 'title'],
  mounted () {
    // const self = this
    // self.reload()
    this.$nextTick(this.reload)
  },
  data () {
    return {
      items: []
    }
  },
  methods: {
    reload (done) {
      const self = this
      const qry = {
        field: '_columns.' + self.field + '.content',
        $limit: 5,
        $sort: {
          value: -1
        }
      }
      const url = window.location.protocol
      .concat('//')
      .concat(window.location.host)
      .concat('/$distinct?')
      .concat(MQS.stringify(qry, {}))
      self.$http.get(url).then(function (response) {
        self.items = clone(response.data)
      })
    }
  }
}
</script>
