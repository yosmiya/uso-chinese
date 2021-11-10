<template>
  <div class="uso">
    <div class="uso__inputarea">
      <textarea class="uso__textarea-input" placeholder="私の名前は佐藤です"
        v-model="state.input" v-on:change="removeHiragana"></textarea>
    </div>
    <div class="uso__inputarea">
      <textarea class="uso__textarea-output" placeholder="私名前佐藤"
        v-model="state.output"></textarea>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue';

export default defineComponent({
  setup() {
    const state = reactive({
      input: '',
      output: '',
    });

    const removeHiragana = () => {
      state.output = state.input.replace(/[\u3042-\u3093]/g, '');
    };

    return {
      state,
      removeHiragana,
    };
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.uso {
  display: flex;
  justify-content: space-between;
  width: 100%;

  &__inputarea {
        flex-grow: 0;
    flex-shrink: 0;
    flex-basis: calc((100% - 40px)/2);

  }

  &__textarea-input {
    width: 100%;
        height: 500px;
  }

  &__textarea-output {
    width: 100%;
        height: 500px;
  }
}

</style>
