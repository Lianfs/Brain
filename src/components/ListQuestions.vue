<template>
  <div class="container">
    <QuestionCard/>
    <h6 style="margin: 30px">Mostrar Mais</h6>
  </div>
</template>
<script>
import QuestionCard from "./QuestionCard.vue";

export default {
  props: ['Perguntas'],
  components: {
    QuestionCard,
  },
};
</script>

<style scoped>
.container {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-top: 3%;
  max-height: 100%;
  border: 2px solid rgba(128, 128, 128, 0.281);
  border-radius: 8px;
  margin-bottom: 20px;
}
</style>