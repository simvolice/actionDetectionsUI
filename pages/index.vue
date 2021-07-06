<template>
  <v-container>
    <v-row>
      <v-col>
        <v-card>
          <v-card-title>
            Мои камеры
            <v-spacer></v-spacer>
            <v-text-field
              v-model="search"
              append-icon="mdi-magnify"
              label="Поиск"
              single-line
              hide-details
            ></v-text-field>
          </v-card-title>
          <v-data-table
            :headers="headers"
            :items="camerasArr"
            :search="search"
          ></v-data-table>
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
        { text: 'Состояние камеры', value: 'state' },
        { text: 'Адрес', value: 'address' },
        { text: 'Дата подключения к системе', value: 'dateCreated' },
        { text: 'Комментарий', value: 'comment' },
      ],
      camerasArr: [
        {
          name: 'Камера 1, Подъезд №1',
          state: 'Работает',
          address: 'ул. 23-15, 9/1, ЖК "Миллениум Парк"',
          dateCreated: "25.05.2021",
          comment: 'Камера установлена у входной группы дома',
        },
        {
          name: 'Камера 2, Подъезд №1',
          state: 'Работает',
          address: 'ул. 23-15, 9/1, ЖК "Миллениум Парк"',
          dateCreated: "05.06.2021",
          comment: 'Камера установлена в лифте',
        },
      ],
    }
  },
}
</script>
