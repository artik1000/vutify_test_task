<template>
  <v-container class="py-0 px-60px" fluid>
    <v-row>
      <v-col :cols="9">
        <h1 class="font-weight-regular">{{ this.$route.name }}</h1>
        <div class="search-module">
          <v-icon dark big>mdi-magnify</v-icon>
          <v-input placeholder="Введите данные"/>
          <v-btn class="btn-gray rounded-pill button elevation-0">Найти</v-btn>
        </div>
        <div class="d-flex flex-column accordion-list">
          <div
            class="d-flex flex-column"
            v-for="item in items"
            :key="item.id"
            :tag="item.title"
          >
            <h2 class="accordion-title">{{item.title}}</h2>
            <v-expansion-panels class="shadow-none">
              <v-expansion-panel
                class="shadow-none"
                v-for="list in item.children"
                :key="list.id"
                :title="list.title"
                :text="list.text"
              >
              </v-expansion-panel>
            </v-expansion-panels>
          </div>
        </div>
      </v-col>
      <v-col :cols="3" class="d-flex flex-column justify-space-between">
        <div class="d-flex flex-column">
          <v-card class="d-flex flex-column">
            <h3>Регламенты и документы</h3>
            <v-btn class="bg-transparent d-flex flex-row elevation-0 mt-15px gap-6px justify-start pa-0">
            <span class="material-icons" style="color: #FF4957">
              picture_as_pdf
            </span>
              <p class="download-link__text d-block my-auto">Регламент Электронной <br> Площадки ЦДТ.pdf</p>
            </v-btn>
            <v-btn class="bg-transparent d-flex flex-row elevation-0 mt-15px gap-6px justify-start pa-0">
            <span class="material-icons" style="color: #3C6EBD">
              article
            </span>
              <p class="download-link__text d-block my-auto">Архив.doc</p>
            </v-btn>
          </v-card>
          <div class="d-flex flex-column gap-15px mt-40px">
            <h2
              class="guide-list"
              v-for="item in items"
              :key="item.id"
              @click="toAccordionElement(item.title)"
            >
              {{ item.title }}
            </h2>
          </div>
        </div>
        <v-btn class="btn-gray rounded-pill button elevation-0 align-self-end bottom-72px">
          <span class="icon-16px">
            chat_bubble_outline
          </span>
          Задать вопрос
        </v-btn>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import Accordion from '@/components/Accordion.vue'
