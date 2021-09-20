<script>
export default {
  data: () => ({
    msg: "첫번째 JSX 컴포넌트 입니다.",
  }),

  render() {
    return <div class="my-jsx">{this.msg}</div>;
  },
};
</script>

<style scoped>
.my-jsx {
  color: #ff1493;
}
</style>
