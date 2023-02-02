<script lang="ts">
import formatRelative from "date-fns/formatRelative";
import { defineComponent } from "vue";
import type Entry from "@/types/Entry";
import type { PropType } from "vue";
export default defineComponent({
  props: {
    date: { type: Date, required: true },
  },
  emits:{
    doSomething(payload:Entry){
      return true;
    }
  },
  computed: {
    formatted():String {
      return formatRelative(this.date, Date.now());
    },
  },
  mounted(){
    this.formatted;
  }
});
</script>
<template>
  <div>{{ formatted }}</div>
</template>
