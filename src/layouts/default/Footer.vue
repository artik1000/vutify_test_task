<template>
  <v-container height="fit-content" class="px-60px bg-primary footer" fluid>
    <v-row class="d-flex flex-row gap-24px ma-0">
      <v-img
        class="my-auto"
        alt="Логотип"
        src="@/assets/logo__footer.svg"
        :width="'132px'"
        :height="'35px'"
      />
      <p class="footer__text my-auto">© 2022 Центр дистанционных торгов</p><pre class="footer__text my-auto"> Нашли ошибку? Напишите нам об этом <a class="footer__text my-auto" href="help@cdtrf.ru">help@cdtrf.ru</a></pre>
    </v-row>
  </v-container>
</template>

<script>
export default {
  name: "footer"
}
</script>

<style>
.footer{
  height: 55px;
}
.footer__text{
  font-family: 'Arimo';
  font-style: normal;
  font-weight: 400;
  font-size: 12px;
  line-height: 140%;
  /* identical to box height, or 17px */

  display: flex;
  align-items: center;
  text-align: center;

  /* White */

  color: #FFFFFF;

  opacity: 0.5;
  display: flex;
}
</style>