export default {
  data () {
    return {
      items: [
        {
          id: 0,
          title: 'Регистрация на ЦДТ',
          children: [
            {
              id: 0,
              title: 'Регистрация на ЦДТ для Организатора торгов или Арбитражного управляющего',
              text: 'Для прохождения регистрации на секции «Банкротные торги», рекомендуем Вам ознакомиться с разделом «Порядок регистрации» и выполнить все шаги: https://bankrot.cdtrf.ru//public/i/order.aspx\n' +
                'Дополнительные инструкции по работе с данной секцией, можно просмотреть в разделе «Инструкции» : https://bankrot.cdtrf.ru//public/i/instructions.aspx\n' +
                'При регистрации организаторов торгов необходимо заключить договор на оказание услуг площадки, а также соглашение о тарифах. Если договор еще не подписан, выбираете пункт «обязуюсь заключить договор позднее».'
            },
            {
              id: 1,
              title: 'Регистрация на ЦДТ для Участника торгов',
              text: ``
            },
            {
              id: 2,
              title: 'Какие нужны Юридическому лицу (ЮЛ) документы для регистрации на ЭТП ЦДТ',
              text: ''
            }
          ]
        },
        {
          id: 1,
          title: 'Проведение торгов',
          children: [
            {
              id: 0,
              title: 'Нет доступа в личном кабинете для поиска торгов и подачи заявки',
              text: ''
            },
            {
              id: 1,
              title: 'Публикация протоколов организатором торгов (ОТ) и/или арбитражным управляющим (АУ)',
              text: ''
            },
            {
              id: 2,
              title: 'По какому времени проводятся торги на ЦДТ',
              text: ''
            },
            {
              id: 3,
              title: 'Как найти этот лот',
              text: ''
            },
          ]
        },
        {
          id: 2,
          title: 'Электронная подпись (ЭП)',
          children: [
            {
              id: 0,
              title: 'Как получить электронную подпись (ЭП)',
              text: ''
            },
            {
              id: 1,
              title: 'Загрузить новую ЭЦП в личный кабинет пользователя',
              text: ''
            },
            {
              id: 2,
              title: 'Продлили срок ЭП, при замене в личном кабинете (ЛК) ошибка «не совпадают ФИО пользователя»',
              text: ''
            }
          ]
        },
        {
          id: 3,
          title: 'Задаток',
          children: [
            {
              id: 0,
              title: 'Как Арбитражному управляющему вернуть задаток победителя',
              text: ''
            },
            {
              id: 1,
              title: 'Что сделать Участнику торгов для возврата задатка',
              text: ''
            }
          ]
        },
        {
          id: 4,
          title: 'Загрузка документов на ЭТП ЦДТ',
          children: [
            {
              id: 0,
              title: 'При загрузке документов, документ не сохраняется',
              text: ''
            },
            {
              id: 1,
              title: 'Требуется загрузить пакет документов',
              text: ''
            }
          ]
        },
      ],
      toAccordionElement(title){
        let el = document.querySelector(`[tag="${title}"]`)
        el.scrollIntoView({behavior: "smooth"})
      }
    }
  }
}
</script>
<style>
.v-card{
  box-shadow: 0px 0px 35px rgba(0, 0, 0, 0.15) !important;
  border-radius: 8px !important;
  padding: 24px 24px !important;
}
.py-15px{
  padding: 15px 0px !important;
}
.download-link__text{
  font-family: 'Arimo' !important;
  font-style: normal !important;
  font-weight: 700 !important;
  font-size: 1.111vw !important;
  line-height: 140% !important;
  color: #3C6EBD !important;
  text-align: left;
  height: fit-content;
  text-transform: none !important;
}
.gap-6px{
  gap: 6px !important;
}
.v-btn__content{
  flex-direction: row;
  gap: 6px;
}
.mt-15px{
  margin-top: 15px;
}
.gap-15px{
  gap: 15px;
}
.guide-list{
  font-family: 'Arimo' !important;
  font-style: normal !important;
  font-weight: 700 !important;
  font-size: 1.111vw !important;
  line-height: 120% !important;
  color: #3C6EBD !important;
}
.mt-40px{
  margin-top: 40px !important;
}
.search-module{
  display: flex;
  flex-direction: row;
  align-items: center;
  padding: 4px 4px 4px 14px;
  gap: 24px;

  width: 424px;
  height: 46px;

  /* White */

  background: #FFFFFF;
  /* Light gray */

  border: 1px solid #E9E9E9;
  border-radius: 40px;
  margin-top: 60px;
  margin-bottom: 60px;
}
.accordion-list{
  margin-top: 60px !important;
  margin-bottom: 136px !important;
  gap: 60px !important;
}
.accordion-title{
  font-family: 'Arimo';
  font-style: normal;
  font-weight: 700;
  font-size: 24px;
  line-height: 120%;
  margin-bottom: 41px;
  top:0;
  left: 0;
}
.shadow-none{

}
.v-expansion-panel__shadow{
  box-shadow: none !important;
}
.v-expansion-panels{
  border-top: 1px solid #E9E9E9;
  border-bottom: 1px solid #E9E9E9;
}
.v-expansion-panel-title{
  font-family: 'Arimo' !important;
  font-style: normal !important;
  font-weight: 400 !important;
  font-size: 18px !important;
  line-height: 24px !important;
  /* identical to box height, or 133% */

  display: flex !important;
  text-align: left !important;

  /* Black */

  color: #222222;
  padding: 28px 24px !important;
}
.v-expansion-panel-title--active > .v-expansion-panel-title__overlay, .v-expansion-panel-title[aria-haspopup=menu][aria-expanded=true] > .v-expansion-panel-title__overlay {
  opacity: 0 !important;
}
.v-expansion-panel-title--active{
  color: #3C6EBD;
}
.v-expansion-panel-title__icon{
  color: black !important;
}
.v-btn:hover{
  color: transparent;
}
.v-expansion-panel--active{
  border-top: 1px solid #E9E9E9;
  border-bottom: 1px solid #E9E9E9;
}
.v-btn{
  text-transform: none !important;
}
.icon-16px{
  /* v-icon-left */


  width: 16px;
  height: 16px;

  /* v-icon/small */

  font-family: 'Material Icons';
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 100%;
  /* identical to box height, or 16px */

  display: flex;
  align-items: center;
  text-align: center;

  /* Black */

  color: #222222;
}
.bottom-72px{
  margin-bottom: 72px;
}
</style>
