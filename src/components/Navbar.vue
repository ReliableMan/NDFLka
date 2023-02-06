<template>
  <div class="header">
    <div class="header__header-top">
      <div class="header__header-top__wrap">
        <div class="header__logos">
          <a href="" class="header__logo">
            <img class="adaptive-logo" src="@/assets/icons/logo.svg" alt="НДФЛка" width="179" height="36">
          </a>
        </div>
        <div class="header__phone-number">
          <!-- number for desktopPC -->
          <a href="tel:+74997057893" class="header__number pc-phoneLink">
            +7 (499) 705 78 93
          </a>
          <!-- number for mobile -->
          <a href="tel:+74997057893" class="mobile pad-mob">
            <img class="icon" src="../assets/icons/mob/call.svg" alt="mob-phone">
          </a>
        </div>
        <div class="header__faq-link">
          <!-- faq-link for desktopPC -->
          <a href="#" class="header__link pc-faqLink">
            вопросы и ответы
          </a>
          <!-- faq-link for mobile -->
          <a href="#" class="mobile pad-mob">
            <img class="icon" src="../assets/icons/mob/question.svg" alt="faq-phone">
          </a>
        </div>
        <div class="header__user-links">
          <!-- auth-links for desktopPC -->
          <a href="#" class="header__link header__user-link-login pc-userLink">Вход</a>
          <a href="#" class="header__link header__user-link-reg pc-userLink">Регистрация</a>
          <!-- auth-link toggle menu for mobile -->
          <a href="#" class="mobile pad-mob">
            <img class="icon" src="../assets/icons/mob/menu.svg" alt="user-link-phone">
          </a>
        </div>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '@/assets/styles/navbar.styles.scss';
</style>
