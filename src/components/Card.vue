<script setup>
defineProps({
  display: Boolean,
});

const emit = defineEmits(["close"]);
</script>
<template>
  <div class="container" v-if="display">
    <div class="header">
      <button @click="emit('close')">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          role="img"
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          aria-labelledby="arrowLeftIconTitle"
          stroke="#FFF"
          stroke-width="2"
          stroke-linecap="square"
          stroke-linejoin="miter"
          fill="none"
          color="#FFF"
        >
          <title id="arrowLeftIconTitle">Arrow Left</title>
          <path d="M9 6l-6 6 6 6" />
          <path d="M21 12H4" />
          <path stroke-linecap="round" d="M3 12h1" />
        </svg>
        返回首页
      </button>
    </div>
    <div class="card">
      <h1>登录</h1>
      <div class="input-group">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          role="img"
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          aria-labelledby="envelopeAltIconTitle"
          stroke="#FFF"
          stroke-width="2"
          stroke-linecap="square"
          stroke-linejoin="miter"
          fill="none"
          color="#FFF"
        >
          <title id="envelopeAltIconTitle">Envelope</title>
          <rect width="20" height="14" x="2" y="5" />
          <path stroke-linecap="round" d="M2 5l10 9 10-9" />
        </svg>
        <input type="email" id="email" placeholder="邮箱" />
      </div>
      <div class="input-group">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          role="img"
          width="24px"
          height="24px"
          viewBox="0 0 24 24"
          aria-labelledby="lockAltIconTitle"
          stroke="#FFF"
          stroke-width="2"
          stroke-linecap="square"
          stroke-linejoin="miter"
          fill="none"
          color="#FFF"
        >
          <title id="lockAltIconTitle">Lock</title>
          <rect width="14" height="10" x="5" y="11" />
          <path
            d="M12,3 L12,3 C14.7614237,3 17,5.23857625 17,8 L17,11 L7,11 L7,8 C7,5.23857625 9.23857625,3 12,3 Z"
          />
          <circle cx="12" cy="16" r="1" />
        </svg>
        <input type="password" id="password" placeholder="密码" />
      </div>
      <div class="card-footer">
        <div>
          <button>注册账号</button>
          <button>忘记密码</button>
        </div>
        <button>
          登录
          <svg
            xmlns="http://www.w3.org/2000/svg"
            role="img"
            width="24px"
            height="24px"
            viewBox="0 0 24 24"
            aria-labelledby="entranceIconTitle"
            stroke="#381E72"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            fill="none"
            color="#381E72"
          >
            <title id="entranceIconTitle">Entrance</title>
            <path d="M11 15l3-3-3-3" />
            <path d="M4.5 12H13" />
            <path stroke-linecap="round" d="M14 12h-1" />
            <path d="M18 4v16H7V4z" />
          </svg>
        </button>
      </div>
    </div>
  </div>
</template>
<style>
.container {
  width: 400px;
  height: 300px;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
}
.card {
  width: 100%;
  height: 90%;
  background-color: rgba(66, 66, 79, 0.5);
  backdrop-filter: blur(5px);
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  border-radius: 20px;
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
  box-sizing: border-box;
  padding: 20px;
}
.card h1 {
  color: white;
  font-size: 24px;
}
.header {
  width: 100%;
  height: 10%;
}
.header {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  padding: 10px 10px;
}
.header button {
  background: none;
  border: none;
  color: white;
  cursor: pointer;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 8px 16px;
  border-radius: 100px;
}
.header button:hover {
  background-color: rgba(53, 204, 146, 0.2);
}
.header button:active {
  background-color: rgba(51, 98, 193, 0.4);
}
.card-footer {
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.card-footer > div {
  display: flex;
  justify-content: center;
  align-items: center;
}
.card-footer > div button {
  background-color: #3b383e;
  color: #4fcfc9;
  margin-right: 10px;
}
.card-footer button {
  height: 36px;
  padding: 0 16px;
  border: none;
  border-radius: 100px;
  background-color: #42a2b1;
  color: #0c010a;
  cursor: pointer;
  justify-content: center;
  align-items: center;
  display: flex;
}
.card-footer button:hover {
  background-color: rgb(66, 145, 134);
}
.card-footer button:active {
  background-color: rgb(6, 143, 33);
}

.input-group {
  width: 95%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}
.input-group input {
  width: 90%;
  height: 30px;
  border: none;
  border-radius: 5px;
  padding: 0 10px;
  box-sizing: border-box;
  background: none;
  outline: none;
  color: white;
}

.input-group input::placeholder {
  color: #ccc;
  font-size: 16px;
}
.input-group:focus-within {
  border-color: #290c62;
}
button {
  transition: 0.5s;
}
</style>
