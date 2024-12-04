<template>

    <div id="app">
  
      <!-- 添加动态背景 -->
  
      <div class="background"></div>
  
      <!-- Vue Logo -->
  
      <img alt="Vue logo" src="./assets/logo.png" class="vue-logo">
  
    
  
      <!-- 动态的 Hello World 组件 -->
  
      <HelloWorld :msg="dynamicMessage"/>
  
    
  
      <!-- 新增一个按钮，点击后显示欢迎提示 -->
  
      <button @click="showWelcomeMessage" class="welcome-button">
  
        Click Me for a Surprise!
  
      </button>
  
    
  
      <!-- 显示欢迎消息 -->
  
      <p v-if="showMessage" class="welcome-message">
  
        You are now part of the Vue.js family! 🎉
  
      </p>
  
    </div>
  
  </template>
  
    
  
  <script>
  
  import HelloWorld from './components/HelloWorld.vue'
  
    
  
  export default {
  
    name: 'App',
  
    components: {
  
      HelloWorld
  
    },
  
    data() {
  
      return {
  
        showMessage: false,
  
      };
  
    },
  
    computed: {
  
      // 动态欢迎信息
  
      dynamicMessage() {
  
        const messages = [
  
          'Welcome to Your Vue.js Adventure!',
  
          'Building great things with Vue!',
  
          'Vue.js: Let the creativity flow!',
  
          'Ready to create something amazing?'
  
        ];
  
        return messages[Math.floor(Math.random() * messages.length)];
  
      }
  
    },
  
    methods: {
  
      showWelcomeMessage() {
  
        this.showMessage = true;
  
      }
  
    }
  
  }
  
  </script>
  
    
  
  <style scoped>
  
  #app {
  
    position: relative;
  
    font-family: 'Comic Sans MS', Helvetica, Arial, sans-serif; /* 更具趣味性的字体 */
  
    -webkit-font-smoothing: antialiased;
  
    -moz-osx-font-smoothing: grayscale;
  
    text-align: center;
  
    color: #2c3e50;
  
    margin-top: 60px;
  
  }
  
    
  
  .vue-logo {
  
    animation: spin 20s linear infinite; /* 添加旋转动画 */
  
    height: 150px;
  
  }
  
    
  
  @keyframes spin {
  
    from {
  
      transform: rotate(0deg);
  
    }
  
    to {
  
      transform: rotate(360deg);
  
    }
  
  }
  
    
  
  .background {
  
    position: absolute;
  
    top: 0;
  
    left: 0;
  
    width: 100%;
  
    height: 100%;
  
    background: linear-gradient(135deg, #6b73ff, #000dff);
  
    z-index: -1;
  
    animation: gradientAnimation 10s ease infinite alternate;
  
  }
  
    
  
  @keyframes gradientAnimation {
  
    0% {
  
      background-position: 0% 50%;
  
    }
  
    100% {
  
      background-position: 100% 50%;
  
    }
  
  }
  
    
  
  .welcome-button {
  
    background-color: #42b983;
  
    border: none;
  
    color: white;
  
    padding: 15px 32px;
  
    text-align: center;
  
    text-decoration: none;
  
    display: inline-block;
  
    font-size: 16px;
  
    margin: 20px;
  
    cursor: pointer;
  
    transition: background-color 0.3s;
  
  }
  
    
  
  .welcome-button:hover {
  
    background-color: #2c8f66;
  
  }
  
    
  
  .welcome-message {
  
    font-size: 1.5em;
  
    color: #ffeb3b;
  
    margin-top: 20px;
  
  }
  
  </style>