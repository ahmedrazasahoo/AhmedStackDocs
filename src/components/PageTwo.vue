<script>
export default {
  data() {
    return {
      count: 0,
      nameData:""
    };
  },
  methods: {
    printData() {
      console.log("Click the Button");
    },
    greet(event) {
      alert(`Hello!`);
      if (event) {
        console.log(event);
        console.log(event.target.value);
        alert(event.target.tagName);
      }
    },
    
    say(message) {
      alert(message);
    },


    pre(num,event ){
      // event.preventDefault()
      // console.log("You Clicked the Button",event);
      console.log(num)
    },

    handler(event){
      this.nameData = event.target.value

      
      console.log("Helooo ki hal ha",this.nameData)
    },
    clear(){
        this.nameData = ""
    },
    leftClick(){
        console.log("left click is working fine now please resolve the error")
    },
  handleClick(event) {
  switch (event.button) {
    case 0:
      alert("Left button clicked");
      break;
    case 1:
      alert("Middle button clicked");
      break;
    case 2:
      alert("Right button clicked");
      break;
    default:
      alert("Other input");
  }
}
 
  },
};
</script>

<template>
  <div class="page-wrapper">
    <h1 class="main-title">Vue Event Handling</h1>
    <p class="intro-text">
      Demonstrates inline handlers, method handlers, and event types.
    </p>

    <ul class="features-list">
      <li>Listening to events and types (inline handlers: count++)</li>
      <li>Calling methods in inline Handlers</li>
      <li>Event modifiers in event Handlers</li>
      <li>Update The Key Modifiers Events</li>
      <li> Update The System Modifier Keys Events</li>
      <li>Update The System Mouse Button Modifiers</li>
    </ul>

    <div class="wrapper_handler">
      <h2 class="counter">{{ count }}</h2>

      <!--       
        <button class="btn" @click="count++">Increment Count</button>
        <button class="btn btn-secondary" @click="printData">Print Data</button>
        <button class="btn btn-secondary" @click="greet">Greet</button>
        <button class="btn btn-secondary" @click="say('Hello')">Say Hello</button>
        <button class="btn btn-secondary" @click="say('Bye')">Say Bye</button> -->
        <!-- @click="pre('Click The Button',$event) -->
         <!-- @click.stop="say"><button -->
        <!-- <form @submit.prevent="pre('Hello This One Be Form Submitted')">
          <button> Click Me </button>

        </form> -->

        <!-- only call `submit` when the `key` is `Enter` -->
          <!-- <input @enter="keyhandle('hehehehe')" /> -->
          <!-- only call `submit` when the `key` is `Enter` -->
      <!-- <input @keyup="handler" /> -->
      <!-- only call `submit` when the `key` is `Enter` -->
       <h1>{{ nameData }}</h1>
      <input
        @keyup="handler($event)"
        @keyup.alt.enter="clear"
        v-bind:value="nameData"

      />
<button @mousedown="handleClick">Try any click</button> 



      
    </div>
  </div>
</template>

<style scoped>
.page-wrapper {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  padding: 30px;
  background: #1a1a2e;
  min-height: 100vh;
  color: #f3f3f3;
}

.main-title {
  font-size: 32px;
  font-weight: 700;
  margin-bottom: 10px;
  color: #e94560;
  text-align: center;
}

.intro-text {
  font-size: 16px;
  margin-bottom: 20px;
  text-align: center;
  color: #dcdde1;
}

.features-list {
  list-style: none;
  padding: 0;
  margin-bottom: 30px;
}

.features-list li {
  margin: 8px 0;
  padding: 6px 10px;
  background: #162447;
  border-radius: 8px;
}

.wrapper_handler {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 15px;
}

.counter {
  font-size: 48px;
  margin-bottom: 15px;
  color: #f76c6c;
}

.btn {
  padding: 10px 20px;
  background-color: #e94560;
  color: #fff;
  border: none;
  border-radius: 8px;
  cursor: pointer;
  font-weight: 600;
  transition: all 0.3s ease;
}

.btn:hover {
  background-color: #ff2e63;
  transform: scale(1.05);
}

.btn-secondary {
  background-color: #0f3460;
}

.btn-secondary:hover {
  background-color: #162447;
}
</style>
