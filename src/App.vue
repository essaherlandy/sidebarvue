<template>
  <div id="panel">
    <sidebar-menu
      :collapsed="collapsed"
      :menu="menu"
      :theme="selectedTheme"
      :show-one-child="true"
      @collapse="onCollapse"
      @itemClick="onItemClick"
    ></sidebar-menu>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  data() {
    return {
      menu: [
        {
          header: true,
          title: "Main Navigation",
          hiddenOnCollapse: true,
        },
        {
          title: "User",
          icon: "fa fa-user",
          child: [
            {
              href: "/panel/group_user_list",
              title: "Group User",
            },
            {
              href: "/panel/user_list",
              title: "User List",
            },
          ],
        },
        {
          title: "Banner",
          icon: "fa fa-flag",
          href: "/panel/banner",
        },
        {
          title: "Subscriber",
          icon: "fa fa-envelope",
          href: "/panel/subscriber",
        },
        {
          title: "Recipe",
          icon: "fa fa-list",
          child: [
            {
              href: "/panel/recipe_community",
              title: "by Community",
            },
            {
              href: "/panel/recipe_tiarapot",
              title: "by Tiarapot",
            },
          ],
        },
        {
          title: "Pers",
          icon: "fa fa-headset",
          href: "/panel/pers",
        },
      ],
    };
  },
  props: {
    relative: {
      type: Boolean,
      default: true,
    },
  },
};
</script>

<style>
.fade-animation-enter-active {
  transition: transform 0.15s, opacity 0.45s !important;
}
.fade-animation-enter,
.fade-animation-leave-to {
  transform: translateX(-60%) !important;
  opacity: 0 !important;
}
</style>