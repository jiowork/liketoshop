<template>
  <div class="profile">
    <div class="profile-banner" v-if="!user.username">
      <img class="avatar" src="../../assets/images/photo.png" alt />
      <cube-button primary inline @click="toLogin">登录</cube-button>
    </div>
    <div class="profile-banner" v-else>
      <img class="avatar" src="../../assets/images/photo.png" alt />
      <cube-button primary inline>{{user.username}}</cube-button>
    </div>
  </div>
</template>


<script>
import { mapState } from "vuex";
export default {
  computed: {
    ...mapState(["user"])
  },
  methods: {
    toLogin() {
      this.$router.push("/login");
    }
  }
};
</script>

<style lang="stylus">
.profile {
  &-banner {
    display: flex;
    justify-content: center;
    flex-direction: column;
    width: 100%;
    align-items: center;
    height: 300px;
    background: url('../../assets/images/user_bg.png');
    background-color: blue;
  }

  .avatar {
    width: 80px;
    margin-bottom: 30px;
    height: 80px;
  }

  .list {
    font-size: 30px;
    line-height: 30px;
  }
}
</style>