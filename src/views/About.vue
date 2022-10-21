<template>
  <div class="about">
    <h1>This is an about page</h1>
    <dl class="download clearfix">
      <dt>或者更换以下浏览器，继续访问</dt>
      <dd>
        <a
          class="chrome"
          href="https://www.google.com/intl/zh-CN/chrome/"
          target="_blank"
          >Chrome</a
        >
      </dd>
      <dd>
        <a
          class="firefox"
          href="https://www.mozilla.org/zh-CN/firefox/new/"
          target="_blank"
          >Firefox</a
        >
      </dd>
    </dl>
    <a-select default-value="lucy" style="width: 120px">
      <div slot="dropdownRender" slot-scope="menu">
        <v-nodes :vnodes="menu" />
      </div>
      <a-select-option v-for="item in items" :key="item" :value="item">
        {{ item }}
      </a-select-option>
    </a-select>
  </div>
</template>
<script>
let index = 0;
export default {
  components: {
    VNodes: {
      functional: true,
      render: (h, ctx) => ctx.props.vnodes,
    },
  },
  data: () => ({ items: ["jackfdsaaaaaaaaaaa", "lufdsaaaaaaaaaacy"] }),
  methods: {
    addItem() {
      console.log("addItem");
      this.items.push(`New item ${index++}`);
    },
  },
};
</script>
<style scoped>
.ant-select-dropdown.ant-select-dropdown--single {
  min-width: 120px;
}
.download {
  width: 370px;
  margin: 0 auto;
  overflow: hidden;
}
.download dt {
  margin: 0 0 20px;
  padding: 0;
  color: #999;
}
.download dd {
  float: left;
  width: 160px;
  height: 60px;
  margin: 0 8px;
  list-style: none;
  border-radius: 10px;
  border: 1px solid #e6e6e6;
}
.download dd .chrome {
  background-position: center 0;
}
.download dd .firefox {
  background-position: center -60px;
}
.download dd a {
  display: block;
  height: 60px;
  background-image: url("//i1.mifile.cn/f/i/17/update-browser/icons.png");
  background-repeat: no-repeat;
  text-indent: -9999em;
  border-radius: 10px;
  -webkit-transition: all 0.3s;
  transition: all 0.3s;
}
</style>
