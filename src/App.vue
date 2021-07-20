<template>
  <Header />
  <Categories />
  <div
    class="container newQuestionButton"
    style="background-color: #198754"
    v-if="this.statusNovaPergunta == false"
    @click="this.statusNovaPergunta = true"
  >
    <h4
      style="
        font-size: 14px;
        line-height: 14px;
        font-weight: bold;
        margin-top: 9px;
        color: white;
      "
    >
      NOVA PERGUNTA
    </h4>
  </div>
  <div class="container newQuestionContainer" v-if="this.statusNovaPergunta">
    <button
      class="btn-close"
      style="
        position: absolute;
        display: flex;
        margin-top: 10px;
        right: 0;
        margin-right: 230px;
      "
      @click="this.statusNovaPergunta = false"
    ></button>
    <h5
      style="
        position: absolute;
        display: flex;
        font-size: 15px;
        line-height: 20px;
        font-weight: 700;
        color: black;
        margin-top: 20px;
        margin-left: 10px;
      "
    >
      Usuário:
    </h5>
    <input
      style="
        position: absolute;
        display: flex;
        background: #ebf2f7;
        border: 2px solid #ebf2f7;
        width: 250px;
        height: 30px;
        margin-top: 15px;
        margin-left: 85px;
        border-radius: 5px;
      "
      v-model="this.auxQuestion.username"
    />
    <select
      style="
        position: absolute;
        display: flex;
        width: 160px;
        height: 25px;
        margin-top: 12px;
        margin-left: 370px;
        font-size: 16px;
        color: #687b8c;
        height: 40px;
        background: #ebf2f7;
        border: 2px solid #ebf2f7;
        border-radius: 20px;
      "
      v-model="this.auxQuestion.category"
    >
      <option>Matemática</option>
      <option>História</option>
      <option>Geografia</option>
      <option>Biologia</option>
      <option>Português</option>
      <option>Física</option>
      <option>Química</option>
      <option>Filosofia</option>
      <option>Sociologia</option>
    </select>
    <textarea
      style="
        position: absolute;
        display: flex;
        background: #ebf2f7;
        border: 2px solid #ebf2f7;
        width: 955px;
        height: 110px;
        margin-top: 65px;
        margin-left: 15px;
        border-radius: 5px;
        overflow: auto;
      "
      v-model="this.auxQuestion.text"
    >
    </textarea>
    <div
      class="addQuestionButton"
      style="background-color: #198754"
      @click="this.addQuestion()"
    >
      <h4
        style="
          position: absolute;
          display: flex;
          font-size: 14px;
          line-height: 14px;
          font-weight: bold;
          margin-top: 9px;
          margin-left: 13px;
          color: white;
        "
      >
        CRIAR PERGUNTA
      </h4>
    </div>
  </div>
  <div class="container container-list" v-for="pergunta in perguntas" :key="pergunta">
    <QuestionCard :arrayPerguntas="pergunta"/>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Categories from "./components/Categories.vue";
import QuestionCard from "./components/QuestionCard.vue";

export default {
  name: "App",
  data() {
    return {
      perguntas: [],
      statusNovaPergunta: false,
      auxQuestion: {},
    };
  },
  components: {
    Header,
    Categories,
    QuestionCard
  },
  methods: {
    addQuestion() {
      this.perguntas.push(this.auxQuestion);
      this.auxQuestion = {};
      console.log(this.perguntas);
    }
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.container {
  max-width: 70%;
  max-height: 100%;
}

.container-list {
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-top: 3%;
  border: 2px solid rgba(128, 128, 128, 0.281);
  border-radius: 8px;
  margin-bottom: 20px;
}

.newQuestionButton {
  position: relative;
  justify-content: center;
  align-items: center;
  width: 13%;
  height: 35px;
  border: 1px solid rgba(0, 0, 0, 0);
  border-radius: 20px;
  margin-top: 3%;
  transition: 0.2s;
}

.addQuestionButton {
  position: relative;
  width: 16%;
  height: 35px;
  border: 1px solid rgba(0, 0, 0, 0);
  border-radius: 20px;
  margin-top: 200px;
  margin-bottom: 20px;
  margin-left: 42%;
}

.newQuestionButton:hover {
  transform: translateY(-5px);
}

.newQuestionContainer {
  display: flex;
  width: 102%;
  max-width: 70%;
  max-height: 100%;
  margin-top: 3%;
  border: 2px solid rgba(128, 128, 128, 0.281);
  border-radius: 8px;
}
</style>
