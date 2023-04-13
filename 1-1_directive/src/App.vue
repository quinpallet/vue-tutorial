<script setup lang="ts">
import { ref, computed } from 'vue';

// テンプレート変数にバインドするデータを設定
const url = ref('https://vuejs.org/');

// 属性値のない属性のバインドを設定
const isButtonDisabled = ref(true);

// バインドする属性とその値をテンプレート変数として指定
const heightAttr = ref('height');
const heightValue = ref(200);

// 引数を指定しないでv-bindを使用する際に設定する属性
const imgAttributes = ref({
  src: '/assets/logo.svg',
  alt: 'Vueのロゴ',
  width: 75,
  height: 75
});

// スタイルのプロパティ値を設定
const msg = ref('こんにちはワールド');
const msgTextRed = ref('red');
const msgTextColor = ref('white');
const msgBgColor = ref('black');
const msgStyles = ref({
  color: 'white',
  backgroundColor: 'black'
});
const msgStyles2 = ref({
  fontSize: '24pt'
});
const msgStyles3 = ref({
  color: 'pink',
  fontSize: '24pt'
});
const textSize = computed((): string => {
  const size = Math.round(Math.random() * 25) + 10;
  return `${size}pt`;
});
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
      <!-- devコマンド：/src/assets/logo.svg -->
      <!-- buildコマンド：/public/assets/logo.svg -->
    </section>
    <section>
      <h3>複数の属性にまとめてバインド</h3>
      <p><img v-bind="imgAttributes"></p>
      <p><img v-bind="imgAttributes" title="ロゴdeath!"></p>
      <p><img v-bind="imgAttributes" alt="ロゴdeath!"></p>
    </section>
    <section>
      <h3>style属性へのバインド</h3>
      <p v-bind:style="{color: msgTextRed}">{{msg}}</p>
      <p v-bind:style="{color: 'pink'}">{{msg}}</p>
      <p v-bind:style="{fontSize: textSize}">{{msg}}</p>
      <p v-bind:style="{color: msgTextColor, backgroundColor: msgBgColor}">{{msg}}</p>
      <p v-bind:style="{color: msgTextColor, 'background-color': msgBgColor}">{{msg}}</p>
      <p v-bind:style="msgStyles">{{msg}}</p>
      <p v-bind:style="[msgStyles, msgStyles2]">{{msg}}</p>
      <p v-bind:style="[msgStyles, msgStyles3]">{{msg}}</p>
      <p v-bind:style="[msgStyles3, msgStyles]">{{msg}}</p>
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