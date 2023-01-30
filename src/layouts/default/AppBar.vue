<template>
  <v-container height="fit-content" class="px-60px" fluid>
      <v-row class="d-flex flex-row bg-white gap-24px ma-0">
        <v-col
          class="d-flex py-12px gap-24px"
        >
          <v-img
            class="my-auto"
            alt="Логотип"
            src="@/assets/logo.svg"
            :width="'189px'"
            :height="'50.1px'"
          />
          <v-list-item class="my-auto">
            <v-list-item-title class="header__time-header">10:50 (мск)</v-list-item-title>
            <v-list-item-subtitle class="header__date-header">чт, 13 октября 2022</v-list-item-subtitle>
          </v-list-item>
          <h6 class="header__phone-number my-auto">8 800 700 50 40</h6>
        </v-col>
        <v-col class="d-flex gap-24px justify-end py-27px my-auto">
          <v-btn class="bg-primary rounded-pill button elevation-0">+ Продать лот</v-btn>
          <v-btn class="btn-gray rounded-pill button elevation-0">Войти</v-btn>
        </v-col>
      </v-row>
  </v-container>
  <v-container height="fit-content" class="px-60px bg-primary d-flex flex-row" fluid @mouseleave="show = false">
    <v-list class="d-flex flex-row bg-transparent w-100 gap-12px overflow-visible" nav tag="nav"  @mouseleave="show = false">
      <v-list-item
        class="position-relative"
        v-for="(link,id) in router.getRoutes().filter(route => route.name === 'default')[0].children"
        :key="id"
        :title="link.name"
        :to="router.getRoutes().filter(route => route.name === 'default')[0].path + link.path"
        :class="(link.path === 'trades')?'v-list-item--bordered':''"
        @mouseover="showDropdown(link.path)"
      >
        <v-card
          v-if="link.path === 'our_services' && show === true"
          class="position-absolute mt-25px p13-19px"
          style="z-index: 9 !important;"
        >
          <h2
            class="dropdown-item"
            v-for="(item, id) in link.children"
              :key="id"
          >
            {{item.name}}
          </h2>
        </v-card>
      </v-list-item>
    </v-list>
    <v-btn class="my-auto bg-transparent elevation-0 px-12px" color="primary">
      <v-icon dark big>mdi-magnify</v-icon>
    </v-btn>
  </v-container>
</template>

<script setup>
import router from "@/router"
</script>
<script>
export default {
  data () {
    return {
      show: false,
    }
  },
  methods: {
    showDropdown (name){
      if(name === 'our_services'){
        this.show = true
      }
    }
  }
}
</script>
<style>
.v-list-item--bordered{
  border: 1px solid white !important;
}
.v-list-item--active > .v-list-item__overlay, .v-list-item[aria-haspopup=menu][aria-expanded=true] > .v-list-item__overlay {
}
.gap-24px{
  gap: 24px
}
.gap-12px{
  gap: 12px
}
.py-27px{
  padding: 27px 0px !important;
}
.py-12px{
  padding: 12px 0px !important;
}
.header__time-header{
  font-family: 'Arimo';
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 140%;
  display: flex;
  align-items: center;
  color: #222222;
}
.header__date-header{
  font-family: 'Arimo';
  font-style: normal;
  font-weight: 400;
  font-size: 14px;
  line-height: 140%;
  display: flex;
  align-items: center;
  color: #222222;
}
.header__phone-number{
  font-family: 'Arimo';
  font-style: normal;
  font-weight: 400;
  font-size: 20px;
  line-height: 140%;
  color: #222222;
}
.button{
  padding: 0px 16px !important;
  font-family: 'Arimo' !important;
  font-style: normal;
  font-weight: 700 !important;
  font-size: 14px !important;
  line-height: 36px !important;
}
.btn-gray{
  background: #E9E9E9 !important;
}
.v-list-item{
  font-family: 'Arimo';
  font-style: normal;
  font-weight: 400 !important;
  font-size: 16px !important;
  line-height: 140% !important;
}
.v-list .v-list-item--nav:not(:only-child) {
  margin-bottom: 0px !important;
}
.v-list-item--density-default.v-list-item--one-line {
  min-height: 1px !important;
  padding-top: 4.5px !important;
  padding-bottom: 4.5px !important;
}
.px-12px{
  padding: 0px 12px !important;
}
.v-btn--size-default{
  min-width: 1px !important;
}
.v-list-item:hover{
  background-color: white;
  color: #3C6EBD;
}
.v-card{
  box-shadow: 0px 0px 35px rgba(0, 0, 0, 0.15) !important;
  border-radius: 8px !important;
  padding: 24px 24px !important;
}
.mt-25px{
  margin-top: 14px !important;
}
.overflow-visible{
  overflow: visible !important;
}
.dropdown-item{
  font-family: 'Arimo' !important;
  font-style: normal !important;
  font-weight: 400 !important;
  font-size: 14px !important;
  line-height: 140% !important;
  /* or 20px */

  display: flex;
  align-items: center;

  /* Black */

  color: #222222 !important;


  /* Inside auto layout */

  flex: none;
  order: 0;
  flex-grow: 0;
  width: 217px !important;
}
.dropdown-item:first-of-type{
  margin-top: 0px;
}
.dropdown-item{
  margin-top: 11px;
}
.p13-19px{
  padding: 13px 19px !important;
}
.dropdown-item:hover{
  color: #3C6EBD !important;
}
</style>
