<template>
  <div class="container-question">
    <div class="photo"></div>
    <h5
      style="
        position: absolute;
        display: flex;
        font-size: 15px;
        line-height: 20px;
        font-weight: 700;
        color: black;
        margin-top: 25px;
        margin-left: 65px;
        display:inline-block;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        max-width: 15em;
      "
    >
      {{ arrayPerguntas.username }}
    </h5>
    <h5
      style="
        position: absolute;
        display: flex;
        font-size: 12px;
        line-height: 16px;
        color: #687b8c;
        font-weight: 400;
        margin-top: 45px;
        margin-left: 65px;
        display:inline-block;
        white-space: nowrap;
        overflow: hidden;
        text-overflow: ellipsis;
        max-width: 22em;
      "
    >
      há 3 minutos - {{ arrayPerguntas.category }}
    </h5>
    <h3
      style="
        position: absolute;
        display: flex;
        font-size: 15px;
        line-height: 30px;
        font-weight: 500;
        color: #000;
        margin-top: 75px;
        margin-left: 10px;
        margin-bottom: 20px;
        display:block;
        overflow: hidden;
        text-overflow: ellipsis;
        max-width: 63em;
        max-height: 110px;
        text-align:left;
      "
    >
      {{ arrayPerguntas.text }}
    </h3>
  </div>
</template>

<script>
export default {
  props: ["arrayPerguntas"],
};
</script>

<style scoped>
.container-question {
  width: 102%;
  height: 13em;
  display: flex;
}

.photo {
  position: relative;
  width: 40px;
  height: 40px;
  background: gray;
  border-radius: 50%;
  margin-top: 20px;
  margin-left: 15px;
}
</style>