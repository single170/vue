<script setup> 
      let searchHistory = [
        { id: 1, text: "3.7全局抽卡规划" },
        { id: 2, text: "3.6剧情解析" },
        { id: 3, text: "3.7前瞻日期" },
      ];

      const searchInput = document.getElementById("searchtext");
      const historyList = document.getElementById("history-list");
      const clearBtn = document.getElementById("clear-history");
      const searchBtn = document.getElementById("search-button");

      function updateHistory() {
        historyList.innerHTML = "";
        searchHistory.forEach((item) => {
          const li = document.createElement("li");
          li.style.cssText =
            "display:flex;justify-content:space-between;padding:6px 12px;border-bottom:1px solid #eee;cursor:pointer";
          li.innerHTML = `
      <span>${item.text}</span>
      <button class="clear-button" data-id="${item.id}">×</button>
    `;

          // 插入文字和删除按钮
          li.innerHTML = `
      <span>${item.text}</span>
      <button class="clear-button" data-id="${item.id}">×</button>
    `;

          /* 点击文字回填搜索框 */
          li.querySelector("span").addEventListener("click", () => {
            searchInput.value = item.text; // 把文字塞进输入框
          });

          /* 点击 × 删除单条 */
          li.querySelector("button").addEventListener("click", (e) => {
            e.stopPropagation(); // 阻止冒泡，防止触发 li 的点击
            deleteHistoryItem(item.id); // 真正删除
          });

          historyList.appendChild(li); // 把 <li> 塞进 <ul>
        });
      }

      /* ========== 增删逻辑 ========== */
      function addHistory(text) {
        if (!text) return; // 空字符串直接返回
        /* 去重：已有则提前 */
        searchHistory = searchHistory.filter((h) => h.text !== text); // 去掉同名旧记录
        searchHistory.unshift({ id: Date.now(), text }); // 新记录插到最前面
        /* 最多保留 8 条 */
        searchHistory = searchHistory.slice(0, 8);
        updateHistory(); // 重新渲染
      }

      function deleteHistoryItem(id) {
        searchHistory = searchHistory.filter((h) => h.id !== id); // 留下 id 不同的
        updateHistory(); // 重新渲染
      }

      function clearHistory() {
        searchHistory = []; // 直接清空数组
        updateHistory(); // 重新渲染（此时会显示空列表）
      }

      searchBtn.addEventListener("click", () => {
        const val = searchInput.value.trim();
        if (!val) {
          alert("请输入内容");
          return;
        }
        addHistory(val);
        searchInput.value = "";
      });

      clearBtn.addEventListener("click", clearHistory);

      updateHistory();
    </script>
<template>
  <main>
    <section class="latest-posts">
      <h2>最新帖子</h2>
      <article class="post">
        <div class="category">游戏攻略</div>
        <h3><a href="#">新角色养成一图流</a></h3>
        <div class="author">祈鸢</div>
        <div class="time">32回复 | 30分钟前</div>
      </article>
      <article class="post">
        <div class="category">官方活动</div>
        <h3><a href="#">【有奖活动】转发新版本专题页已上线，参与...</a></h3>
        <div class="author">呜呜是个呜呜伯</div>
        <div class="time">评论过千 | 45分钟前</div>
      </article>
      <article class="post">
        <div class="category">同人图</div>
        <h3><a href="#">第一次画，不喜勿喷</a></h3>
        <div class="author">AL光</div>
        <div class="time">54回复 | 1小时前</div>
      </article>
      <article class="post">
        <div class="category">COS</div>
        <h3><a href="#">“以身入局吧” </a></h3>
        <div class="author">欲子a</div>
        <div class="time">43回复 | 1小时前</div>
      </article>
      <article class="post">
        <div class="category">候车厅</div>
        <h3><a href="#">终于凹过去了...</a></h3>
        <div class="author">批发好人卡</div>
        <div class="time">74回复 | 2小时前</div>
      </article>
    </section>
  </main>
</template>
<style>
main {
  padding: 30px;
}

.latest-posts h2 {
  font-size: 28px;
  margin-bottom: 20px;
  border-bottom: 2px solid #007bff;
  display: inline-block;
  padding-bottom: 5px;
}

.post {
  background-color: #60c1de5a;
  border: 1px solid #e0e0e0;
  border-radius: 10px;
  padding: 20px;
  margin-bottom: 20px;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  transition: 0.5s;
}

.post:hover {
  transform: translateY(-5px);
}

.category {
  background-color: #007bff;
  color: white;
  display: inline-block;
  padding: 6px 12px;
  border-radius: 20px;
  font-size: 14px;
  margin-bottom: 10px;
}

.post h3 {
  font-size: 20px;
  margin-bottom: 10px;
}

.post h3 a {
  color: #333;
  text-decoration: none;
  transition: 0.5s;
}

.post h3 a:hover {
  color: #007bff;
}

.author {
  font-size: 14px;
  color: #777;
  margin-bottom: 5px;
}

.time {
  font-size: 14px;
  color: #777;
}
</style>
