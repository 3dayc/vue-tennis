<template>
  <div>
    <v-card
      :loading="loading"
      class="mx-auto"
      max-width="374"
      style="margin-bottom:56px; margin-top:36px"
    >
      <template slot="progress">
        <v-progress-linear
          color="deep-purple"
          height="10"
          indeterminate
        ></v-progress-linear>
      </template>

      <v-img src="../assets/tennis_01.png"></v-img>

      <v-card-title>1그룹 (테린이 상 + 중)</v-card-title>

      <v-card-text>
        <v-row align="center" class="mx-0">
          <v-rating
            :value="3"
            color="amber"
            dense
            half-increments
            readonly
            size="14"
          ></v-rating>

          <div class="grey--text ms-4"></div>
        </v-row>

        <div class="my-4 text-subtitle-1">
          $ • 제1회 초테모임 챔피언쉽 1그룹 경기
        </div>

        <div>우승 : 김동환 / 권기현<br />준우승 : 엘라토스 / 정현</div>
      </v-card-text>

      <v-divider class="mx-4"></v-divider>

      <v-card-title>THE FINAL PLACE</v-card-title>

      <v-card-text>
        <v-chip-group
          v-model="selection"
          active-class="deep-purple accent-4 white--text"
          column
        >
          <v-chip>송도달빛축제공원</v-chip>

          <v-chip>열우물</v-chip>

          <v-chip>가좌시립</v-chip>

          <v-chip>청라솔레아스</v-chip>

          <v-chip>송도새아침</v-chip>

          <v-chip>환경공단송도지소</v-chip>
        </v-chip-group>
      </v-card-text>

      <v-card-actions>
        <v-btn color="deep-purple lighten-2" text @click="reserve">
          Refresh
        </v-btn>
      </v-card-actions>
    </v-card>
    <v-card :loading="loading" class="mx-auto my-14" max-width="374">
      <template slot="progress">
        <v-progress-linear
          color="deep-purple"
          height="10"
          indeterminate
        ></v-progress-linear>
      </template>

      <v-img src="../assets/tennis_02.png"></v-img>

      <v-card-title>2그룹 (테린이 하 + 왕초보)</v-card-title>

      <v-card-text>
        <v-row align="center" class="mx-0">
          <v-rating
            :value="2"
            color="amber"
            dense
            half-increments
            readonly
            size="14"
          ></v-rating>

          <div class="grey--text ms-4"></div>
        </v-row>

        <div class="my-4 text-subtitle-1">
          $ • 제1회 초테모임 챔피언쉽 2그룹 경기
        </div>

        <div>우승 : 박대범 / 노정현<br />준우승 : 향훈 / 박진영</div>
      </v-card-text>

      <v-divider class="mx-4"></v-divider>

      <v-card-title>THE FINAL PLACE</v-card-title>

      <v-card-text>
        <v-chip-group
          v-model="selection2"
          active-class="deep-purple accent-4 white--text"
          column
        >
          <v-chip>송도달빛축제공원</v-chip>

          <v-chip>열우물</v-chip>

          <v-chip>가좌시립</v-chip>

          <v-chip>청라솔레아스</v-chip>

          <v-chip>송도새아침</v-chip>

          <v-chip>환경공단송도지소</v-chip>
        </v-chip-group>
      </v-card-text>

      <v-card-actions>
        <v-btn color="deep-purple lighten-2" text @click="reserve">
          Refresh
        </v-btn>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  data: () => ({
    loading: false,
    selection: 0,
    selection2: 0,
  }),

  methods: {
    reserve() {
      this.loading = true;

      setTimeout(() => (this.loading = false), 2000);
    },
  },
};
</script>
