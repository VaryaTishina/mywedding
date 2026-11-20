<template>
  <div class="min-h-screen flex justify-center font-serif text-[#f4e9dc] relative">
    
    <!-- Сама открытка (ограничена по ширине для ПК) -->
    <div class="w-full max-w-lg relative z-10 flex flex-col items-center">

      <!-- ================= БЛОК 1: ПРИГЛАШЕНИЕ ================= -->
      <!-- Уменьшили pt-16 до pt-10 (верхний отступ) и pb-8 до pb-2 (нижний отступ) -->
      <section class="w-full flex flex-col items-center pt-10 pb-2 px-6 text-center">
        
        <!-- Именная вставка -->
        <div v-if="guestName" class="mb-4 w-full flex justify-center">
          <p class="font-corsiva text-3xl text-[#f4e9dc] drop-shadow-md text-center">{{ guestName }}</p>
        </div>
        <div v-else class="mb-4 w-full flex justify-center">
          <p class="text-sm font-sans font-semibold italic tracking-[0.2em] uppercase text-[#f4e9dc]/80">Дорогие гости</p>
        </div>

        <!-- Картинка с надписью "Приглашение на свадьбу" -->
        <div class="w-full flex justify-center mb-0 relative z-10 px-4">
          <img 
            src="./assets/title.png" 
            alt="Приглашение на свадьбу" 
            class="w-full max-w-[350px] md:max-w-[450px] h-auto object-contain title-blend"
          >
        </div>
      </section>

          <!-- ================= КАРТИНКА КОНВЕРТА (НА ВСЮ ШИРИНУ) ================= -->
      <!-- Выходим за рамки центральной колонки -->
      <div class="relative w-screen left-1/2 -translate-x-1/2 flex justify-center overflow-hidden py-4 pointer-events-none z-20">
        <img 
          src="./assets/envelope.png" 
          alt="Конверт с приглашением" 
          class="w-full h-auto object-cover opacity-0 animate-fade-in envelope-blend"
        >
      </div>

      <section class="w-full flex flex-col items-center pt-4 pb-8 px-6 text-center">
               <!-- Имена (Картинка) -->
        <div class="w-full flex justify-center mb-10 px-4">
          <img 
            src="./assets/names.png" 
            alt="Савва и Варвара" 
            class="w-full max-w-[280px] md:max-w-[350px] h-auto object-contain title-blend drop-shadow-md"
          >
        </div>
        
          <!-- Календарь (Картинка с анимацией) -->
          <div class="w-full flex justify-center mb-6 mt-2">
            <img 
              src="./assets/calendar.png" 
              alt="Календарь" 
              ref="calendarImage"
              class="w-full max-w-[280px] md:max-w-[320px] h-auto object-contain title-blend opacity-0 translate-y-8 transition-all duration-1000 ease-out"
            >
          </div>

               <!-- Локация (Картинка с анимацией и кнопкой) -->
        <div class="w-full flex justify-center relative mt-6">
          <img 
            src="./assets/location.png" 
            alt="Место проведения" 
            ref="locationImage"
            class="w-full max-w-[400px] md:max-w-[450px] h-auto object-contain opacity-0 translate-y-8 transition-all duration-1000 ease-out mix-blend-multiply"
          >
          
          <!-- НАЛОЖЕННАЯ КНОПКА -->
          <!-- Класс top-[56%] и w-[65%] подгоняют размер и положение кнопки под картинку -->
          <a 
            href="https://yandex.ru/maps/?text=Фурштатская ул., 52, Дворец Бракосочетания №2" 
            target="_blank" 
            class="absolute top-[44%] left-1/2 transform -translate-x-1/2 -translate-y-1/2 z-10 
                   w-[65%] h-[7%] rounded-full cursor-pointer opacity-0 transition-opacity duration-1000
                   hover:bg-white/20"
            ref="locationButton"
            title="Посмотреть на карте"
          >
            <!-- Кнопка специально сделана прозрачной, чтобы было видно нарисованную -->
          </a>
        </div>
      </section>

      <!-- Разделитель -->
      <div class="w-full flex justify-center py-2 opacity-50">
        <svg width="150" height="20" viewBox="0 0 100 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0 10 Q 25 20 50 10 T 100 10" stroke="#f4e9dc" stroke-width="1.5" fill="none"/></svg>
      </div>

      <!-- ================= БЛОК 2: ПРОГРАММА ================= -->
      <section class="w-full flex flex-col items-center py-12 px-6 text-center">

               <!-- Программа дня (Картинка с анимацией) -->
        <div class="w-full flex justify-center my-8 px-2">
          <img 
            src="./assets/program.png" 
            alt="Программа дня" 
            ref="programImage"
            class="w-full max-w-[400px] md:max-w-[500px] h-auto object-contain opacity-0 translate-y-8 transition-all duration-1000 ease-out mix-blend-multiply"
          >
        </div>
      <!-- Разделитель -->
      <div class="w-full flex justify-center py-2 opacity-50">
        <svg width="150" height="20" viewBox="0 0 100 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0 10 Q 25 20 50 10 T 100 10" stroke="#f4e9dc" stroke-width="1.5" fill="none"/></svg>
      </div>
       <!-- Дресс-код -->
