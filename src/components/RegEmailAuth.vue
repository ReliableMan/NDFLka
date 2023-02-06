<script setup>
import { ref, onUpdated } from 'vue';

const authEmailValue = ref('');
const disabled = ref(true);
const emit = defineEmits(['valueForEmailAuth', 'sectionWorking'])

const props = defineProps({
  hide: {
  type: Boolean, 
  default: false,
  }
});

onUpdated(() => {
  authEmailValue.value.length ? disabled.value = false : disabled.value = true ;
  console.log('authEmailValue: ', authEmailValue.value)
});
function changeForm () {
  emit('valueForEmailAuth')
}
function open () {
  emit('sectionWorking')
};
</script>

<template>
  <div class="auth-container">
    <div class="auth-email">
      <span class="auth-title active">Вход</span>
      <a href="https://ndflka.ru/user/signup/"  class="auth-title link">Регистрация</a>
    </div>
    <div class="auth-content">
      <span class="auth-content__text">На почту будет отправлена временная ссылка для входа.</span>
      <input v-model="authEmailValue" class="auth-content__input-email text-input pd-t" name="email" 
      autofocus="autofocus" placeholder="Введите email" type="email" aria-required="true">
      <button :disabled="disabled" class="auth-content__button-tel pd-t">Получить ссылку</button>
      <button @click="changeForm" class="auth-content__button-email pd-t">Войти с помощью телефона</button>
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
@import '@/assets/styles/reg-email-auth.styles.scss';
</style>
