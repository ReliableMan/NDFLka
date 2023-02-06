<script setup>
import { ref, onUpdated } from 'vue';

const emailValue = ref('');
const disabled = ref(true);
const emit = defineEmits(['valueForPhone'])

onUpdated(() => {
  emailValue.value.length ? disabled.value = false : disabled.value = true ;
  console.log('email-value: ', emailValue.value)
});
function changeForm () {
  emit('valueForPhone')
}
</script>

<template>
   <div class="form">
        <form  class="auth-email-form">
          <div class="section1">
            <p class="email-form-title">
              На почту будет отправлена временная ссылка для входа.
            </p>
          </div>
          <div class="email-form-input-btn">
            <div class="form__email">
              <input v-model="emailValue" class="form__email__input" name="email" autofocus="autofocus"
                placeholder="Введите email" type="email" aria-required="true">
            </div>
            <div class="form__btn">
              <button :disabled="disabled" type="button" class="form__email__button">Получить ссылку</button>
            </div>
          </div>
          <div class="section2">
           <div class="checkbox">
             <label for="privacy" class="text">
              Авторизуясь на сайте, вы соглашаетесь с <a href="https://ndflka.ru/documents/privacy/" class="text" target="_blank">политикой конфиденциальности</a>
              и даете согласие на обработку персональных данных, а также подтверждаете, 
              что <a href="https://ndflka.ru/documents/eula/" class="text" target="_blank">ознакомлены и согласны с условиями Договора</a>.
            </label>
             <input class="real-checkbox" type="checkbox" id="privacy" checked="checked">
             <span class="custom-checkbox"></span>
           </div>
            <div class="section2-buttons">
              <button class="section2-btn" @click="changeForm" type="button">Войти с помощью телефона</button>
            </div>
          </div>
        </form>
      </div>
</template>

<style lang="scss" scoped>
@import '@/assets/styles/reg-email.styles.scss';
</style>
