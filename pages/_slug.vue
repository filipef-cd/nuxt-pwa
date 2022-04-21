<template>
  <div class="max-w-screen-2xl mx-auto px-10">
    <Header />
    <div class="app-member-page__page">
      <div class="app-member-page__container">
        <img
          class="app-member-page__photo"
          :src="memberData.photo"
          :alt="memberData.name"
        />
        <h3 class="app-member-page__name">
          {{ memberData.name }}
        </h3>
        <h4 class="app-member-page__role">
          {{ memberData.role }}
        </h4>
        <a :href="`mailto:${memberData.email}`" class="app-member-page__email">
          {{ memberData.email }}
          <!-- <font-awesome-icon icon="envelope" /> -->
        </a>
        <p class="app-member-page__description">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Laboriosam
          numquam tenetur rem reiciendis fugiat odio pariatur aliquam animi
          fugit. Tempora eaque soluta saepe porro ut ab vero culpa fugiat,
          dolores architecto suscipit corrupti maiores beatae aspernatur.
          Laudantium ducimus doloremque iste quas totam possimus nulla vero,
          necessitatibus assumenda incidunt quibusdam culpa.
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import members from '~/contents/members'
import Header from '~/components/Header'
export default {
  name: 'AppMemberPage',
  components: { Header },

  asyncData({ params, route }) {
    const slug = params.slug

    const memberData = members.find((member) => member.id === slug)
    return {
      memberData,
    }
  },
}
</script>

<style scoped lang="scss">
.app-member-page {
  &__container {
    @apply relative w-full max-w-[800px] mx-auto h-[800px] rounded-[16px] mt-[80px] p-[32px];
    background-color: #97e3f0;
  }

  &__photo {
    @apply absolute right-[5px] bottom-0 max-h-[100%] max-w-[100%] h-[65%];
  }

  &__name {
    @apply text-3xl font-semibold mb-[0px];
  }

  &__role {
    @apply text-xl font-normal;
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

  &__description {
    @apply mt-[30px] max-w-[50%] bottom-[32px];
  }
}
</style>
