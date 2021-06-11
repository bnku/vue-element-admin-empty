<template>
  <div class="dashboard-container">
    <aside>Welcome {{ roles }}</aside>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'

export default {
  name: 'Dashboard',
  data() {
    return {
      currentRole: 'adminDashboard'
    }
  },
  computed: {
    ...mapGetters([
      'roles'
    ])
  },
  created() {
    if (!this.roles.includes('admin')) {
      this.currentRole = 'editorDashboard'
    }
  }
}
</script>

<style lang="scss" scoped>
.dashboard-container {
  margin: 30px 20px 0;
  overflow: hidden;
}
</style>
