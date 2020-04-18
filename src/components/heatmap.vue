<template>
  <div style="width:100%; margin-bottom:2em">
    <h1>{{ user }}</h1>
    <calendar-heatmap :end-date="end" :values="commits" :max="max" />
    <p>{{ totalCommits() }} Commits ({{ format_date(start) }} - {{ format_date(end) }})</p>
  </div>
</template>

<script>
import '@/libs/vue-calendar-heatmap.css'
import { CalendarHeatmap } from '@/libs/vue-calendar-heatmap.common'
import moment from 'moment'
export default {
  name: 'Heatmap',
  components: { CalendarHeatmap },
  props: {
    commits: Array,
    user: {
      type: String,
      default: 'Toby Qin'
    }
  },
  methods: {
    format_date(value) {
      if (value) {
        return moment(String(value)).format('YYYY/MM/DD')
      }
    },
    totalCommits() {
      var total = 0

      var s = '9999-01-01'
      var e = '0000-00-00'
      for (var day of this.commits) {
        var currentDate = moment(String(day.date)).format('YYYY-MM-DD')
        if (currentDate > e) {
          e = currentDate
        }
        if (currentDate < s) {
          s = currentDate
        }
        total += day.count
      }
      this.start = s
      this.end = e
      return total
    }
  },
  data: () => {
    return {
      start: '',
      end: '',
      max: 6
    }
  },
  computed: {}
}
</script>
