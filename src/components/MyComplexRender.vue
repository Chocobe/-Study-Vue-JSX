<script>
export default {
  data: () => ({
    title: "My Complex Render 입니다.",
    contents: "컨텐츠 입니다.",
    buttonName: "버튼명",
  }),

  render(h) {
    return h("div", [
      h("h1", {
        class: ["my-complex-title"],
        domProps: {
          innerHTML: this.title,
        },
      }),

      h("p", {
        class: ["my-complex-contents"],
        domProps: {
          innerHTML: this.contents,
        },
      }),

      h("button", {
        class: ["my-complex-button"],
        domProps: {
          innerHTML: this.buttonName,
        },
      }),
    ]);
  },
};
</script>

<style scoped>
.my-complex-title {
  color: #ff1493;
}

.my-complex-contents {
  color: #34eb7a;
}

.my-complex-button {
  color: #2b51b9;
  font-weight: 900;
}
</style>
