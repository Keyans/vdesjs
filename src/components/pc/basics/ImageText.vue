<template>
  <div
     class="var"
     :style="{
       '--boxBg': myItem.propValues[boxBgIndex].value,
        '--smItemWidth': smItemWidth,
     }"
  >
    <ul class="container-fluid imageText" v-if="myItem.templates.chooseKey == 'sxpl'">
      <li v-for="(item, i) in myItem.propValues[dataIndex].value.data" :key="i" class="col-xs-12 sm_item">
        <div class="box">
          <div class="img">
            <div class="img-wrapper">
              <img
              style="width:120px;height:120px"
                :src="item.imageUrl"
                alt=""
              />
            </div>
          </div>
          <div class="text">
            <div class="title">
              <h4>{{item.name}}</h4>
            </div>
            <div class="desc">
              <p>{{item.desc}}</p>
            </div>
          </div>
        </div>
      </li>
    </ul>
    <ul class="container-fluid imageText" v-if="myItem.templates.chooseKey == 'zypl'">
      <li v-for="(item, i) in myItem.propValues[dataIndex].value.data" :key="i" class="col-xs-12 sm_item">
        <div class="box2">
          <div class="img2">
            <div class="img-wrapper">
              <img
               style="width:120px;height:120px"
                :src="item.imageUrl"
                alt=""
              />
            </div>
          </div>
          <div class="text2">
            <div class="title">
              <h4>{{item.name}}</h4>
            </div>
            <div class="desc">
              <p>
                {{item.desc}}
              </p>
            </div>
          </div>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  props: {
    myItem: {},
  },
  data() {
    return {
      dataIndex: 0,
      boxBgIndex: 1,
      colNumIndex: 2,
    }
  },
  computed: {
    smItemWidth() {
      return 100 / this.myItem.propValues[this.colNumIndex].value + "%";
    }
  }

};
</script>
<style scoped>
@import "bootstrap/dist/css/bootstrap.min.css";
.var {
  --boxBg: lightgray;
  --smItemWidth: 33.3%;
}

.imageText {
  display: flex;
  flex-wrap: wrap;
}
.img-wrapper {
  display: flex;
  justify-content: center;
  padding: 12px;
}
.title h4 {
  display: flex;
  justify-content: center;
  font-size: 22px;
  font-weight: 700;
  padding: 5px;
}
.desc {
  display: flex;
  justify-content: center;
  font-size: 16px;
  color: rgba(143, 149, 170, 1);
  padding: 5px;
}
@media (min-width: 768px) {
  .sm_item {
    width: var(--smItemWidth);
    
  }
}
.box {
  background-color: var(--boxBg);
  margin-bottom: 5px;
}
.box2 {
  display: flex;
  background-color: var(--boxBg);
  margin-bottom: 5px;
}
.img2 {
}
</style>