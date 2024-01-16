<template>
  <el-button
    type="primary"
    v-bind="{ ...$attrs }"
    link
    size="small"
    @click="showFlag = !showFlag"
  >
    {{ titleCom }}
    <el-icon v-show="showFlag">
      <ArrowUpBold />
    </el-icon>
    <el-icon v-show="!showFlag">
      <ArrowDownBold />
    </el-icon>
  </el-button>
</template>

<script setup lang="ts">
import {computed, ref} from "vue";
import { ArrowUpBold, ArrowDownBold } from '@element-plus/icons-vue';
const props = defineProps({
  title: {
    type: String,
    default: "详情",
  },
});
const showFlag = ref(false);
const titleCom = computed(() => {
  return showFlag.value ? `${props.title}收起` : `${props.title}展开`;
});
</script>
<style scoped>
.link {
  cursor: pointer;
  color: #17bade;
}
</style>
