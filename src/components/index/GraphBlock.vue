<template>
  <div class="graph">
    <svg class="graph__red" xmlns="http://www.w3.org/2000/svg" width="84" height="84" viewBox="0 0 84 84" fill="none">
      <g filter="url(#filter0_d_704_328)">
        <circle cx="42" cy="22" r="7" fill="#FF8B8B"/>
      </g>
      <defs>
        <filter id="filter0_d_704_328" x="0" y="0" width="84" height="84" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
          <feFlood flood-opacity="0" result="BackgroundImageFix"/>
          <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
          <feOffset dy="20"/>
          <feGaussianBlur stdDeviation="17.5"/>
          <feColorMatrix type="matrix" values="0 0 0 0 0.354167 0 0 0 0 0.196741 0 0 0 0 0.196267 0 0 0 0.4 0"/>
          <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_704_328"/>
          <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_704_328" result="shape"/>
        </filter>
      </defs>
    </svg>

    <img class="graph__categories" src="@/assets/img/categories.png" alt="">
    <img class="graph__analitics" src="@/assets/img/analitics.png" alt="">
    <img class="graph__questions" src="@/assets/img/questions.png" alt="">
    <img class="graph__photo" src="@/assets/img/photo.png" alt="">

    <svg class="graph__yellow" xmlns="http://www.w3.org/2000/svg" width="92" height="81" viewBox="0 0 92 81" fill="none">
      <g filter="url(#filter0_d_704_326)">
        <circle cx="46" cy="26" r="11" fill="#FFC86F"/>
      </g>
      <defs>
        <filter id="filter0_d_704_326" x="0" y="0" width="92" height="92" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB">
          <feFlood flood-opacity="0" result="BackgroundImageFix"/>
          <feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/>
          <feOffset dy="20"/>
          <feGaussianBlur stdDeviation="17.5"/>
          <feColorMatrix type="matrix" values="0 0 0 0 0.6125 0 0 0 0 0.394428 0 0 0 0 0.13526 0 0 0 0.3 0"/>
          <feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_704_326"/>
          <feBlend mode="normal" in="SourceGraphic" in2="effect1_dropShadow_704_326" result="shape"/>
        </filter>
      </defs>
    </svg>
  </div>
</template>

<script>
export default {
  name: 'GraphBlock',
}
</script>

<style lang="scss" scoped>
  .graph {
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    min-width: 100%;
    &__categories {
      position: absolute;
      top: 140px;
      right: 0;
    }
    &__analitics {
      position: absolute;
      top: 102px;
      right: 286px;
    }
    &__questions {
      position: absolute;
      top: 470px;
      right: 404px;
    }
    &__photo {
      position: absolute;
      top: 556px;
      left: -350px
    }
    &__yellow {
      position: absolute;
      right: 293px;
      bottom: 0;
    }
    &__red {
      position: absolute;
      top: 298px;
      right: 360px;
    }
  }

  @media (max-width: 1270px) {
    .graph__analitics,
    .graph__questions {
      display: none;
    }
  }
</style>