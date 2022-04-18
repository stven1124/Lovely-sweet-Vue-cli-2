<template>
  <div>
    <NavbarBack/>
    <Alert></Alert>
    <div class="container-fluid">
      <div class="row">
        <Sidebar/>
        <main role="main" class="col-lg-9 ml-sm-auto col-lg-10 px-4">
          <router-view></router-view>
        </main>
      </div>
    </div>
  </div>
</template>

<script>
import NavbarBack from './NavbarBack';
import Sidebar from './Sidebar';
import Alert from './AlertMessage';

export default {
  components: {
    NavbarBack,
    Sidebar,
    Alert,
  },
  data() {
    return {};
  },
  created() {
    const token = document.cookie.replace(/(?:(?:^|.*;\s*)hexToken\s*=\s*([^;]*).*$)|^.*$/, '$1');
    this.$http.defaults.headers.common.Authorization = `${token}`;
  }
};
</script>

<style>
.bd-placeholder-img {
  font-size: 1.125rem;
  text-anchor: middle;
}

@media (min-width: 768px) {
  .bd-placeholder-img-lg {
    font-size: 3.5rem;
  }
}
</style>