<template>
  <app-navbar></app-navbar>
  <router-view></router-view>
</template>

<script>
import appNavbar from "./components/appNavbar";
import axios from "axios";
export default {
  components: {
    appNavbar,
  },
};
</script>
