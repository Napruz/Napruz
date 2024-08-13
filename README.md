<template>
  <q-expansion-item
    v-for="category in categories"
    :key="category.id"
    :icon="category.icon"
    :label="removeNbsp(category.text)"
    class="text-white link-text"
    label-class="text-white"
    icon-class="text-white"
    :expand-icon-class="expandIconClass(category)"
    :model-value="openedItem === category.id"
    @update:model-value="(value) => onItemToggle(category.id, value)"
  >
    <!-- ... (остальное содержимое q-expansion-item) ... -->
  </q-expansion-item>
</template>

<script>
import { ref, onMounted, computed } from "vue";
import { useRouter } from "vue-router";
import axios from "axios";

export default {
  name: "MyLayout",
  setup() {
    // ... (другие переменные) ...

    const expandIconClass = computed(() => (category) => {
      return category.parent_id === '' ? 'q-pa-none' : 'text-white';
    });

    // ... (остальной код) ...
  }
};
</script>