<div class="w-full flex flex-col items-center">

  <!-- Картинка с примером наряда (если она нужна) -->
  <div class="w-full flex justify-center mb-4">
    <img 
      src="./assets/dresscode.png" 
      alt="Дресс-код" 
      class="w-full max-w-[200px] md:max-w-[250px] h-auto object-contain mix-blend-multiply"
    >
  </div>

  <p class="text-cursive font-sans font-semibold italic mb-6 px-4 text-[#f4e9dc]/70 leading-relaxed text-center">
    Будем благодарны, если Вы придете в нарядах, соответствующих<br>стилю нашей свадьбы:
  </p>
  
  <!-- Новая картинка с палитрой цветов -->
  <div class="w-full flex justify-center mb-6">
    <img 
      src="./assets/palette.png" 
      alt="Цветовая палитра свадьбы" 
      class="w-full max-w-md h-auto object-contain"
    >
  </div>

  <p class="text-cursive font-sans font-semibold italic mb-6 px-4 text-[#f4e9dc]/70 leading-relaxed text-center">
    Исключить образы состоящие полностью из белого<br>(и всех близких к нему оттенков) и черного цветов,<br>а также минимизировать их количество
  </p>
  
  <p class="text-cursive font-sans font-semibold italic mb-6 px-4 text-[#f4e9dc]/70 leading-relaxed text-center">
    Для девушек:<br>просьба взять с собой платок для <br>покрытия головы и плеч в соборе;<br>отдать предпочтение нарядам, закрывающим колени;<br>в случае выбора короткого наряда<br>просьба взять второй платок,<br>чтобы повязать его на пояс
  </p>
  
  <p class="text-cursive font-sans font-semibold italic mb-6 px-4 text-[#f4e9dc]/70 leading-relaxed text-center">
    Для мужчин:<br>отдать предпочтение классическому стилю;<br>допускается выбор костюма<br>черного, синего, серого<br>и других цветов,<br>отличных от цветовой палитры,<br>в таком случае, просьба выбрать<br>рубашку в соответствии с<br>цветовой палитрой
  </p>
</div>
      </section>

      <!-- Разделитель -->
      <div class="w-full flex justify-center py-2 opacity-50">
        <svg width="150" height="20" viewBox="0 0 100 20" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0 10 Q 25 20 50 10 T 100 10" stroke="#f4e9dc" stroke-width="1.5" fill="none"/></svg>
      </div>

      <!-- ================= БЛОК 3: АНКЕТА ГОСТЯ ================= -->
      <section class="w-full flex flex-col items-center py-12 px-6 pb-20 text-center">
        
        <div class="bg-black/40 backdrop-blur-lg border border-white/10 rounded-3xl p-6 w-full shadow-2xl">
          <p class="text-sm font-sans leading-relaxed mb-8 opacity-90 max-w-sm mx-auto text-[#f4e9dc]">
            Пожалуйста, заполните форму ниже. Это поможет нам в организации торжества.
          </p>

          <!-- ФОРМА -->
          <form @submit.prevent="submitForm" class="w-full max-w-sm mx-auto text-left font-sans flex flex-col gap-6">
            
            <input type="hidden" v-model="form.name" />

            <!-- Присутствие -->
