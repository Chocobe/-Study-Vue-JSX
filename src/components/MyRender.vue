<script>
export default {
  data: () => ({
    msg: "My Render 입니다.",
  }),

  render(h) {
    return h("h1", {
      class: ["my-render-title"],

      domProps: {
        innerHTML: this.msg,
      },
    });
  },
};
</script>

<style scoped>
.my-render-title {
  color: #03a9f4;
}
</style>
