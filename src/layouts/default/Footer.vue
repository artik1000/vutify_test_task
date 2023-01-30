<template>
  <v-container height="fit-content" class="px-60px bg-primary footer d-flex flex-row justify-space-between" fluid tag="footer">
    <div class="d-flex flex-row">
      <img
        class="my-auto align-self-start footer-img"
        alt="Логотип"
        src="@/assets/logo__footer.svg"
        width="132px"
        height="35px"
      />
      <div class="footer__text my-auto ml-92px">© 2022 Центр дистанционных торгов</div>
    </div>
    <div class="my-auto"><pre class="footer__text"> Нашли ошибку? Напишите нам об этом <a class="footer__text my-auto" href="help@cdtrf.ru">help@cdtrf.ru</a></pre></div>
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
}
.v-img__img{
  width: auto !important;
}
.footer-img{
  width: 132px !important;
  height: 35px !important;
  display: block;
}
.ml-92px{
  margin-left: 92px;
}
</style>
