<template>
  <transition>
    <router-view />
  </transition>
</template>

<script>
import MainLayout from '~/layouts/Main.vue'

export default {
  components: {
    MainLayout
  }
}
</script>

 
<static-query>
query {
  metadata {
    siteName
    siteDescription
  }
}
</static-query>

<script>
export default {
  metaInfo() {
    return {
      title: this.$static.metadata.siteName,
      meta: [
        {
          key: 'description',
          name: 'description',
          content: this.$static.metadata.siteDescription
        }
      ]
    }
  }
}
</script>
