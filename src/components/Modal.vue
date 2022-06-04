<template>
  <v-row justify="space-around">
    <v-col cols="auto">
      <v-dialog transition="dialog-top-transition" max-width="600">
        <template v-slot:activator="{ on, attrs }">
          <v-btn color="primary" v-bind="attrs" v-on="on">{{ openText }}</v-btn>
        </template>
        <template v-slot:default="dialog">
          <v-card>
            <v-toolbar color="primary" dark>1회 대회 요강</v-toolbar>
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
        text: "참가자격 : 초테모임 가입자",
      },
      {
        text: "참가레벨 : 4개 레벨 (테린이 상/중/하, 왕초보)",
      },
      {
        text: "참가종목 : 남여 구분 없는 복식 경기",
      },
      {
        text:
          "참가비 : 1만원 (계좌 : <span style='color:green'>농협</span> <span style='color:#1976d2; text-decoration:underline'>146-02-120216</span> [윤경기])",
      },
      {
        text: "시상내역 : 1,2 그룹 우승팀 각 10만원",
      },
      {
        text:
          "경기방법<br/>- 16강 ~ 8강 : 상대팀과 경기 일정 협의 후 자율 경기<br/>- 4강 ~ 결승 : 5/28(토) 집합경기 (송도달빛축제공원보조경기장)<br/>- 3세트2선승제 / 노-에드 / 매세트 5대5일 때 타이 7점 적용 / 세트스코어 1대1 동점일 때 3세트는 매치타이 7점 결정<br/>- 코트 체인지 : 상대팀과 게임 스코어 합이 홀수 일때 변경<br/>- 복식게임 핸디 부여 : 혼복 vs 남복 경기시 15 : 0 부터 매 게임 시작<br/>- 파트너 교체는 첫 경기 시작 전에만 가능하며 승리팀이 다음 경기 출전 불가시 이전 경기에서 패한 팀이 출전",
      },
      {
        text: "기타사항<br/>- 참가비는 첫 1경기 종료 이후 입금",
      },
    ],
  }),
};
</script>
