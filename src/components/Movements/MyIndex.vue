<template>
  <div class="movements">
      <h2 class="title">Historial</h2>
      <div class="content">
          <Movement
              v-for="movement in movements"
              :key="movement.id"
              :id="movement.id"
              :title="movement.title"
              :description="movement.description"
              :amount="movement.amount"
              @remove="remove"
          />
      </div>
  </div>
</template>

<script setup>
import { toRefs, defineProps } from 'vue';
import Movement from './MyMovement.vue';

const props = defineProps({
  movements: {
    type: Array,
    // se ejecuta la funcion default cada que necesita reactividad
    default: () => [],
  },
});
/**
 * toRefs is useful when returning a reactive object from
 * a composable function so that the consuming component
 * can destructure/spread the returned object without losing reactivity
 */
const { movements } = toRefs(props);

const remove = (id) => {
  console.log('remove', id);
};

</script>

<style scoped>
.movements {
  max-height: 100%;
  padding: 0 8px;
  margin-bottom: 14px;
}

.title {
  margin: 8px 16px 24px 16px;
  color: var(--brand-blue);
}

.content {
  max-height: 68vh;
  display: flex;
  flex-direction: column;
  gap: 8px;
  overflow-y: scroll;
}
</style>
