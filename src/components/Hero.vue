<template>
  <div
    class="flex h-screen-80 max-w-7xl m-center mt-24 md:flex-col lg:flex-row md:pt-10"
  >
    <div class="info flex flex-col items-start lg:w-3/6 m-auto">
      <h2
        data-aos="fade-right"
        data-aos-delay="500"
        data-aos-duration="500"
        class="text-5xl pb-3 font-extrabold f-black name dark:text-white duration-1000"
      >
        Khier de Leon.
      </h2>
      <h4
        class="text-lg pb-2 f-gray dark:text-white duration-1000"
        data-aos="fade-right"
        data-aos-delay="700"
        data-aos-duration="500"
      >
        Software Developer
      </h4>
      <h5
        class="text-sm pb-12 f-gray dark:text-white duration-1000"
        data-aos="fade-right"
        data-aos-delay="800"
        data-aos-duration="500"
      >
        I'm an experienced software developer with a passion for developing innovative programs. 
        Well-versed in technology and able to write code to construct dependable and user-friendly solutions. 
        Highly skilled in JavaScript(React/VueJS)
      </h5>
      <div data-aos="fade-right" data-aos-delay="800" data-aos-duration="700">
        <a
          class="btn-accent cursor-pointer flex items-center"
          href="mailto:kirochan.kd@gmail.com"
        >
          <span> Contact Me&nbsp;</span>
          <span
            ><font-awesome-icon class="w-4" :icon="['fas', 'paper-plane']"
          /></span>
        </a>
      </div>
    </div>
    <div class="profile-image lg:w-2/6 flex hidden md:flex md:m-auto md:pt-16">
      <img
        data-aos="zoom-in-right"
        data-aos-delay="1700"
        data-aos-duration="800"
        class="m-auto clipped light imedium img-center md:w-auto"
        src="https://drive.google.com/uc?id=1hnbxNrPhcr3DyGbfDPNFAlxCgduzoVfR"
        alt=""
        width="500"
      />
    </div>
  </div>
</template>
<script lang="ts" setup>
import { watch } from "@vue/runtime-dom";
import { useDark, useToggle } from "@vueuse/core";
const isDark = useDark();
</script>
<style lang="scss" scoped>
.clipped {
  clip-path: polygon(25% 0%, 100% 0%, 75% 100%, 0% 100%);
}
.ismall {
  height: 19rem;
}
.imedium {
  height: 25rem;
}

.img-first {
  margin-left: 12px;
  height: 350px;
  clip-path: polygon(25% 0%, 100.5% 0%, 73% 100%, 0% 100%);
}

.img-center {
  margin-left: -66px;
}

.img-last {
  margin-left: -65px;
}

.light {
  filter: grayscale(40%);
  transition: 0.5s ease-out 100ms;
  cursor: pointer;

  &:hover {
    filter: grayscale(0);
    transform: scale(1.03);
    z-index: 999;
  }

  &.colored {
    filter: grayscale(0) !important;
  }
}
</style>
