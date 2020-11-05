<template>
  <div class="hello">
    <div class="text">
      <span class="title">
        {{ $t("hello.title") }}
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
.hello{
  max-width: 700px;
}
.text {
  margin-bottom: 10px;
}
.title {
  background: linear-gradient(transparent 40%, #7db9de 40%);
  font-weight: 700;
  font-size: 22px;
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
