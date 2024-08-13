<template>
  <q-expansion-item
    v-for="category in categories"
    :key="category.id"
    :icon="category.icon"
    :label="removeNbsp(category.text)"
    class="text-white link-text"
    label-class="text-white"
    icon-class="text-white"
    :expand-icon-class="category.parent_id === '' ? 'q-pa-none' : 'text-white'" 
    :model-value="openedItem === category.id"
    @update:model-value="(value) => onItemToggle(category.id, value)"
  >
    <!-- ... (остальное содержимое q-expansion-item) ... -->
  </q-expansion-item>
</template>

<script>
// ... (другой код) ...

setup() {
  // ... (другие переменные) ...

  const categories = ref([
    { id: 1, text: 'Категория 1', icon: 'fa-solid fa-home', parent_id: '' },
    { id: 2, text: 'Категория 2', icon: 'fa-solid fa-user', parent_id: '' },
    { id: 3, text: 'Подкатегория 1', icon: 'fa-solid fa-folder', parent_id: 1 },
    { id: 4, text: 'Подкатегория 2', icon: 'fa-solid fa-file', parent_id: 1 },
  ]);

  // ... (остальной код) ...
}
</script>
