<template>
  <div class="quiz-container">
    <header>
      <h1>Quiz</h1> 
    </header>
    <div class="question" v-for="(question, index) in questions" :key="index">
      <h2>{{ question.title }}</h2>
      <p>{{ question.description }}</p>
      <ul>
        <li v-for="(answer, answerIndex) in question.answers" :key="answerIndex">
          <label>
            <input type="radio" :name="`question${index}`" :value="answer" v-model="question.selectedAnswer">
            {{ answer }}
          </label>
        </li>
      </ul>
    </div>
    <button class="submit-button" @click="submitQuiz">Enviar</button>
    <div class="results" v-if="showResults">
      <h2>Resultados:</h2>
      <ul>
        <li v-for="(question, index) in questions" :key="index">
          <p>
            {{ question.title }}
            Resposta Correta: {{ question.correctAnswer }}
            Sua Resposta: {{ question.selectedAnswer }}
          </p>
        </li>
      </ul> 
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      questions: [
        {
          title: "Pergunta 1:",
          description: "Qual o elemento químico mais abundante na Terra ?",
          answers: ["Oxigênio", "Silício", "Alumínio", "Ferro", "Cálcio"],
          selectedAnswer: null,
          correctAnswer:"Oxigênio",
        },
        {
          title: "Pergunta 2:",
          description: "Qual o elemento químico mais leve da tabela periódica ?",
          answers: ["Hidrogênio", "Hélio", "Lítio", "Berílio", "Boro"],
          selectedAnswer: null,
          correctAnswer: "Hidrogênio",
        },
        {
          title: "Pergunta 3:",
          description: "Qual é o símbolo químico do elemento hidrogênio ?",
          answers: ["H", "He", "Hf", "Ho", "Hg"],
          selectedAnswer: null,
          correctAnswer: "H",
        },
        {
          title: "Pergunta 4:",
          description: "Qual é o nome do grupo 18 da tabela periódica ?",
          answers: ["gases nobres", "Metais alcalinos", "Metais alcalino-terrosos", "Metais de transição", "Halogênios"],
          selectedAnswer: null,
          correctAnswer: "gases nobres"
        },
        {
          title: "Pergunta 5:",
          description: "Qual o símbolo químico para o elemento ouro ?",
          answers: ["Au", "Ag", "Cu", "Pt", "Pd"],
          selectedAnswer: null,
          correctAnswer: "Au"
        },
        {
          title: "Pergunta 6:",
          description: "Qual o elemento químico mais eletronegativo ?",
          answers: ["Flúor", "Oxigênio", "Cloro", "Nitrogênio", "Enxofre"],
          selectedAnswer: null,
          correctAnswer: "Flúor"
        },
        {
          title: "Pergunta 7:",
          description: "Qual o elemento químico usado como combustível em reatores nucleares ?",
          answers: ["Urânio", "Plutônio", "Tório", "Césio", "Estrôncio"],
          selectedAnswer: null,
          correctAnswer: "Urânio"
        },
        {
          title: "Pergunta 8:",
          description: "Qual o elemento químico mais denso ?",
          answers: ["Ósmio", "Iridio", "Platina", "Ouro", "Tungstênio"],
          selectedAnswer: null,
          correctAnswer: "Ósmio"
        },
        {
          title: "Pergunta 9:",
          description: "Qual o elemento químico mais reativo ?",
          answers: ["Flúor", "Cloro", "Oxigênio", "Hidrogênio", "Sódio"],
          selectedAnswer: null,
          correctAnswer: "Flúor"
        },
        {
          title: "Pergunta 10:",
          description: "Qual o elemento químico presente em maior quantidade no corpo humano ?",
          answers: ["Oxigênio", "Carbono", "Hidrogênio", "Nitrogênio", "Cálcio"],
          selectedAnswer: null,
          correctAnswer: "Oxigênio"
        },
        {
          title: "Pergunta 11:",
          description: "Qual o elemento químico presente em maior quantidade na crosta terrestre ?",
          answers: ["Oxigênio", "Silício", "Alumínio", "Ferro", "Cálcio"],
          selectedAnswer: null,
          correctAnswer: "Oxigênio"
        },
        {
          title: "Pergunta 12:",
          description: "Qual o grupo da tabela periódica que é conhecido como metais alcalinos ?", 
          answers: ["Grupo 1", "Grupo 2", "Grupo 3", "Grupo 4", "Grupo 5"],
          selectedAnswer: null,
          correctAnswer: "Grupo 1"
        },
        {
          title: "Pergunta 13:",
          description: "Qual o elemento químico que é usado como lubrificante em altas temperaturas ?",
          answers: ["Molibdênio", "Grafite, Boro", "Silício", "Cobre"],
          selectedAnswer: null,
          correctAnswer: "Molibdênio"
        },
        {
          title: "Pergunta 14:",
          description: "Qual o elemento químico que é usado para tratar o câncer ?",
          answers: ["Platina", "Ferro", "Cobre", "Carbono", "Ouro"],
          selectedAnswer: null,
          correctAnswer: "Platina"
        },
        {
          title: "Pergunta 15:",
          description: "Qual o elemento químico que é usado para construir espelhos ?",
          answers: ["Prata", "Alumínio", "Cobre", "Ouro", "Cromo"],
          selectedAnswer: null,
          correctAnswer: "Prata"
        },
      ],
      showResults: false,
    };
  },
  methods: {
    submitQuiz() {
      this.showResults = true;
      console.log("Quiz enviado!");
    },
  },
};
</script>

<style scoped>
.quiz-container {
  max-width: 600px;
  margin: 0 auto;
  padding: 20px;
  background-color: #ffffff;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

header {
  text-align: center;
}

h1 {
  color: #333333;
}

.question {
  margin-bottom: 20px;
}

h2 {
  color: #333333;
}

ul {
  list-style-type: none;
  padding: 0;
  margin: 10px 0;
}

li {
  margin: 5px 0;
}

.submit-button {
  display: block;
  width: 100%;
  padding: 10px;
  background-color: #4caf50;
  color: #ffffff;
  font-size: 16px;
  text-align: center;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.submit-button:hover {
  background-color: #45a049;
}
</style>
