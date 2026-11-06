<script setup>
import { ref } from 'vue';

// Данные тоже выносим в массив. Потом их легко заменить данными с сервера.
const arrivals = ref([
  {
    id: 1, title: 'Длинное предлинное длиннющее название прихода',
    products: 23, day: '04 / 12', date: '06 / Aпр / 2017',
    usd: '2 500 $', uah: '250 000.50 UAH'
  },
  {
    id: 2, title: 'Длинное название прихода',
    products: 23, day: '09 / 12', date: '06 / Сен / 2017',
    usd: null, uah: '50 UAH'
  },
]);

// id выбранной карточки (null = ничего не выбрано)
const activeArrivalId = ref(null);

// функция для выбора карточки прихода. Вызывается при клике на карточку.
function selectedArrival(id) {
  activeArrivalId.value = id;
};

// функция для удаления прихода. Вызывается при клике на кнопку удаления.
function removeArrival(id) {
  // Удаляем приход из массива arrivals
  arrivals.value = arrivals.value.filter(arrival => arrival.id !== id);
  // Если удаляемый приход был выбранным, сбрасываем выбор
  if (activeArrivalId.value === id) {
    activeArrivalId.value = null;
  }
}
</script>

<template>
  <div>
    <main>
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
</template>

<style scoped>
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
  .card-arrival {
    gap: 16px;
    padding: 16px 20px;
  }
}
@media (max-width: 768px) {
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