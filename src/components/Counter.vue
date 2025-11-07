<template>
  <div class="counter-container">
    <div :class="StyleBinding">
      <h1 :="objectOfAttrs">Binding the Attribute Bindings</h1>
      <div :id="`list-${count}`">
        <p>ID Set the values with expression with class</p>
      </div>
        <button class="button" @click="handledisk(count)"> Call Funcation</button>

      <h4>
        Current Style Binding is :
        <span>{{ StyleBinding }}</span>
      </h4>
      <h3>Javescript Object Binding for the Attribute</h3>
    </div>

    <div v-html="raw_tag"></div>
    <div class="raw_tag">
      {{ raw_tag }}
    </div>

    <h1 class="title">{{ txt }}</h1>

    <div class="counter-card">
      <h2 class="count-display">
        {{ count > 1 ? "Ahmed Raza" : "Chal Dafa ho" }}<br />{{ count }}
      </h2>

      <div class="btn-group">
        <button class="btn decrement" @click="decrement">−</button>
        <button
          :disabled="ButtonDisable"
          class="btn increment"
          @click="increment"
        >
          +
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      txt: "This page is used for the counter By using the option api",
      raw_tag: "<ul><li>Raw HTML tag rander as a plan html<li/></ul>",
      count: 0,
      StyleBinding: "normal",
      ButtonDisable: false,
      objectOfAttrs: {
        id: "container",
        class: "wrapper",
      },
    };
  },
  methods: {
    increment() {
      this.count++;

      if (this.count >= 10) {
        this.ButtonDisable = true;

        this.StyleBinding = "warning";
      } else if (this.count > 5) {
        this.StyleBinding = "success";
        this.ButtonDisable = false;
      } else {
        this.StyleBinding = "normal";
      }
    },

    decrement() {
      this.count--;

      if (this.count < 0) {
        this.StyleBinding = "danger";
      } else if (this.count < 10) {
        this.ButtonDisable = false;
      }
    },
    handledisk(num) {
      alert("Function Called with the value " + num/2);
    },
  },
};
</script>

<style scoped>
.button{
  padding: 10px 15px;
  background: #10b981;
  color: white;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  margin-bottom: 15px;
}
.success {
  color: #58e735;
}

.danger {
  color: rgb(212, 82, 82);
}
.warning {
  color: rgb(209, 209, 64);
}
.counter-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  min-height: 70vh;
  background: #f9fafb;
  color: #1f2937;
  font-family: "Inter", sans-serif;
}

.title {
  font-size: 1.5rem;
  margin-bottom: 2rem;
  color: #065f46;
  font-weight: 600;
}

.counter-card {
  background: #ffffff;
  border-radius: 16px;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
  padding: 2rem 3rem;
  text-align: center;
  transition: all 0.3s ease;
}

.counter-card:hover {
  transform: translateY(-3px);
}

.count-display {
  font-size: 3rem;
  font-weight: bold;
  color: #047857;
  margin-bottom: 1.5rem;
}

.btn-group {
  display: flex;
  gap: 1rem;
  justify-content: center;
}

.btn {
  padding: 0.75rem 1.5rem;
  border: none;
  border-radius: 12px;
  font-size: 1.5rem;
  font-weight: 700;
  color: white;
  cursor: pointer;
  transition: background 0.3s, transform 0.2s;
}

.increment {
  background: linear-gradient(135deg, #22c55e, #16a34a);
}
.increment:hover {
  background: linear-gradient(135deg, #16a34a, #15803d);
  transform: scale(1.05);
}

.decrement {
  background: linear-gradient(135deg, #ef4444, #dc2626);
}
.decrement:hover {
  background: linear-gradient(135deg, #dc2626, #b91c1c);
  transform: scale(1.05);
}
</style>
