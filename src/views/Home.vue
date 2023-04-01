<template>
  <v-app id="inspire">
    <v-app-bar
      class="px-3"
      color="white"
      flat
      density="compact"
    >
      <v-toolbar-title>Title by Index.vue</v-toolbar-title>
      <v-tabs
        centered
        color="grey-darken-2"
        v-model="tab"
      >
        <v-tab
          v-for="link in links"
          :key="link.id"
          :value="link.id"
        >
          {{ link.title }}
        </v-tab>
      </v-tabs>
      <v-spacer></v-spacer>
    </v-app-bar>

    <v-main class="bg-grey-lighten-3">
      <v-window v-model="tab">
        <!-- transition 画面遷移時のアニメーションを変更 -->
        <v-window-item
          v-for="link in links"
          :key="link.id"
          :value="link.id"
          transition="fade-transition"
        >
          <v-container>
            <!-- justify contentsを中央揃えに -->
            <v-row
                justify="center"
              >
                <v-col
                  cols="12"
                  sm="12"
                >
                  <v-sheet
                    min-height="70vh"
                    rounded="lg"
                    class="sheet"
                    id="scrolling-techniques-3"
                  >
                  <v-card flat>
                    <v-card-text>{{ link.title }}</v-card-text>
                  </v-card>
                  </v-sheet>
                </v-col>
              </v-row>
          </v-container>
        </v-window-item>
      </v-window>
    </v-main>
    <v-footer class="bg-grey-lighten-1">
      <v-row justify="center" no-gutters>
        <v-btn
          v-for="link in links"
          :key="link.id"
          color="white"
          variant="text"
          class="mx-2"
          rounded="xl"
        >
          {{ link.title }}
        </v-btn>
        <v-col class="text-center mt-4" cols="12">
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>


  <script>
    export default {
      data: () => ({
        tab: null,
        links: [
          {id: 1, title: 'ホーム'},
          {id: 2, title: '事業内容'},
          {id: 3, title: '実績紹介'},
          {id: 4, title: '会社概要'},
          {id: 5, title: 'お問い合わせ'}
        ],
      }),
    }
  </script>

<style>
  .sheet{
    padding: 100px;
  }
</style>