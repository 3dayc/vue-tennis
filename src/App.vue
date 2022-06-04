<template>
  <v-app style="over-flow:hidden">
    <v-app-bar app color="black" dark>
      <div class="d-flex align-center">
        <h2 style="line-height:24px; font-size:20px">Tennis Championship</h2>
      </div>

      <v-spacer></v-spacer>

      <v-btn :href="link.kakao" target="_blank" text style="padding:0">
        <span class="mr-2">KAKAO TALK</span>
        <v-icon>{{ icons.mdiShareVariant }}</v-icon>
      </v-btn>
    </v-app-bar>

    <v-card style="padding-top:64px; background-color:#1976d2; border-radius:0">
      <v-tabs v-model="tab" background-color="primary" dark>
        <v-tab v-for="item in items" :key="item.num">
          {{ item.tab }}
        </v-tab>
      </v-tabs>

      <v-tabs-items v-model="tab">
        <v-tab-item v-for="item in items" :key="item.num">
          <v-card flat>
            <v-main v-if="item.num === '01'" style="padding-top:36px">
              <Progress :sum="sum" />
              <Modal openText="1회 대회 요강" closeText="close" />
              <!-- <div class="text-center" style="margin-top:20px;">
                <v-bottom-sheet v-model="sheet" persistent>
                  <template v-slot:activator="{ on, attrs }">
                    <v-btn color="pink" dark v-bind="attrs" v-on="on">
                      4강/결승 일정
                    </v-btn>
                  </template>
                  <v-sheet class="text-center" height="100%">
                    <v-btn
                      class="mt-6"
                      text
                      color="error"
                      @click="sheet = !sheet"
                    >
                      close
                    </v-btn>
                    <div class="py-3">
                      <img
                        src="./assets/tennis_03.png"
                        style="max-width:374px; height:230px"
                      />
                    </div>
                  </v-sheet>
                </v-bottom-sheet>
              </div> -->
              <Card />
              <List />
            </v-main>
            <v-main v-if="item.num === '02'" style="padding-top:36px">
              <Progress :sum="sum2" />
              <Modal2 openText="2회 대회 요강" closeText="close" />
              <div style="height:100vh; text-align:center; margin-top:36px">
                <span style="display:block; font-weight:bold; margin-bottom:4px"
                  >6/25(토) ~ 6/26(일) - 1세트 매치 / 노-에드</span
                >
                <img src="./assets/tennis_04.png" style="max-width:374px" />
              </div>
            </v-main>
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-card>
  </v-app>
</template>

<script>
import { mdiShareVariant } from "@mdi/js";
import Progress from "./components/Progress";
import Modal from "./components/Modal";
import Modal2 from "./components/Modal2";
import Card from "./components/Card";
import List from "./components/List";

export default {
  name: "App",

  components: {
    Card,
    List,
    Modal,
    Modal2,
    Progress,
  },

  data: () => ({
    sheet: false,
    icons: {
      mdiShareVariant,
    },
    link: {
      kakao: "https://open.kakao.com/o/gUYUMBod",
    },
    tab: null,
    items: [
      { tab: "1회", num: "01" },
      { tab: "2회", num: "02" },
    ],
  }),

  computed: {
    sum() {
      // let total_km = 0;
      // for (let i = 0; i < this.items.length; i++) {
      //   total_km = total_km + this.items[i].km;
      // }
      // return total_km.toFixed(2);
      return 100;
    },
    sum2() {
      // let total_km = 0;
      // for (let i = 0; i < this.items.length; i++) {
      //   total_km = total_km + this.items[i].km;
      // }
      // return total_km.toFixed(2);
      return 0;
    },
  },
};
</script>

<style>
body {
  overflow: hidden;
}
</style>
