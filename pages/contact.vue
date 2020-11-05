<template>
  <ContentCard>
    <span>{{ $t("contact") }}</span>
    <div class="mail">
      <a href="mailto:muto.tsujimoto@gmail.com">muto.tsujimoto@gmail.com</a>
    </div>
  </ContentCard>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  head () {
    return {
      title: 'contact'
    }
  }
})
</script>

<style scoped>
span{
  font-size: 14px;
}
.mail{
  margin-top: 8px;
}
.mail a{
  font-size: 16px;
  text-decoration: underline;
}
</style>
