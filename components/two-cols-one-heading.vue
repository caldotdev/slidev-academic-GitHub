
<!--
  Usage:

```md
---
layout: two-cols-one-heading
---

# Heading

::left::

# Left

This shows on the left

::right::

# Right

This shows on the right
```

-->

<script setup lang="ts">
const props = defineProps({
  class: {
    type: String,
  },
})
</script>

<template>
  <div class="slidev-layout">
    <slot />
    <div class="two-columns w-full h-full grid grid-cols-2 space-x-8">
      <div class="col-left" :class="props.class">
        <slot name="left"/>
      </div>
      <div class="col-right" :class="props.class">
        <slot name="right" />
      </div>
    </div>
  </div>
</template>
