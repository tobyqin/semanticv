<template>
  <div style="width:100%; margin-bottom:2em">
    <h1>{{ user }}</h1>
    <calendar-heatmap :end-date="end" :values="commits" :max="max" />
    <p>
      {{ totalCommits() }} Commits ({{ format_date(start) }} -
      {{ format_date(end) }})
    </p>
  </div>
</template>

<script>
import 'vue-calendar-heatmap/dist/vue-calendar-heatmap.css'
import { CalendarHeatmap } from 'vue-calendar-heatmap'
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
      var len = this.commits.length
      var counter = 0
      for (var day of this.commits) {
        if (counter == 0) {
          this.start = day.date
        } else if (counter == len - 1) {
          this.end = day.date
        }
        total += day.count
        counter += 1
      }
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
