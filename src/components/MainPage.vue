<script setup>
import { ref, computed } from 'vue';

import ArrivalsPage from './pages/ArrivalsPage.vue';
import GroupsPage from './pages/GroupsPage.vue';
import ProductsPage from './pages/ProductsPage.vue';
import UsersPage from './pages/UsersPage.vue';
import SettingsPage from './pages/SettingsPage.vue';


// 1. Данные для меню. Вместо 5 одинаковых <li> пишем один и гоняем по массиву.
const tabs = [
  { id: 'arrivals', label: 'ПРИХОД', component: ArrivalsPage },
  { id: 'groups', label: 'ГРУППЫ', component: GroupsPage },
  { id: 'products', label: 'ПРОДУКТЫ', component: ProductsPage },
  { id: 'users', label: 'ПОЛЬЗОВАТЕЛИ', component: UsersPage },
  { id: 'settings', label: 'НАСТРОЙКИ', component: SettingsPage },
];

// 2. Реактивная переменная: id активной вкладки.
//    Меняется значение — Vue сам перерисует всё, что от него зависит.
const activeTab = ref('arrivals');

// 3. computed пересчитывается автоматически, когда меняется activeTab.
//    Он находит объект вкладки и отдаёт его компонент.
const currentTabComponent = computed(() => tabs.find((tab) => tab.id === activeTab.value)?.component);
</script>

<template>
  <div>
    <div class="page">
      <!-- Sidebar -->
      <aside class="page__sidebar sidebar">
        <div class="sidebar__profile">
          <div class="sidebar__avatar-wrapper">
            <img src="../assets/images/avatar.png" alt="User avatar" class="sidebar__avatar" />
            <button class="sidebar__settings-btn" aria-label="Настройки">
              <svg viewBox="0 0 24 24" class="sidebar__settings-icon">
                <path
                  d="M12 15a3 3 0 100-6 3 3 0 000 6z"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                />
                <path
                  d="M19.4 15a1.65 1.65 0 00.33 1.82l.06.06a2 2 0 010 2.83 2 2 0 01-2.83 0l-.06-.06a1.65 1.65 0 00-1.82-.33 1.65 1.65 0 00-1 1.51V21a2 2 0 01-2 2 2 2 0 01-2-2v-.09A1.65 1.65 0 009 19.4a1.65 1.65 0 00-1.82.33l-.06.06a2 2 0 01-2.83 0 2 2 0 010-2.83l.06-.06a1.65 1.65 0 00.33-1.82 1.65 1.65 0 00-1.51-1H3a2 2 0 01-2-2 2 2 0 012-2h.09A1.65 1.65 0 004.6 9a1.65 1.65 0 00-.33-1.82l-.06-.06a2 2 0 010-2.83 2 2 0 012.83 0l.06.06a1.65 1.65 0 001.82.33H9a1.65 1.65 0 001-1.51V3a2 2 0 012-2 2 2 0 012 2v.09a1.65 1.65 0 001 1.51 1.65 1.65 0 001.82-.33l.06-.06a2 2 0 012.83 0 2 2 0 010 2.83l-.06.06a1.65 1.65 0 00-.33 1.82V9a1.65 1.65 0 001.51 1H21a2 2 0 012 2 2 2 0 01-2 2h-.09a1.65 1.65 0 00-1.51 1z"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                />
              </svg>
            </button>
          </div>
        </div>
        <!-- /.sidebar__profile -->
        
        <nav class="sidebar__nav">
          <ul class="sidebar__list">
            <li v-for="tab in tabs" :key="tab.id" class="sidebar__item">
              <a href="#" class="sidebar__link" :class="{ 'sidebar__link--active': activeTab === tab.id }" @click.prevent="activeTab = tab.id">{{ tab.label }}</a>
            </li>
            <!-- <li class="sidebar__item">
              <a href="#" class="sidebar__link sidebar__link--active">ПРИХОД</a>
            </li>
            <li class="sidebar__item">
              <a href="#" class="sidebar__link">ГРУППЫ</a>
            </li>
            <li class="sidebar__item">
              <a href="#" class="sidebar__link">ПРОДУКТЫ</a>
            </li>
            <li class="sidebar__item">
              <a href="#" class="sidebar__link">ПОЛЬЗОВАТЕЛИ</a>
            </li>
            <li class="sidebar__item">
              <a href="#" class="sidebar__link">НАСТРОЙКИ</a>
            </li> -->
          </ul>
        </nav>
        <!-- /.sidebar__nav -->
      </aside>
      <!-- /.page__sidebar sidebar -->

      <!-- Main content -->
      <main class="page__content content">
        <!-- Сюда подставляется текущая страница -->
        <!-- <ArrivalsPage /> -->
        <component :is="currentTabComponent" />
      </main>
    </div>
    <!-- /.page -->
  </div>
