<template>
  <div>
    <v-card class="mx-auto" max-width="300" tile style="margin-bottom:20px">
      <v-list rounded>
        <v-subheader
          ><p>참가자 명단(50)</p>
          <v-spacer></v-spacer>
          <p>구력</p></v-subheader
        >
        <v-list-item-group v-model="selectedItem" color="primary">
          <v-list-item v-for="(item, i) in items" :key="i">
            <v-list-item-icon>
              <v-icon v-text="item.icon" :color="item.color"></v-icon>
            </v-list-item-icon>
            <v-list-item-content>
              <v-list-item-title v-text="item.text"></v-list-item-title>
            </v-list-item-content>
            <v-list-item-content>
              <v-list-item-title
                v-text="item.career"
                style="text-align:end"
              ></v-list-item-title>
            </v-list-item-content>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-card>
    <p
      style="text-align:center; margin-bottom:56px; font-size:12px; color:#757575"
    >
      (오픈톡 기준)
    </p>
  </div>
</template>

<script>
export default {
  components: {},

  data: () => ({
    selectedItem: 0,
    items: [
      {
        text: "상효씨",
        icon: "mdi-account",
        color: "blue",
        career: "2년6개월",
      },
      { text: "정현", icon: "mdi-account", color: "blue", career: "2년" },
      { text: "김기승", icon: "mdi-account", color: "blue", career: "2년" },
      { text: "신성혜", icon: "mdi-account", color: "pink", career: "2년" },
      { text: "이용희", icon: "mdi-account", color: "blue", career: "2년" },
      {
        text: "김신우",
        icon: "mdi-account",
        color: "blue",
        career: "1년6개월",
      },
      {
        text: "권기현",
        icon: "mdi-account",
        color: "blue",
        career: "1년3개월",
      },
      {
        text: "박동규",
        icon: "mdi-account",
        color: "blue",
        career: "1년3개월",
      },
      {
        text: "김태정",
        icon: "mdi-account",
        color: "pink",
        career: "1년2개월",
      },
      { text: "엘라토스", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "노박", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "김동환", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "페더러워", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "안현욱", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "오과장", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "종말이", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "김종석", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "김두섭", icon: "mdi-account", color: "blue", career: "1년" },
      { text: "쫑", icon: "mdi-account", color: "blue", career: "10개월" },
      { text: "김연지", icon: "mdi-account", color: "pink", career: "10개월" },
      { text: "이재성", icon: "mdi-account", color: "blue", career: "10개월" },
      { text: "최지원", icon: "mdi-account", color: "blue", career: "10개월" },
      { text: "노정현", icon: "mdi-account", color: "blue", career: "9개월" },
      { text: "임호혁", icon: "mdi-account", color: "blue", career: "8개월" },
      { text: "김라한", icon: "mdi-account", color: "blue", career: "8개월" },
      { text: "이윤상", icon: "mdi-account", color: "blue", career: "8개월" },
      { text: "배수현", icon: "mdi-account", color: "pink", career: "8개월" },
      { text: "민경숙", icon: "mdi-account", color: "pink", career: "8개월" },
      { text: "국민호", icon: "mdi-account", color: "blue", career: "8개월" },
      { text: "최강현", icon: "mdi-account", color: "blue", career: "7개월" },
      { text: "박진영", icon: "mdi-account", color: "blue", career: "7개월" },
      { text: "김정현", icon: "mdi-account", color: "blue", career: "6개월" },
      { text: "김초희", icon: "mdi-account", color: "pink", career: "6개월" },
      { text: "조수현", icon: "mdi-account", color: "blue", career: "5개월" },
      { text: "최범석", icon: "mdi-account", color: "blue", career: "5개월" },
      { text: "오정석", icon: "mdi-account", color: "blue", career: "5개월" },
      { text: "장성현", icon: "mdi-account", color: "blue", career: "5개월" },
      { text: "송은정", icon: "mdi-account", color: "pink", career: "5개월" },
      { text: "꾹", icon: "mdi-account", color: "blue", career: "5개월" },
      { text: "향훈", icon: "mdi-account", color: "blue", career: "4개월" },
      { text: "서영득", icon: "mdi-account", color: "blue", career: "4개월" },
      { text: "박대범", icon: "mdi-account", color: "blue", career: "4개월" },
      { text: "이수민", icon: "mdi-account", color: "pink", career: "3개월" },
      { text: "은미", icon: "mdi-account", color: "pink", career: "3개월" },
      { text: "이재현", icon: "mdi-account", color: "blue", career: "3개월" },
      { text: "나계환", icon: "mdi-account", color: "blue", career: "3개월" },
      { text: "정광길", icon: "mdi-account", color: "blue", career: "5회" },
      {
        text: "지혜씨",
        icon: "mdi-account",
        color: "pink",
        career: "정보없음",
      },
      {
        text: "이창주",
        icon: "mdi-account",
        color: "blue",
        career: "정보없음",
      },
      {
        text: "김연수",
        icon: "mdi-account",
        color: "pink",
        career: "정보없음",
      },
    ],
  }),
};
</script>
