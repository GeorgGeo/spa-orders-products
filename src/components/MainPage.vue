<script setup></script>

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
            <li class="sidebar__item">
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
            </li>
          </ul>
        </nav>
        <!-- /.sidebar__nav -->
      </aside>
      <!-- /.page__sidebar sidebar -->

      <!-- Main content -->
      <main class="page__content content">
        <!-- Header -->
        <div class="content__header">
          <button class="content__add-btn btn btn-success rounded-circle" aria-label="Добавить приход">
            <svg viewBox="0 0 24 24" class="content__add-icon">
              <path d="M12 5v14M5 12h14" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
            </svg>
          </button>
          <h1 class="content__title">Приходы / 25</h1>
        </div>
        <!-- /.content__header -->

        <!-- Arrivals List -->
        <div class="content__list">
          <!-- Карточка прихода 1 -->
          <div class="card-arrival">
            <div class="card-arrival__title-wrapper">
              <a href="#" class="card-arrival__title">Длинное предлинное длиннющее название прихода</a>
            </div>

            <div class="card-arrival__products">
              <div class="card-arrival__products-icon">
                <svg viewBox="0 0 24 24">
                  <path d="M8 6h13M8 12h13M8 18h13M3 6h.01M3 12h.01M3 18h.01" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
                </svg>
              </div>
              <div class="card-arrival__products-info">
                <div class="card-arrival__products-count">23</div>
                <div class="card-arrival__products-label">Продукта</div>
              </div>
            </div>

            <div class="card-arrival__meta">
              <div class="card-arrival__date">
                <div class="card-arrival__date-day"> 04 / 12</div>
                <div class="card-arrival__date-full"> 06 / Aпр / 2017</div>
              </div>

              <div class="card-arrival__price">
                <div class="card-arrival__price-usd">2 500 $</div>
                <div class="card-arrival__price-uah">250 000.50 UAH</div>
              </div>
            </div>
            <!-- /.card-arrival__meta -->

            <button class="card-arrival__delete" aria-label="Удалить приход">
              <svg viewBox="0 0 24 24">
                <path d="M3 6h18M19 6v14a2 2 0 01-2 2H7a2 2 0 01-2-2V6m3 0V4a2 2 0 012-2h4a2 2 0 012 2v2" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
              </svg>
            </button>
          </div>
          <!-- Карточка прихода 2 -->
          <div class="card-arrival">
            <div class="card-arrival__title-wrapper">
              <a href="#" class="card-arrival__title card-arrival__title--active">Длинное название прихода</a>
            </div>

            <div class="card-arrival__products">
              <div class="card-arrival__products-icon">
                <svg viewBox="0 0 24 24">
                  <path d="M8 6h13M8 12h13M8 18h13M3 6h.01M3 12h.01M3 18h.01" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
                </svg>
              </div>
              <div class="card-arrival__products-info">
                <div class="card-arrival__products-count">23</div>
                <div class="card-arrival__products-label">Продукта</div>
              </div>
            </div>

            <div class="card-arrival__meta">
              <div class="card-arrival__date">
                <div class="card-arrival__date-day"> 09 / 12</div>
                <div class="card-arrival__date-full"> 06 / Сен / 2017</div>
              </div>

              <div class="card-arrival__price">
                <div class="card-arrival__price-uah">50 UAH</div>
              </div>
            </div>
            <!-- /.card-arrival__meta -->

            <button class="card-arrival__delete" aria-label="Удалить приход">
              <svg viewBox="0 0 24 24">
                <path d="M3 6h18M19 6v14a2 2 0 01-2 2H7a2 2 0 01-2-2V6m3 0V4a2 2 0 012-2h4a2 2 0 012 2v2" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" />
              </svg>
            </button>
          </div>
        </div>
        <!-- /.content__list -->
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
.content__header {
  display: flex;
  align-items: center;
  gap: 16px;
  margin-bottom: 20px;
}
.content__add-btn {
  width: 36px;
  height: 36px;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
  flex-shrink: 0; /* жёстко сохраняет исходный размер при изменении ширины экрана */
}
.content__add-icon {
  width: 20px;
  height: 20px;
}
.content__title {
  font-size: 24px;
  font-weight: 600;
  color: #2c3e50;
  margin: 0;
}
/* ===== CARD ARRIVAL ===== */
.card-arrival {
  /* display: flex;
  align-items: center; */
  display: grid;
  grid-template-columns: 1fr auto auto auto;
  grid-template-areas: "title products meta delete";
  align-items: center;
  gap: 20px;
  padding: 20px 24px;
  background-color: #fff;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  transition: all 0.2s ease-in-out;
}
.card-arrival:hover {
  box-shadow: 0 2px 10px rgba(0, 0, 0, 0.1);
}
.card-arrival__title-wrapper {
  flex: 1;
  min-width: 0; /* Убирает отступы слева и справа для элемента с автоматическим растягиванием ширины, нужен для правильного растягивания ширины элемента */
}
.card-arrival__title {
  color:#2c3e50;
  text-decoration: none;
  font-size: 16px;
  border-bottom: 1px solid transparent;
  transition: all 0.2s ease-in-out;
  display: inline-block;
  position: relative;
}
.card-arrival__title::after {
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
.card-arrival__title:hover {
  border-bottom-color: #4caf50;
  color: #4caf50;
  background-color: transparent;
}
.card-arrival__title:hover::after,
.card-arrival__title--active::after {
  transform: scaleX(1);
}
.card-arrival__title--active {
  color: #4caf50;
}
.card-arrival__products {
  display: flex;
  align-items: center;
  gap: 8px;
  flex-shrink: 0; /* жёстко сохраняет исходный размер при изменении ширины экрана */
}
.card-arrival__products-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  border: 1px solid #e0e0e0;
  padding: 5px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-shrink: 0; /* жёстко сохраняет исходный размер при изменении ширины экрана */
}
.card-arrival__products-info {
  display: flex;
  flex-direction: column;
  /* gap: 4px; */
}
.card-arrival__products-count {
  font-size: 20px;
  font-weight: 600;
  color: #2c3e50;
  line-height: 1;
}
.card-arrival__products-label {
  font-size: 12px;
  color: #999;
  margin-top: 4px;
}
.card-arrival__meta {
  display: flex;
  align-items: flex-end; /* нижние строки даты и цены на одной линии */
  gap: 20px;
  flex-shrink: 0;
}
.card-arrival__date {
  display: flex;
  flex-direction: column;
  align-items: center;
  /* align-self: flex-end; */
  flex-shrink: 0; /* жёстко сохраняет исходный размер при изменении ширины экрана */
  min-width: 100px; 
}
.card-arrival__date-day {
  font-size: 12px;
  color: #999;
}
.card-arrival__date-full {
  font-size: 14px;
  color: #2c3e50;
  font-weight: 500;
}
.card-arrival__price {
  display: flex;
  flex-direction: column;
  align-items: start; /*  */
  flex-shrink: 0; /* жёстко сохраняет исходный размер при изменении ширины экрана */
  min-width: 120px; 
}
.card-arrival__price-usd {
  font-size: 12px;
  color: #999;
}
.card-arrival__price-uah {
  font-size: 14px;
  color: #2c3e50;
  font-weight: 500;
}
.card-arrival__delete {
  background: none;
  border: none;
  padding: 8px;
  cursor: pointer;
  color: #999;
  transition: all 0.2s ease-in-out;
  flex-shrink: 0; /* жёстко сохраняет исходный размер при изменении ширины экрана */
}
.card-arrival__delete:hover {
  color: #e74c3c;
}
.card-arrival__delete svg {
  width: 20px;
  height: 20px;
  display: block;
  transition: rotate 0.5s ease, scale 0.5s ease-in-out;
}
.card-arrival__delete:hover svg {
  rotate: 360deg;
  scale: 1.2;
}
/* ===== CARD ARRIVAL ===== */

.card-arrival__title-wrapper { grid-area: title;    min-width: 0; }
.card-arrival__products      { grid-area: products; }
.card-arrival__meta          { grid-area: meta; }
.card-arrival__delete        { grid-area: delete; }
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
    /* order: 5;
    margin-left: auto; */
  }
  /*  */
  /* .card-arrival {
    grid-template-columns: auto 1fr auto;
    grid-template-areas:
      "title    title title"
      "products meta  delete";
    gap: 12px;
  }
  .card-arrival__meta {
    justify-self: start;
  } */
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