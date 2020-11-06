<template>
  <div class="card">
    <div v-if="!isLoaded" class="skeleton-wrapper">
      <div class="skeleton" />
    </div>
    <img
      v-lazy="require('~/assets/' + thumbnail)"
      alt="thumbnail"
      class="image"
      @load="isLoaded = true"
    >
    <div ref="card" class="card-content">
      <div class="title">
        <span class="text">
          {{ title }}
        </span>
        <div v-if="tags != undefined" class="tag-box">
          <div v-for="(tag, i) in tags" :key="i" class="tag">
            <span>{{ tag }}</span>
          </div>
        </div>
      </div>
      <div v-if="showDetails" class="details">
        <div v-if="description != ''" class="description">
          {{ description }}
        </div>
        <div v-if="infomations.length > 0" class="infomation">
          <table>
            <tr v-for="(infomation, i) in infomations" :key="i">
              <td class="title">
                {{ infomation.title }}
              </td>
              <td>{{ infomation.data }}</td>
            </tr>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue, { PropType } from 'vue'
type Infomation = {
  title: string;
  data: string;
};
export default Vue.extend({
  props: {
    thumbnail: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    },
    tags: {
      type: Array as PropType<Text[]>,
      required: true
    },
    description: {
      type: String,
      default: '',
      required: false
    },
    infomations: {
      type: Array as PropType<Infomation[]>,
      default: [],
      required: false
    },
    showDetails: {
      type: Boolean,
      default: true,
      required: false
    }
  },
  data () {
    return {
      isLoaded: false
    }
  }
})
</script>

<style scoped>
/* ----------------------- */
.skeleton-wrapper {
  position: relative;
  width: 100%;
}
.skeleton-wrapper:before {
  content:"";
  display: block;
  padding-top: 56.25%;
}
.skeleton{
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  border-radius: 6px 6px 0 0;
  background: #d9d9d9;
  overflow: hidden;
}
.skeleton::before{
  content: '';
  display: block;
  height: 100%;
  width: 100%;
  background: linear-gradient(90deg, transparent, rgba(255,255,255,0.5), transparent);
  position: absolute;
  top: 0;
  left: 0;
  animation: skeleton-animation 1.2s linear infinite;
}
@keyframes skeleton-animation{
  0%{
    transform: translateX(-100%);
  }
  100%{
    transform: translateX(100%);
  }
}
/* ----------------------- */
.card {
  border-radius: 6px;
  background: #ffffff;
  max-width: 420px;
  border: 1px solid #0f2540;
  box-shadow: 3px 3px 0 0 #0f2540;
}
.image {
  width: 100%;
  height: auto;
  border-radius: 6px 6px 0 0;
  background: #6f7c8c;
}
.card-content {
  padding: 20px;
}
.title {
  display: flex;
}
.text {
  line-height: 31px;
  font-size: 16px;
  color: #0f2540;
  font-weight: 700;
}
.tag-box {
  display: flex;
  margin-top: 3px;
}
.tag {
  margin-left: 10px;
  height: 23px;
  line-height: 19px;
  border: 1px solid #6f7c8c;
  border-radius: 2px;
  padding: 0 8px 0 8px;
}
.tag span {
  font-size: 12px;
  color: #6f7c8c;
}
.description {
  line-height: 24px;
  color: #0f2540;
  font-size: 14px;
  margin-top: 12px;
}
.infomation {
  margin-top: 12px;
}
td{
  font-size: 12px;
  color: #6f7c8c;
  vertical-align: top;
}
.infomation .title {
  width: 130px;
}
</style>
