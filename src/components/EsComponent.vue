<template>
  <div
    class="dialog"
    v-if="flag"
  >
    <div class="content">

      <head>
        {{
          title
        }}
      </head>
      <div>
        原始内容
      </div>
      <slot></slot>
      <div class="foot">
        <button @click="ok">确认</button>
        <button @click="cancel">取消</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['flag', 'title'],
  data() {
    return {};
  },
  methods: {
    ok() {
      // eslint-disable-next-line no-alert
      alert(23);
      if (this.title === 1) {
        // eslint-disable-next-line no-console
        console.log('gg');
      }
      this.$emit('update:flag', false);
    },
    cancel() {
      this.$emit('update:flag', false);
    }
  }
};
</script>
t>

<style>
  .dialog {
    border: 1px solid salmon;
  }
  .foot {
    margin-top: 20px;
  }
</style>
