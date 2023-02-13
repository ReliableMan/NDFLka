<template>
  <div class="section-working">
          <div class="section-container">
          <h2 class="section-working__title">Как мы работаем</h2>
          <div class="section-working__stages">
            <!-- 1 блок -->
            <div class="container-1">
              <div class="container-1__stage-1">
                <picture>
                  <source srcset="">
                  <img src="@/assets/img/1-phone_call.svg" alt="work-image-1">
                </picture>
              <p class="text text1">Звонок, регистрация, заказ</p>
              </div>
              <img class="arrow-down-svg" src="@/assets/icons/arrow-down.svg" alt="arrow-down">
            </div>
            <!-- 2 блок -->
            <div class="container-2">
              <div class="container-2__stage-2">
                <picture>
                  <source srcset="">
                  <img src="@/assets/img/2-talking.svg" alt="work-image-2">
                </picture>
              <p class="text text2">Консультация</p>
              </div>
              <img class="arrow-up-svg" src="@/assets/icons/arrow-up.svg" alt="arrow-up">
            </div>
            <!-- 3 блок -->
            <div class="container-1 third-block">
              <div class="container-1__stage-1">
                <picture>
                  <source srcset="">
                  <img src="@/assets/img/3-money.svg" alt="work-image-3">
                </picture>
              <p class="text text3">Оплата заказа, загрузка документов</p>
              </div>
              <img class="arrow-down-svg third-row" src="@/assets/icons/arrow-down.svg" alt="arrow-down">
            </div>
            <!-- 4 блок -->
            <div class="container-2 fifth-block">
              <div class="container-2__stage-2">
                <picture>
                  <source srcset="">
                  <img src="@/assets/img/4-docs.svg" alt="work-image-4">
                </picture>
              <p class="text text4 centered">Проверка документов, заполнение и отправка декларации</p>
              </div>
              <img class="arrow-up-svg2" src="@/assets/icons/arrow-up.svg" alt="arrow-up">
            </div>
            <!-- 5 блок -->
            <div class="container-1">
              <div class="container-1__stage-1">
                <picture>
                  <source srcset="">
                  <img src="@/assets/img/5-happiness.svg" alt="work-image-5">
                </picture>
              <p class="text text3">Поступление денег от ФНС</p>
              </div>
            </div>
          </div>
        </div>
        </div>
</template>

<style lang="scss" scoped>
@import '../assets/styles/section-work.styles.scss';
</style>
