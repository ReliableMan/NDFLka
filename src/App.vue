<script setup>
  import Navbar from '@/components/Navbar.vue';
  import RegEmail from '@/components/RegEmail.vue'
  import RegPhone from '@/components/RegPhone.vue';
  import SectionWork from '@/components/SectionWork.vue';
  import RegEmailAuth from './components/RegEmailAuth.vue';
  import RegMobileAuth from '@/components/RegMobileAuth.vue';
  import SectionWorkMobile from './components/SectionWorkMobile.vue';
  import { ref } from 'vue';

  const emailForm = ref(true);
  const phoneForm = ref(false);

  const emailAuthForm = ref(true);
  const phoneAuthForm = ref(false);

  const valueHowWorking = ref(false)

  function changeForm () {
    emailForm.value = !emailForm.value;
    phoneForm.value = !phoneForm.value;
  }
  function changeAuthForm () {
    emailAuthForm.value = !emailAuthForm.value;
    phoneAuthForm.value = !phoneAuthForm.value;
    valueHowWorking.value = false
  }
  function openSection () {
    valueHowWorking.value = !valueHowWorking.value;
  }

</script> 

<template>
  <navbar/>
  <div class="main">
    <div class="wrap">
      <h1 class="title">Вход</h1>
        <reg-email v-if="emailForm" @valueForPhone="changeForm"/>
        <reg-phone v-if="phoneForm" @valueForEmail="changeForm"/>
        <section-work/>
      </div>
  </div>
  <reg-mobile-auth class="isNone" v-if="emailAuthForm" 
  :hide="valueHowWorking" @valueForPhoneAuth="changeAuthForm" @sectionWorking="openSection"/>
  <reg-email-auth class="isNone" v-if="phoneAuthForm" 
  :hide="valueHowWorking" @valueForEmailAuth="changeAuthForm" @sectionWorking="openSection"/>

  <section-work-mobile v-if="valueHowWorking"/>
</template>

<style lang="scss" scoped>
@import '@/assets/styles/app.styles.scss';

</style>
