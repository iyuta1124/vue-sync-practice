<template>
  <v-dialog
    :value="isModalOpen"
    @click:outside="$emit('update:isModalOpen', false)"
  >
    <v-card>
      <v-card-text>
        <v-text-field
          @input="$emit('input', $event || false)"
          label="検索キーワード"
          :value="keyword"
        />
        <v-text-field
          @input="$emit('update:excludeKeyword', $event || '')"
          label="除外キーワード"
        />
        <v-checkbox
          label="大文字小文字を区別する"
          :value="considerCase"
          @change="$emit('update:considerCase', $event || false)"
        />
      </v-card-text>
      <v-card-actions>
        <v-btn @click="$emit('update:isModalOpen', false)">OK</v-btn>
      </v-card-actions>
    </v-card>
  </v-dialog>
</template>

<script>
export default {
  name: "SearchModal",
  props: {
    isModalOpen: { type: Boolean, default: false },
    considerCase: { type: Boolean, default: false },
    keyword: { type: String, default: "" },
    excludeKeyword: { type: String, default: "" },
  },
};
</script>
