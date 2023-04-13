<script setup lang="ts">
import { ref } from 'vue';

// テンプレート変数にバインドするデータを設定
const url = ref('https://vuejs.org/');

// 属性値のない属性のバインドを設定
const isButtonDisabled = ref(true);

// バインドする属性とその値をテンプレート変数として指定
const heightAttr = ref('height');
const heightValue = ref(200);
</script>

<template>
  <div>
    <section>
      <h3>属性にデータをバインドする v-bind</h3>
      <p><a v-bind:href="url" target="_blank">Vue.jsのサイト</a></p>
      <p><a v-bind:href="url + 'guide/introduction.html'" target="_blank">Vue.jsガイドのページ</a></p>
    </section>
    <section>
      <h3>属性値のない属性へのバインド</h3>
      <p><button type="button" v-bind:disabled="isButtonDisabled">ボタン(無効化)</button></p>
    </section>
    <section>
      <h3>バインドする属性をテンプレート変数として指定</h3>
      <p><img src="/assets/logo.svg" alt="VueLogo" v-bind:[heightAttr]="heightValue"></p>
    </section>
  </div>
</template>

<style lang="scss">
section {
  &:not(:last-child) {
    margin-bottom: 1em;
  }
  h3 {
    font-weight: bold;
  }
}
</style>