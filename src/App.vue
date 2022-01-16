<template>
  <v-app>
    <v-content>
      <v-container>
        <search-modal
          v-model="keyword"
          :isModalOpen.sync="isModalOpen"
          :considerCase.sync="considerCase"
          :excludeKeyword.sync="excludeKeyword"
        />
        <v-btn @click="isModalOpen = true">検索モーダルを開く</v-btn>
        <p>検索キーワード:{{ keyword }}</p>
        <p>除外キーワード:{{ excludeKeyword }}</p>
        <p>大文字小文字を区別する:{{ considerCase }}</p>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import SearchModal from "@/components/SearchModal";

export default {
  components: { SearchModal },
  data: () => ({
    keyword: "",
    isModalOpen: false,
    considerCase: false,
    excludeKeyword: "",
  }),
};
</script>
