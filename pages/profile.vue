<template>
  <div>
    <h3 class="name">
      {{ $t("profile.name") }}
    </h3>
    <p class="birth">
      {{ $t("profile.birthday") }}
    </p>
    <div v-for="(content, i) in $t('profile.contents')" :key="i" class="content-box">
      <Index :text="content.heading" />
      <ContentCard>
        <p v-for="(text, j) in content.texts" :key="j">
          {{ text }}
        </p>
      </ContentCard>
    </div>
    <div class="content-box">
      <Index :text="$t('profile.whatICanDo.heading')" />
      <ContentCard>
        <table>
          <tr v-for="(row, j) in $t('profile.whatICanDo.rows')" :key="j">
            <td class="title">
              {{ row.title }}
            </td>
            <td>{{ row.data }}</td>
          </tr>
        </table>
      </ContentCard>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  head () {
    return {
      title: 'profile'
    }
  }
})
</script>

<style scoped>
.name {
  font-size: 22px;
  color: #0f2540;
}
.birth {
  font-size: 12px;
  color: #6f7c8c;
}
.content-box{
  margin-top: 50px;
  color: #0f2540;
  font-size: 14px;
  line-height: 26px;
}
.content-box .title {
  width: 140px;
}
td{
  vertical-align: top;
}

</style>
