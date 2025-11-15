<script setup>
const emit = defineEmits(["show-card"]);
</script>
<template>
  <header>
    <div class="logo">乱七八糟</div>
    <div class="search-bar">
      <input id="searchtext" type="text" placeholder="搜索话题、用户..." />
      <button class="search-button" id="search-button">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          width="18"
          height="18"
          fill="currentColor"
          class="bi bi-search"
          viewBox="0 0 16 16"
        >
          <path
            d="M11.742 10.344a6.5 6.5 0 1 0-1.397 1.398h-.001q.044.06.098.115l3.85 3.85a1 1 0 0 0 1.415-1.414l-3.85-3.85a1 1 0 0 0-.115-.1zM12 6.5a5.5 5.5 0 1 1-11 0 5.5 5.5 0 0 1 11 0"
          />
        </svg>
      </button>
      <div class="search-history">
        <div class="history-header">
          <span>历史记录</span>
          <button class="clear-button" id="clear-history">清除全部</button>
        </div>
        <ul id="history-list"></ul>
      </div>
    </div>
    <nav>
      <ul>
        <li><a href="#">首页</a></li>
        <li><a href="#">发帖</a></li>
        <li><a href="#">消息</a></li>
        <li><a href="#">个人中心</a></li>
        <li><a href="#" @click.prevent="emit('show-card')">登录</a></li>
        <li><a href="#">注册</a></li>
      </ul>
    </nav>
  </header>
</template>
<style>
header {
  background-color: #ffffff;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
  padding: 20px;
  text-align: center;
}

.logo {
  font-size: 32px;
  font-weight: bold;
  color: #007bff;
  display: inline-block;
  position: relative;
}

.logo::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: 0;
  width: 100%;
  height: 2px;
  background-color: #007bff;
  transform: scale(0);
  transition: 0.5s;
}

.logo:hover::after {
  transform: scale(1);
}

.search-bar input {
  padding: 10px 30px 10px 15px;
  width: 350px;
  border: 1px solid #ccc;
  border-radius: 25px;
  font-size: 16px;
  position: relative;
}

.search-bar {
  position: relative;
  margin: 0 auto;
  width: 350px;
}

.search-button {
  position: absolute;
  left: 100%;
  top: 50%;
  transform: translateY(-50%);
  background: none;
  border: none;
  padding: 5px;
  cursor: pointer;
}
.search-button:hover {
  background-color: rgba(0, 255, 255, 0.23);
}
.search-button:active {
  background-color: #ffffff;
}

ul li {
  display: inline-block;
  margin: 0 15px;
}

ul li a {
  text-decoration: none;
  color: #333;
  font-size: 18px;
  position: relative;
  transition: 0.5s;
}

ul li a::after {
  content: "";
  position: absolute;
  left: 0;
  bottom: -5px;
  width: 100%;
  height: 2px;
  background-color: #007bff;
  transform: scale(0);
  transition: 0.5s;
}

ul li a:hover {
  color: #007bff;
}

ul li a:hover::after {
  transform: scale(1);
}
.search-history {
  position: absolute;
  top: 80%;
  width: 350px;
  background: white;
  border-radius: 14px;
  box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
  margin-top: 10px;
  z-index: 100;
  display: none;
}

.search-bar:hover .search-history {
  display: block;
}
.clear-button {
  background: none;
  border: none;
  padding: 5px;
  border-radius: 10px;
  cursor: pointer;
}
.clear-button:hover {
  background-color: rgba(0, 255, 255, 0.23);
}
.clear-button:active {
  background-color: #ffffff;
}

.history-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 6px 14px 10px;
  font-weight: 600;
  color: #007bff;
  border-bottom: 1px solid #f0f0f0;
}

#history-list li {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 8px 14px;
  transition: 0.15s;
}
#history-list li:hover {
  background: #f0f8ff;
}
#history-list li button {
  background: none;
  border: none;
  font-size: 18px;
  color: #aaa;
  cursor: pointer;
  transition: 0.2s;
}
#history-list li button:hover {
  color: #ff5c5c;
}
</style>
