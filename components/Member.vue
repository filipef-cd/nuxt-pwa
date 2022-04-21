<template>
  <nuxt-link :to="`/${data.id}`">
    <div class="app-member">
      <img class="app-member__photo" :src="data.photo" :alt="data.name" />
      <h3 class="app-member__name">
        {{ data.name }}
      </h3>
      <h4 class="app-member__role">
        {{ data.role }}
      </h4>
      <a :href="`mailto:${data.email}`" class="app-member__email">
        {{ data.email }}
        <!-- <font-awesome-icon icon="envelope" /> -->
      </a>
    </div>
  </nuxt-link>
</template>

<script>
export default {
  name: 'AppMember',
  props: {
    data: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style scoped lang="scss">
.app-member {
  @apply relative w-full h-[340px] max-w-[340px] mx-auto rounded-[11px] px-16 py-[24px] mb-[25px];
  @apply cursor-pointer;

  @screen sm {
    @apply max-w-[370px] h-[370px] mb-[50px] px-[32px];
  }

  @screen lg {
    @apply mb-[40px];
  }

  &:nth-of-type(n) {
    background-color: #97e3f0;
  }

  &:nth-of-type(2n) {
    background-color: #c4c6f0;
  }

  &:nth-of-type(3n) {
    background-color: #9ce5d8;
  }

  &:nth-of-type(4n) {
    background-color: #fdccce;
  }

  &:nth-of-type(6n) {
    background-color: #c4c6f0 !important;
  }

  &__photo {
    @apply absolute right-[5px] bottom-0 max-h-[75%] max-w-[85%];
  }

  &__name {
    @apply text-lg font-semibold mb-[0px];
  }

  &__role {
    @apply text-base font-normal;
  }

  &__email {
    @apply hover:text-white hover:scale-[1.2] duration-300;

    svg {
      @apply h-[20px] w-20;
    }

    @screen sm {
      @apply bottom-[22px] left-[30px];
    }
  }

  &:before {
    @apply absolute top-0 left-[0px] w-full h-[370px] opacity-0 duration-500;
    filter: blur(5px);
    transform: scale(1.05);

    content: '';
    background-color: inherit;
  }

  &:hover {
    &:before {
      @apply opacity-50;
    }
  }
}
</style>