<div>
  <label class="block text-xs tracking-wider uppercase mb-3 text-[#f4e9dc]/80">Сможете ли вы присутствовать?</label>
  <div class="flex flex-col gap-3">
    <label class="flex items-center gap-3 cursor-pointer group">
      <input v-model="form.attendance" type="radio" value="Да, с удовольствием буду" class="w-4 h-4 accent-[#f4e9dc]">
      <span class="text-sm group-hover:text-[#f4e9dc] transition-colors text-[#f4e9dc]/90">Да, с удовольствием буду</span>
    </label>
    <label class="flex items-center gap-3 cursor-pointer group">
      <input v-model="form.attendance" type="radio" value="К сожалению не смогу" class="w-4 h-4 accent-[#f4e9dc]">
      <span class="text-sm group-hover:text-[#f4e9dc] transition-colors text-[#f4e9dc]/90">К сожалению не смогу</span>
    </label>
  </div>
</div>

<!-- Напитки (появляются только если гость придёт) -->
<div v-if="form.attendance === 'Да, с удовольствием буду'">
  <label class="block text-xs tracking-wider uppercase mb-3 text-[#f4e9dc]/80">Предпочтение по напиткам:</label>
  <div class="grid grid-cols-2 gap-3">
    <label v-for="drink in drinks" :key="drink" class="flex items-center gap-3 cursor-pointer group">
      <input 
        v-model="form.drink" 
        type="radio" 
        :value="drink" 
        name="drink"
        class="w-4 h-4 accent-[#f4e9dc]"
      >
      <span class="text-sm group-hover:text-white transition-colors text-[#f4e9dc]/90">{{ drink }}</span>
    </label>
  </div>
</div>

            <!-- Кнопка -->
            <button type="submit" :disabled="isSubmitting" class="mt-4 bg-[#f4e9dc] text-[#4a0e14] font-bold py-4 rounded-full text-sm tracking-widest uppercase hover:bg-white transition-colors disabled:opacity-50 shadow-lg pointer-events-auto">
              {{ isSubmitting ? 'Отправка...' : 'Отправить' }}
            </button>
            
            <!-- Сообщение -->
            <div v-if="isSubmitted" class="text-green-200 text-sm text-center mt-2 bg-green-900/50 p-3 rounded-lg border border-green-500/30">
              Спасибо! Ваш ответ записан.
            </div>
          </form>
        </div>

                <!-- Прощание -->
        <div class="mt-16 w-full flex flex-col items-center">
          <p class="text-xs tracking-[0.2em] uppercase mb-3 text-[#f4e9dc]/70">С нетерпением ждем</p>
          <p class="text-xs tracking-[0.2em] uppercase mb-8 text-[#f4e9dc]/70">встречи на нашей свадьбе!</p>
          
          <!-- Имена в конце (Картинка) -->
          <div class="w-full flex justify-center px-4">
            <img 
              src="./assets/names.png" 
              alt="Савва и Варвара" 
              class="w-full max-w-[250px] md:max-w-[300px] h-auto object-contain title-blend drop-shadow-md"
            >
          </div>
        </div>
      </section>

    </div>
  </div>
</template>

<script setup>
import { ref, reactive, onMounted, onUnmounted, watch } from 'vue'

const GOOGLE_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbyl_u0F7R4XMJ77lUcoVgiR7HNsFwwLkGSCsx64Y4hy-e_IHsq3FSbqfuA3etdeE3ZF/exec'
const guestName = ref('')

// Ссылки на элементы для анимации
const calendarImage = ref(null)
const locationImage = ref(null)
const locationButton = ref(null)
const programImage = ref(null)

// Переменные видимости
const isCalendarVisible = ref(false)
const isLocationVisible = ref(false)
let observer = null

const form = reactive({
  name: '',
  attendance: 'Да, с удовольствием буду',
  drink: '' // было drinks: []
})

const drinks = ['Вино красное полусладкое', 'Вино белое сухое ', 'Шампанское полусладкое', 'Шампанское брют', 'Водка', 'Самогон-Егермейстер', 'Самогон-Коньяк', 'Самогон-Лимончелло', 'Не пью алкоголь']
const isSubmitting = ref(false)
const isSubmitted = ref(false)

watch(() => form.attendance, (newValue) => {
  if (newValue === 'К сожалению не смогу') {
    form.drink = '' // очищаем выбор напитка
  }
})

