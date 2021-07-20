<template>
  <v-container>
    <v-row>
      <v-col>
        <v-card>
          <v-card-title>
            Аналитика правонарушений
            <v-spacer></v-spacer>
          </v-card-title>
          <div id="container"></div>
          <v-data-table
            :headers="headers"
            :items="camerasArr"
          >


            <template #[`item.urlVideo`]="{ item }">
              <a :href='item.urlVideo' target='_blank'>Видео</a>
            </template>
          </v-data-table>
        </v-card>
      </v-col>

    </v-row>

  </v-container>

</template>
<script>

export default {
  data () {
    return {
      search: '',
      headers: [
        { text: 'Имя камеры', value: 'name' },
        { text: 'Адрес', value: 'address' },
        { text: 'Дата обнаружения правонарушения', value: 'dateCreated' },
        { text: 'Вид правонарушения', value: 'typeViolation' },
        { text: 'Ссылка на видео', value: 'urlVideo' },
      ],
      camerasArr: [
        {
          name: 'Камера 1, Подъезд №1',
          address: 'ул. 23-15, 9/1, ЖК "Миллениум Парк"',
          dateCreated: "25.05.2021",
          typeViolation: 'Курение в общественно месте',
          urlVideo: 'videos/smoke1.gif',
        },
        {
          name: 'Камера 1, Подъезд №1',
          address: 'ул. 23-15, 9/1, ЖК "Миллениум Парк"',
          dateCreated: "25.05.2021",
          typeViolation: 'Курение в общественно месте',
          urlVideo: 'videos/smoke888.gif',
        },

        {
          name: 'Камера 1, Подъезд №1',
          address: 'ул. 23-15, 9/1, ЖК "Миллениум Парк"',
          dateCreated: "25.05.2021",
          typeViolation: 'Курение в общественно месте',
          urlVideo: 'videos/smoke3333555.gif',
        },

      ],
    }
  },
  mounted() {

    // eslint-disable-next-line no-undef
    Highcharts.setOptions({
      lang: {
        loading: 'Загрузка...',
        months: ['Январь', 'Февраль', 'Март', 'Апрель', 'Май', 'Июнь', 'Июль', 'Август', 'Сентябрь', 'Октябрь', 'Ноябрь', 'Декабрь'],
        weekdays: ['Воскресенье', 'Понедельник', 'Вторник', 'Среда', 'Четверг', 'Пятница', 'Суббота'],
        shortMonths: ['Янв', 'Фев', 'Март', 'Апр', 'Май', 'Июнь', 'Июль', 'Авг', 'Сент', 'Окт', 'Нояб', 'Дек'],
        exportButtonTitle: "Экспорт",
        printButtonTitle: "Печать",
        rangeSelectorFrom: "С",
        rangeSelectorTo: "По",
        rangeSelectorZoom: "Период",
        downloadPNG: 'Скачать PNG',
        downloadJPEG: 'Скачать JPEG',
        downloadPDF: 'Скачать PDF',
        downloadSVG: 'Скачать SVG',
        printChart: 'Напечатать график'
      }
    });

    // eslint-disable-next-line no-undef
    Highcharts.chart('container', {
      chart: {
        type: 'line'
      },

      title: {
        text: 'Курение в общественном месте за 2021 год.'
      },


      yAxis: {
        title: {
          text: 'Количество'
        }
      },

      xAxis: {
        type: 'datetime',

      },





      series: [{
        name: "Курение в общественном месте",
        data: [


          { "_id" : { "day" : 1, "month" : 4, "year" : 2021 }, "x" : new Date("2021-04-01T15:42:09.020+0000"), "y" : 5.0, "videoFile_idArr" : [ { "item" : { "$oid" : "6065e9d15b3bad8e7cb738ff" } }, { "item" : { "$oid" : "6065ef245b3bad8e7cb73917" } }, { "item" : { "$oid" : "606610a8c69a7cc8c0439851" } }, { "item" : { "$oid" : "606610aac69a7cc8c0439855" } }, { "item" : { "$oid" : "606610adc69a7cc8c0439859" } } ] },
          { "_id" : { "day" : 8, "month" : 4, "year" : 2021 }, "x" : new Date("2021-04-08T17:35:34.797+0000"), "y" : 1.0, "videoFile_idArr" : [ { "item" : { "$oid" : "606f3ee659ae2f7f45176002" } } ] },
          { "_id" : { "day" : 10, "month" : 4, "year" : 2021 }, "x" : new Date("2021-04-10T10:16:48.327+0000"), "y" : 5.0, "videoFile_idArr" : [ { "item" : { "$oid" : "60717b10110d31060e5766ef" } }, { "item" : { "$oid" : "60717b14110d31060e5766f9" } }, { "item" : { "$oid" : "60717b19110d31060e576701" } }, { "item" : { "$oid" : "60717b1d110d31060e576709" } }, { "item" : { "$oid" : "60717b21110d31060e576711" } } ] },
          { "_id" : { "day" : 17, "month" : 4, "year" : 2021 }, "x" : new Date("2021-04-17T13:57:49.849+0000"), "y" : 3.0, "videoFile_idArr" : [ { "item" : { "$oid" : "607ae95d3709b09718dab696" } }, { "item" : { "$oid" : "607ae9663709b09718dab69e" } }, { "item" : { "$oid" : "607ae96f3709b09718dab6a6" } } ] },


          { "_id" : { "day" : 1, "month" : 5, "year" : 2021 }, "x" : new Date("2021-05-01T07:22:28.261+0000"), "y" : 5.0, "videoFile_idArr" : [ { "item" : { "$oid" : "608d01b4ec4b2d921d9918d4" } }, { "item" : { "$oid" : "608d813fe1df42941da4571a" } }, { "item" : { "$oid" : "608d8148e1df42941da45723" } }, { "item" : { "$oid" : "608d8ce39eb6882e1c1adfaf" } }, { "item" : { "$oid" : "608d8cf39eb6882e1c1adfb5" } } ] },
          { "_id" : { "day" : 2, "month" : 5, "year" : 2021 }, "x" : new Date("2021-05-02T14:07:21.223+0000"), "y" : 1.0, "videoFile_idArr" : [ { "item" : { "$oid" : "608eb219bf3884362ddc3518" } } ] },
          { "_id" : { "day" : 3, "month" : 5, "year" : 2021 }, "x" : new Date("2021-05-03T08:51:04.723+0000"), "y" : 1.0, "videoFile_idArr" : [ { "item" : { "$oid" : "608fb978146b37f0cc4cc6d4" } } ] },
          { "_id" : { "day" : 7, "month" : 5, "year" : 2021 }, "x" : new Date("2021-05-07T10:24:30.209+0000"), "y" : 11.0, "videoFile_idArr" : [ { "item" : { "$oid" : "6095155e912634e5dbe48cb7" } }, { "item" : { "$oid" : "60951994249b6ca4ad561c8b" } }, { "item" : { "$oid" : "60951998249b6ca4ad561c92" } }, { "item" : { "$oid" : "609519a1249b6ca4ad561c99" } }, { "item" : { "$oid" : "609519f9249b6ca4ad561cc9" } }, { "item" : { "$oid" : "60951a4d249b6ca4ad561cf6" } }, { "item" : { "$oid" : "60951a60249b6ca4ad561cff" } }, { "item" : { "$oid" : "60951ae0249b6ca4ad561d0b" } }, { "item" : { "$oid" : "60951b47249b6ca4ad561d17" } }, { "item" : { "$oid" : "60951b53249b6ca4ad561d2b" } }, { "item" : { "$oid" : "60955a0ba8b45f00d6d1a010" } } ] },
          { "_id" : { "day" : 8, "month" : 5, "year" : 2021 }, "x" : new Date("2021-05-08T09:37:42.151+0000"), "y" : 6.0, "videoFile_idArr" : [ { "item" : { "$oid" : "60965be69a3ff917c9112512" } }, { "item" : { "$oid" : "60965bfd9a3ff917c9112526" } }, { "item" : { "$oid" : "60965c1a9a3ff917c9112542" } }, { "item" : { "$oid" : "60965c1e9a3ff917c9112545" } }, { "item" : { "$oid" : "60965cd29a3ff917c911258c" } }, { "item" : { "$oid" : "60965cf09a3ff917c91125c0" } } ] },

        ],
      }],
       /* tooltip: {
         useHTML: true,
         pointFormatter() {

          /!* console.log(this.series)
           console.log(this.series.userOptions.data[this.point.index]) *!/
           return `<img src="http://localhost:3000/video/smoke1.gif">`
         }
       }, */

    });

  }
}
</script>
