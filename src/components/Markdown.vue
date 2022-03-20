<template>
  <div class="box">
    <h1>MarkDown</h1>
    <v-md-editor v-model="text" height="80vh"
    left-toolbar="undo redo | bold italic table"
    right-toolbar="image link emoji "
    :disabled-menus="[]"
    @upload-image="handleUploadImage"
    ></v-md-editor>
    <button v-on:click="showText">显示</button>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data() {
    return {
      text: '',
    };
  },
  methods: {
    showText () {
      alert(this.text);
    },
    handleUploadImage(event, insertImage, files) {
      // 拿到 files 之后上传到文件服务器，然后向编辑框中插入对应的内容
      console.log(files);
      const imgUrl = 'https://ss0.bdstatic.com/70cFvHSh_Q1YnxGkpoWK1HF6hhy/it/u=1269952892,3525182336&fm=26&gp=0.jpg';

      // 此处只做示例
      insertImage({
        url: imgUrl,
        desc: '',
        width: 'auto',
        height: 'auto',
      });
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.box {
  height: 100vh;
  width: 100vw;
  margin: -8px;
}
</style>
