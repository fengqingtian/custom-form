<template>
  <WidgetDecorator :widget="widget">
    <WidgetLayout :widget="widget" :isDesign="true">
      <el-input-number :placeholder="widget.placeholder" :modelValue="widget.defaultValue" style="width:140px" />
      <span style="margin-left: 5px;">{{ widget.unit }}</span>
    </WidgetLayout>
  </WidgetDecorator>
</template>

<script setup lang="ts">
import Widget from './Widget';
import WidgetDecorator from '../base/design/WidgetDecorator.vue';
import WidgetLayout from '../base/WidgetLayout.vue';

defineProps<{
  widget: Widget
}>();
</script>

<style lang="less" scoped></style>
