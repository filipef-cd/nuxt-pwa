<template>
  <div class="max-w-screen-2xl mx-auto px-10">
    <Header />
    <main>
      <div class="app-team-list">
        <div class="app-team-list__grid">
          <Member
            v-for="(member, index) in members"
            :key="index"
            :data="member"
          />
        </div>
      </div>
    </main>
  </div>
</template>

<script>
import members from '~/contents/members'
import Member from '~/components/Member'
import Header from '~/components/Header'

export default {
  name: 'AppIndex',
  components: {
    Member,
    Header,
  },

  data() {
    return {
      members,
    }
  },

  head() {
    return {
      title: 'Spring Financial | Meet The Team',
    }
  },
}
</script>

<style scoped lang="scss">
body {
  background: linear-gradient(0deg, #fff 57%, #ededff);
}
.app-team-list {
  @apply mt-[70px] mb-[170px] mx-auto flex flex-col items-center w-full;

  @screen lg {
    @apply mt-[130px];
  }

  &__title {
    @apply mb-[40px];

    @screen lg {
      @apply mb-[85px];
    }
  }

  &__grid {
    @apply w-full;

    @screen md {
      @apply grid flex-col justify-center max-w-[780px];

      grid-template-columns: repeat(2, 1fr);
      grid-column-gap: 40px;
    }

    @screen lg {
      @apply max-w-none;

      grid-template-columns: repeat(3, 1fr);
    }
  }
}
</style>
