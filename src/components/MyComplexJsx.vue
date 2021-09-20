<script>
export default {
  data: () => ({
    title: "My Complex Jsx 입니다.",
    contents: "컨텐츠 입니다.",
    buttonName: "My버튼",
  }),

  render() {
    return (
      <div>
        <h1 class="my-complex-title">{this.title}</h1>
        <p class="my-complex-contents">{this.contents}</p>
        <button class="my-complex-button">{this.buttonName}</button>
      </div>
    );
  },
};
</script>

<style scoped>
.my-complex-title {
  color: #ff1493;
}

.my-complex-contents {
  color: #03a9f4;
}

.my-complex-button {
  color: #2b51b9;
  font-weight: 900;
}
</style>
