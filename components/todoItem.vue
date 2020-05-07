<template>
  <text>
    {{ item.id }}. {{ item.title }}
  </text>
</template>

<script type="text/javascript">
export default {
  props: {
    item: {
      Type: Object,
    }
  }
};
</script>
