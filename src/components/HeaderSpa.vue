<script setup></script>

<template>
  <div>
    <header class="header">
      <!-- Логотип -->
      <div class="header__logo">
        <div class="header__shield">
          <svg viewBox="0 0 24 24" class="header__shield-icon">
            <path
              d="M12 2L4 5v6.09c0 5.05 3.41 9.76 8 10.91 4.59-1.15 8-5.86 8-10.91V5l-8-3z"
              fill="#4CAF50"
            />
            <circle cx="12" cy="12" r="4" fill="white" />
          </svg>
        </div>
        <span class="header__logo-text">INVENTORY</span>
      </div>
      <!-- /.header__logo -->
      <!-- Поиск -->
      <div class="header__search">
        <input type="text" class="header__search-input" placeholder="Поиск" v-model="searchQuery" />
      </div>
      <!-- /.header__search -->
      <!-- Дата и время -->
      <div class="header__datetime">
        <div class="header__date">
          <div>12</div>
          <div>april</div>
        </div>
        <!-- /.header__date -->
        <div class="header__time">
          <svg viewBox="0 0 24 24" class="header__clock-icon">
            <circle cx="12" cy="12" r="10" fill="none" stroke="#4CAF50" stroke-width="2" />
            <path d="M12 6v6l4 2" fill="none" stroke="#4CAF50" stroke-width="2" stroke-linecap="round" />
          </svg>
          <span>Time</span>
        </div>
        <!-- /.header__time -->
      </div>
      <!-- /.header__datetime -->
    </header>
  </div>
</template>

<style scoped>
.header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 12px 24px;
  border-bottom: 1px solid #e0e0e0;
  background-color: #fff;
  gap: 24px;
}
/* Логотип */
.header__logo {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 1.5rem;
  flex-shrink: 0; /*Запрещает логотипу сжиматься*/
}
.header__shield {
  width: 40px;
  height: 40px;
  display: flex;
  align-items: center;
  justify-content: center;
}
.header__shield-icon {
  width: 36px;
  height: 36px;
}
.header__logo-text {
  color: #4caf50;
  font-size: 16px;
  font-weight: 600;
  letter-spacing: 0.5px;
}
/* Поиск */
.header__search {
  flex: 1; /*Растягивает по ширине все остальное, занять всё оставшееся свободное место в контейнере*/
  max-width: 400px;
  min-width: 0; /*Устанавливает минимальную ширину элемента, и инпут будет сжиматься корректно*/
}
.header__search-input {
  width: 100%;
  height: 40px;
  padding: 8px 12px;
  border: 1px solid #d0d0d0;
  border-radius: 4px;
  font-size: 14px;
  outline: none;
  transition: border-color 0.2s;
}
.header__search-input:focus {
  border-color: #4caf50;
}
/* Дата и время */
.header__datetime {
  display: flex;
  align-items: center;
  gap: 1rem;
  font-size: 1.2rem;
  flex-shrink: 0;
}
.header__date {
  text-align: right;
  font-size: 13px;
  color: #333;
  line-height: 1.4;
}
.header__time {
  display: flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 13px;
  color: #333;
}
.header__clock-icon {
  width: 16px;
  height: 16px;
}
</style>