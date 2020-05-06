<template>
  <text>
    {{ item.id }}. {{ item.text }}
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
