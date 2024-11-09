<script setup>
// import { RouterLink, RouterView } from "vue-router";
// import HelloWorld from "./components/HelloWorld.vue";
</script>

<template>
  <v-app id="inspire">
    <v-content>
      <v-container fluid fill-height>
        <v-layout justify-center align-center>
          <v-flex text-xs-center>
            <v-text-field
              v-model="lastname"
              :counter="10"
              :rules="nameRules"
              label="Введите ссылки на котировочные сессии"
              required
            ></v-text-field>
            Характеристики для проверки
            <v-checkbox label="Характеристика"></v-checkbox>
            <v-checkbox label="Характеристика"></v-checkbox>
            <v-checkbox label="Характеристика"></v-checkbox>
            <v-checkbox label="Характеристика"></v-checkbox>
            <v-checkbox label="Характеристика"></v-checkbox>

            <span class="pa-4 text-center">
              <v-btn
                @click="dialog1 = true"
                class="text-none font-weight-regular"
                prepend-icon="mdi-account"
                text="Добавить новые характеристики"
                variant="tonal"
              ></v-btn>
              <v-dialog v-model="dialog1" width="auto">
                <v-card
                  prepend-icon="mdi-account"
                  title="Добавление характеристики"
                >
                  <v-card-text>
                    <v-row dense>
                      <v-col cols="12" md="4" sm="6">
                        <v-text-field
                          label="Введите характеристику"
                          required
                        ></v-text-field>
                      </v-col>

                      <v-col cols="12" md="4" sm="6"></v-col>
                    </v-row>
                  </v-card-text>
                  <v-btn @click="dialog1 = false"
                    >Добавить характеристику</v-btn
                  >
                </v-card>
              </v-dialog>
            </span>

            <div class="text-center pa-4">
              <v-btn @click="dialog = true"> Open Dialog </v-btn>

              <v-dialog v-model="dialog" width="auto">
                <v-card
                  max-width="400"
                  prepend-icon="mdi-update"
                  text="Your application will relaunch automatically after the update is complete."
                  title="Update in progress"
                >
                  <v-table density="compact">
                    <thead>
                      <tr>
                        <th class="text-left">Ссылка</th>
                        <th class="text-left">Итог</th>
                        <th class="text-left">Комментарий</th>
                      </tr>
                    </thead>
                    <tbody>
                      <tr v-for="item in desserts" :key="item.name">
                        <td>{{ item.name }}</td>
                        <td>{{ item.calories }}</td>
                        <td>{{ item.calories }}</td>
                      </tr>
                    </tbody>
                  </v-table>

                  <template v-slot:actions>
                    <v-btn
                      class="ms-auto"
                      text="Сбросить"
                      @click="dialog = false"
                    ></v-btn>
                  </template>
                </v-card>
              </v-dialog>
            </div>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>

    <v-footer color="indigo" app>
      <span class="white--text">&copy; Brain OverFlow</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      dialog: false,
      dialog1: false,
    };
  },
};
</script>

<style>
#clickable {
  cursor: pointer;
}
</style>
