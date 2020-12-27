<template>
  <div class="hello">
    <div class="text">
      <span class="title">
        <img
          :src="require('~/assets/' + $t('hello.svg'))"
          :alt="$t('hello.title')"
          class="svg"
        />
      </span>
    </div>
    <div class="text">
      <span class="description">
        {{ $t("hello.message") }}
      </span>
    </div>
    <MoreButton
      title="goto profile"
      :path="localePath('/profile')"
      class="more-button"
    />
  </div>
</template>

<style scoped>
.svg {
  height: 50px;
  background: linear-gradient(transparent 60%, #7db9de 60%);
}
#title {
  fill: #0f2540;
}
.hello {
  max-width: 700px;
}
.text {
  margin-bottom: 10px;
}
.description {
  background: linear-gradient(transparent 40%, #ffffff 40%);
  font-size: 20px;
}
.more-button {
  margin-top: 14px;
}
span {
  color: #0f2540;
}
</style>
