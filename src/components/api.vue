<script>
export default {
  data() {
    return {
      question: "",
      answer: "Questions usually contain a question mark. ;-)",
      loading: false,
    };
  },
  watch: {
    // whenever question changes, this function will run
    question(newQuestion, oldQuestion) {
      if (newQuestion.includes("?")) {
        this.getAnswer();
      }
    },
  },
  methods: {
    async getAnswer() {
      this.loading = true;
      this.answer = "Thinking...";
      try {
        const res = await fetch("https://yesno.wtf/api");
        this.answer = (await res.json()).answer;
      } catch (error) {
        this.answer = "Error! Could not reach the API. " + error;
      } finally {
        this.loading = false;
      }
    },
  },
};
</script>
<template>
  <div class="api-wrapper">
    <p>
      Ask a yes/no question:
      <input v-model="question" :disabled="loading" />
    </p>
    <p>{{ answer }}</p>
  </div>
</template>
