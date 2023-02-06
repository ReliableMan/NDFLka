<script setup>
import { ref, onUpdated } from 'vue';

const authPhoneValue = ref('');
const disabled = ref(true);
const emit = defineEmits(['valueForPhoneAuth', 'sectionWorking'])
const props = defineProps({
  hide: {
  type: Boolean, 
  default: false,
  }
});

onUpdated(() => {
  authPhoneValue.value.length ? disabled.value = false : disabled.value = true ;
  console.log('authPhoneValue: ', authPhoneValue.value)
});
function changeForm () {
  emit('valueForPhoneAuth')
};
function open () {
  emit('sectionWorking')
};
</script>

<template>
  <div class="auth-container">
    <div class="auth-mobile">
      <span class="auth-title active">Вход</span>
      <a href="https://ndflka.ru/user/signup/"  class="auth-title link">Регистрация</a>
    </div>
    <div class="auth-content">
      <span class="auth-content__text">На указанный телефон придет СМС с кодом для входа</span>
      <input v-model="authPhoneValue" class="auth-content__input-email text-input pd-t" name="tel" 
      autofocus="autofocus" placeholder="Телефон" type="tel" aria-required="true">
      <button :disabled="disabled" class="auth-content__button-tel pd-t">Войти по смс-коду</button>
      <button @click="changeForm" class="auth-content__button-email pd-t">Войти по email</button>
      <div class="checkbox pd-t">
        <input class="real-checkbox" type="checkbox" id="privacy" checked="checked">
        <span class="custom-checkbox"></span>
        <label for="privacy" class="text">
          Оставляя контактные данные, вы соглашаетесь с <a href="https://ndflka.ru/documents/privacy/" class="text" target="_blank">политикой конфиденциальности</a>
          и даете согласие на обработку персональных данных, <br/>а также подтверждаете, 
          что <a href="https://ndflka.ru/documents/eula/" class="text" target="_blank">ознакомлены и согласны с условиями Договора</a>.
        </label>
      </div>
      <button v-if="!hide" @click="open" class="section-work pd-t">
        <img src="@/assets/icons/question-mark.svg" alt="">
        <span class="section-work__text">Как мы работаем</span>
      </button>
    </div>
  </div>
</template>

<style lang="scss" scoped>
@import '@/assets/styles/reg-mobile-auth.styles.scss';
</style>
