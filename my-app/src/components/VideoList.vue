<template>
  <div class="hello">
    <ul>VideoList {{ videos.length }} </ul>
  </div>
</template>

<script>
export default {
  name: 'VideoList',
  props: ['videos']
}
</script>