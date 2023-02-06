<script setup>
import { ref, onUpdated } from 'vue';

const phoneValue = ref('');
const disabled = ref(true);
const emit = defineEmits(['valueForEmail'])

onUpdated(() => {
  phoneValue.value.length ? disabled.value = false : disabled.value = true ;
  console.log('phone-value: ', phoneValue.value)
});
function changeForm () {
  emit('valueForEmail')
}
</script>

<template>
   <div class="form">
        <form class="auth-phone-form">
          <div class="section1">
            <p class="email-phone-title">
              На указанный телефон придет СМС с кодом для входа.
            </p>
          </div>
          <div class="phone-form-input-btn">
            <div class="form__phone">
              <input v-model="phoneValue" class="form__phone__input" name="tel" autofocus="autofocus"
                placeholder="Телефон" type="tel" aria-required="true">
            </div>
            <div class="form__btn">
              <button :disabled="disabled" type="button" class="form__phone__button">Войти по смс-коду</button>
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
              <button class="section2-btn" @click="changeForm" type="button">ВОЙТИ ПО EMAIL</button>
            </div>
          </div>
        </form>
      </div>
</template>

<style lang="scss" scoped>
@import '@/assets/styles/reg-phone.styles.scss';
</style>
