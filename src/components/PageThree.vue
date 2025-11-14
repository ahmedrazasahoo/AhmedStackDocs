<script>
export default {
  data() {
    return {
      FormData: {
        nameData: "",
        age: 0,
        message: "",
        multimessage: "",
        checked: false,
        adminList: [],
        picked: "",
        role: "",
        multipleRole: [],
        dynamicRole: [],
        toggle: "",
        radio: "",
      },
      secondUser:{id:2,name:"Raza"} ,
      firstUser:{id:1,name:"Ahmed"},
      OptionsDataoptions: [
        { text: "One", value: "Ahmed" },
        { text: "One", value: "Raza" },
        { text: "Two", value: "B" },
        { text: "Three", value: "C" },
      ],
    };
  },

  computed: {
    finalOptions() {
      return this.fetchData().filter((op) => op.text == "One");
    },
  },
  methods: {
    uper() {
      this.FormData.nameData = this.FormData.nameData.toUpperCase();
    },

    fetchData() {
      return [
        { text: "One", value: "Ahmed" },
        { text: "One", value: "Raza" },
        { text: "One", value: "khan" },
        { text: "One", value: "Fianl" },
        { text: "Two", value: "B" },
        { text: "Three", value: "C" },
      ];
    },
  },
};
</script>

<template>
  <div class="page-wrapper">
    <h1 class="main-title">Vue Form Input Bindings</h1>
    <p class="intro-text">
      Demonstrates how <code>v-model</code> keeps form inputs in sync with Vue
      data.
    </p>

    <ul class="features-list">
      <li>
        <strong>v-model</strong> automatically binds input value to Vue data.
      </li>
      <li>No need for manual event listeners like <code>@input</code>.</li>
      <li>Works seamlessly with text, checkbox, radio, and select elements.</li>
      <li>Value Bindings in the form inputs when data is set in the filed</li>
      <li>
        Modifiers like <code>.number</code> and <code>.trim</code> can be used
        with <code>v-model</code> for specific input handling.
      </li>
    </ul>

    <div class="form-wrapper">
      <form @submit.prevent class="styled-form">
        <!-- NAME -->
        <div class="form-group">
          <label>Enter your name:</label>
          <input
            type="text"
            v-model="FormData.nameData"
            placeholder="Type your name here..."
          />
        </div>

        <!-- AGE -->
        <div class="form-group">
          <label>Age:</label>
          <input
            type="number"
            v-model="FormData.age"
            placeholder="Type your age here..."
          />
        </div>

        <!-- SINGLE-LINE MESSAGE -->
        <div class="form-group">
          <label>Message:</label>
          <input
            type="text"
            v-model="FormData.message"
            placeholder="Edit message"
          />
        </div>

        <!-- MULTI-LINE MESSAGE -->
        <div class="form-group">
          <label>Multiline Message:</label>
          <textarea
            v-model="FormData.multimessage"
            placeholder="Add multiple lines"
          ></textarea>
        </div>

        <!-- CHECKBOX -->
        <div class="form-group checkbox-group">
          <label>
            <input type="checkbox" v-model="FormData.checked" />
            Checked: {{ FormData.checked }}
          </label>
        </div>

        <label>
          <input type="checkbox" v-model="FormData.adminList" value="Ahmed" />
          Ahmed
        </label>
        <label>
          <input type="checkbox" v-model="FormData.adminList" value="Raza" />
          Raza
        </label>

        <br /><br />

        <div>
          <input type="radio" value="One" v-model="FormData.picked" />
          <label>One</label>

          <input type="radio" value="Two" v-model="FormData.picked" />
          <label>Two</label>
          <input type="radio" value="Three" v-model="FormData.picked" />
          <label>Three</label>
        </div>
        <br /><br />
        <div class="form-group">
          <label>Simple Selected Field</label>

          <select v-model="FormData.role">
            <option>A</option>
            <option>B</option>
            <option>C</option>
          </select>
        </div>
        <br /><br />
        <div class="form-group">
          <label>Multiline Selected Field</label>

          <select v-model="FormData.multipleRole" multiple>
            <option>A</option>
            <option>B</option>
            <option>C</option>
          </select>
        </div>

        <br /><br />
        <div class="form-group">
          <label>Dynamic Selected Options</label>
          <select v-model="FormData.dynamicRole">
            <option
              v-for="opt in finalOptions"
              :key="opt.value"
              :value="opt.value"
            >
              {{ opt.value }}
            </option>
          </select>
        </div>
        <br /><br />
        <!-- `picked` is a string "a" when checked -->
        <label>Rab Da Radio</label>
        <input type="radio" v-model="FormData.radio" value="a" />

        <!-- `toggle` is either true or false -->
        <label>Toggle The form</label>
        <input type="checkbox" v-model="FormData.toggle" />

        <br /><br /><br />

        {{ FormData }}
      </form>
    </div>
  </div>
</template>

<style scoped>
.page-wrapper {
  font-family: "Segoe UI", sans-serif;
  background: #1a1a2e;
  min-height: 100vh;
  padding: 40px;
  color: #fff;
}

.styled-form {
  background: #162447;
  padding: 25px;
  border-radius: 16px;
  width: 420px;
  margin: 0 auto;
  box-shadow: 0 0 15px #0006;
}

.form-group {
  margin-bottom: 20px;
  display: flex;
  flex-direction: column;
}

.form-group label {
  margin-bottom: 6px;
  font-size: 15px;
  color: #eee;
}

input,
textarea,
select {
  padding: 10px 14px;
  border-radius: 10px;
  background: #0f3460;
  border: none;
  outline: none;
  color: #fff;
  box-shadow: inset 0 0 10px #0005;
  font-size: 14px;
}

textarea {
  height: 90px;
}

input:focus,
textarea:focus,
select:focus {
  border: 2px solid #e94560;
}

.inline-group {
  display: flex;
  gap: 15px;
  flex-wrap: wrap;
}

.checkbox-line {
  display: flex;
  align-items: center;
  gap: 10px;
}

.output-box {
  background: #0f3460;
  padding: 15px;
  border-radius: 12px;
  margin-top: 20px;
  color: #fff;
  font-family: monospace;
  font-size: 13px;
}
</style>