onMounted(() => {
  // 1. Логика для получения имени из URL
  const urlParams = new URLSearchParams(window.location.search)
  const nameFromUrl = urlParams.get('guest')
  
  if (nameFromUrl) {
    guestName.value = nameFromUrl
    form.name = nameFromUrl
  } else {
    form.name = 'Дорогой гость'
  }

  // 2. Логика для появления картинок при скролле
  observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
      if (entry.isIntersecting) {
        
        // Если это календарь
        if (entry.target === calendarImage.value) {
          isCalendarVisible.value = true
          entry.target.classList.remove('opacity-0', 'translate-y-8')
          entry.target.classList.add('opacity-100', 'translate-y-0')
        }
        
        // Если это локация
        if (entry.target === locationImage.value) {
          isLocationVisible.value = true
          entry.target.classList.remove('opacity-0', 'translate-y-8')
          entry.target.classList.add('opacity-100', 'translate-y-0')
          
          // Показываем наложенную кнопку с небольшой задержкой (чтобы она появилась после картинки)
          setTimeout(() => {
            if (locationButton.value) {
              locationButton.value.classList.remove('opacity-0')
              locationButton.value.classList.add('opacity-100')
            }
          }, 500)
        }

        if (entry.target === programImage.value) {
          entry.target.classList.remove('opacity-0', 'translate-y-8')
          entry.target.classList.add('opacity-100', 'translate-y-0')
        }
        // Отключаем наблюдение за этим конкретным элементом, чтобы анимация сработала только 1 раз
        observer.unobserve(entry.target)
      }
    })
  }, {
    threshold: 0.2 // Анимация сработает, когда элемент покажется на 20% на экране
  })

  // Начинаем следить за тремя картинками
  if (calendarImage.value) {
    observer.observe(calendarImage.value)
  }
  if (locationImage.value) {
    observer.observe(locationImage.value)
  }
  if (programImage.value) {
    observer.observe(programImage.value)
  }
})

// Отключаем наблюдатель при закрытии страницы
onUnmounted(() => {
  if (observer) {
    observer.disconnect()
  }
})

// Функция отправки формы
const submitForm = async () => {

  if (form.attendance === 'Да, с удовольствием буду' && !form.drink) {
    alert('Пожалуйста, выберите напиток')
    return
  }

  isSubmitting.value = true
  try {
    await fetch(GOOGLE_SCRIPT_URL, {
      method: 'POST',
      mode: 'no-cors',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify({
        name: form.name,
        attendance: form.attendance,
        drinks: form.attendance === 'Да, с удовольствием буду' ? form.drink : ''
      })
    })
    isSubmitted.value = true
    form.attendance = 'Да, с удовольствием буду'
    form.drink = ''
    setTimeout(() => { isSubmitted.value = false }, 5000)
  } catch (error) {
    console.error('Ошибка отправки:', error)
    alert('Произошла ошибка при отправке. Попробуйте позже.')
  } finally {
    isSubmitting.value = false
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Marck+Script&family=Montserrat:wght@300;400;600&display=swap');

.font-serif { font-family: 'Montserrat', sans-serif; }
.font-cursive { font-family: 'Marck+Script', cursive; }
html { scroll-behavior: smooth; }

body {
  background-image: url('./assets/bg.jpg'); 
  background-size: cover;
  background-position: center;
  background-attachment: fixed;
  background-repeat: no-repeat;
  margin: 0;
}

@media (max-width: 768px) {
  body {
    background-attachment: scroll;
  }
}

/* === АНИМАЦИЯ ПОЯВЛЕНИЯ КАРТИНКИ === */
@keyframes fadeInImage {
  0% {
    opacity: 0;
    transform: translateY(20px) scale(0.95); /* Легкое движение вверх и уменьшение */
  }
  100% {
    opacity: 1;
    transform: translateY(0) scale(1);
  }
}

.animate-fade-in {
  /* 1.5s - длительность; ease-out - плавное замедление в конце; forwards - оставить в конечном состоянии */
  animation: fadeInImage 1.5s ease-out forwards; 
  /* Небольшая задержка, чтобы сайт успел прогрузиться */
  animation-delay: 0.3s; 
}

/* 
  Секрет красивого слияния с фоном:
  Поскольку у вашей картинки белый фон, mix-blend-mode: multiply 
  сделает белый цвет прозрачным, а конверт и руки останутся.
*/
.mix-blend-multiply {
  mix-blend-mode: multiply;
}
</style>