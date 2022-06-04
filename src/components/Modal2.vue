<template>
  <v-row justify="space-around">
    <v-col cols="auto">
      <v-dialog transition="dialog-top-transition" max-width="600">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="primary" v-bind="attrs" v-on="on">{{ openText }}</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar color="primary" dark>2회 대회 요강</v-toolbar>
            <v-card-text>
              <div class="text-h6 pa-12">
                <!-- 참고사항<br /> -->
                <ul style="font-size:14px; margin-top:20px; padding-left:0">
                  <li
                    v-for="(item, i) in contents"
                    :key="i"
                    style="line-height:20px; margin-bottom:10px"
                    v-html="item.text"
                  ></li>
                </ul>
              </div>
            </v-card-text>
            <v-card-actions class="justify-end">
              <v-btn text @click="dialog.value = false">{{ closeText }}</v-btn>
            </v-card-actions>
          </v-card>
        </template>
      </v-dialog>
    </v-col>
  </v-row>
</template>

<script>
export default {
  props: ["openText", "closeText"],

  data: () => ({
    contents: [
      {
        text: "참가종목 : 남자복식, 여자복식, 혼합복식, 남자단식",
      },
      {
        text:
          "참가비 : 참가 종목당 15,000원 (계좌 : <span style='color:green'>농협</span> <span style='color:#1976d2; text-decoration:underline'>146-02-120216</span> [윤경기])",
      },
      {
        text: "시상내역 : 우승/준우승팀 상품 지급",
      },
      {
        text:
          "경기방법<br/>- 16강 ~ 결승 : 6/25(토) ~ 6/26(일) (송도글로벌캠퍼스테니스장)<br/>- 1세트 매치 / 노-에드 / 게임스코어 5:5 타이브레이크 7점 적용<br/>- 코트 체인지 : 상대팀과 게임 스코어 합이 홀수 일때 변경<br/>- 파트너 교체는 첫 경기 시작 전에만 가능하며 승리팀이 다음 경기 출전 불가시 이전 경기에서 패한 팀이 출전",
      },
      {
        text:
          "기타사항<br/>- 참가비는 6/10(금)까지 입금 요청<br/>- 참가선수 전원 기념품 지급",
      },
    ],
  }),
};
</script>
