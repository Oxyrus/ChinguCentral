<template>
  <section class="hero">
    <div class="hero-body">
      <div class="container">
        <h1 class="title">
          Cohorts
        </h1>
        <h2 class="subtitle">
          There are dozens of cohorts, find the one that suits you best
        </h2>

        <div class="columns is-multiline row">
          <individual-cohort
            v-for="cohort in cohorts"
            :cohort="cohort"
            :key="cohort.id"
          ></individual-cohort>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import IndividualCohort from '@/components/cohort/IndividualCohort'

export default {
  name: 'cohort-list',

  components: {
    IndividualCohort
  },

  computed: {
    cohorts () {
      return this.$store.state.cohort.cohorts
    }
  },

  mounted () {
    this.$store.dispatch('LOAD_COHORTS_LIST')
  }
}
</script>