</template>

<style scoped>
/* ===== PAGE LAYOUT ===== */
.page {
  display: flex;
  min-height: 100vh;
  background-color: #f5f5f5;
}
/* ===== SIDEBAR ===== */
.page__sidebar {
  width: 200px;
  background-color: #fff;
  border-right: 1px solid #e5e5e5;
  padding: 20px 15px;
  flex-shrink: 0; /* жёстко сохраняет исходный размер при изменении ширины экрана */
}
.sidebar__profile {
  margin-bottom: 30px;
}
.sidebar__avatar-wrapper {
  position: relative;
  width: 80px;
  height: 80px;
  margin: 0 auto;
}
.sidebar__avatar {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
}
.sidebar__settings-btn {
  position: absolute;
  bottom: 0;
  right: 0;
  width: 28px;
  height: 28px;
  border-radius: 50%;
  background-color: #fff;
  border: 2px solid #e0e0e0;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 2px;
  cursor: pointer;
  transition: all 0.2s ease-in-out;
}
.sidebar__settings-btn:hover {
  background-color: #d2cbcb;
}
.sidebar__settings-icon {
  width: 16px;
  height: 16px;
  color: #666;
}
.sidebar__item {
  margin-bottom: 8px;
}
.sidebar__link {
  /* display: block; */
  position: relative;
  display: inline-block;
  padding: 8px 0;
  color: #333;
  font-size: 14px;
  font-weight: 600;
  text-decoration: none;
  letter-spacing: 0.5px;
  transition: all 0.2s ease-in-out;
}
.sidebar__link::after {
  content: '';
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  height: 2px;
  background-color: #4caf50;
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.3s ease-in-out;
}
.sidebar__link:hover {
  color: #4caf50;
  background-color: transparent;
}
.sidebar__link:hover::after,
.sidebar__link--active::after {
  transform: scaleX(1);
}
.sidebar__link--active {
  color: #4caf50;
  /* border-bottom: 2px solid #4caf50; */
}
/* ===== CONTENT ===== */
.content {
  padding: 20px;
  flex: 1; /* Заставляет элемент растягиваться и занимать всю доступную ширину */
  overflow-x: auto; /* Добавляет прокрутку при изменении размера экрана */
}

/* ===== RESPONSIVE ===== */
@media (max-width: 992px) {
  .sidebar {
    width: 180px;
  }
  .content {
    padding: 20px 30px;
  }
  .card-arrival {
    gap: 16px;
    padding: 16px 20px;
  }
}
@media (max-width: 768px) {
  .page {
    flex-direction: column;
  }
  .sidebar {
    width: 100%;
    padding:  15px 20px;
  }
  .sidebar__profile {
    display: flex;
    align-items: center;
    gap: 16px;
    margin-bottom: 15px;
  }
  .sidebar__avatar-wrapper {
    width: 50px;
    height: 50px;
  }
  .sidebar__settings-btn {
    width: 20px;
    height: 20px;
  }
  .sidebar__nav {
    overflow-x: auto;
  }
  .sidebar__list {
    display: flex;
    gap: 8px;
    flex-wrap: nowrap;
  }
  .sidebar__link {
    padding: 6px 12px;
    font-size: 12px;
    white-space: nowrap;
  }
  .content {
    padding: 20px;
  }
  .card-arrival {
    /* flex-wrap: wrap; */
    grid-template-columns: auto 1fr auto;
    grid-template-areas:
      "title    title title"
      "products meta  delete";
    gap: 12px;
  }
  .card-arrival__title-wrapper {
    /* width: 100%; */
    /* flex: 0 0 100%;
    order: 1; */
    grid-area: title;
    min-width: 0;
  }
  .card-arrival__products {
    /* order: 2; */
  }
  .card-arrival__meta {
    /* order: 3; */
    justify-self: start;
  }
  .card-arrival__delete {
  }
}

@media (max-width: 576px) {
  .content {
    padding: 15px;
  }
  .content__title {
    font-size: 20px;
  }
  .card-arrival {
    padding: 12px 16px;
  }
  .card-arrival__products-count {
    font-size: 18px;
  }
  .card-arrival__date-full,
  .card-arrival__price-uah {
    font-size: 13px;
  }
  /*  */
  .card-arrival {
    grid-template-columns: 1fr auto;
    grid-template-areas:
      "title    title"
      "products delete"
      "meta     meta";
  }
}
</style> 