<template>
  <div>
    <Navbar></Navbar>
    <Body></Body>
  </div>
</template>

<script>
import Navbar from '@/components/layouts/Navbar.vue'
import Body from '@/components/body/Content.vue'
export default {
  components: {
    Navbar,
    Body
  }
}
</script>