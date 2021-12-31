<template>
  <nav id="sidebar" class="sidebar js-sidebar">
    <div class="sidebar-content js-simplebar">
      <div class="bg-dark" style="position: fixed; width: 259px; z-index: 999">
        <a class="sidebar-brand headBar" href="/">
          <span class="align-middle">Fabbi</span>
        </a>
      </div>

      <ul class="sidebar-nav" style="margin-top: 66px">
        <li class="sidebar-item">
          <a class="sidebar-link navItem" href="/">
            <i class="align-middle" data-feather="sliders"></i>
            <span class="align-middle">Dashboard</span>
          </a>
        </li>

        <li class="sidebar-header">MANAGEMENT</li>

        <li class="sidebar-item">
          <a class="sidebar-link navItem" href="">
            <i class="align-middle" data-feather="sliders"></i>
            <span class="align-middle">Cong so</span>
          </a>
        </li>

        <li class="sidebar-item">
          <a class="sidebar-link navItem" href="">
            <i class="align-middle" data-feather="clock"></i>
            <span class="align-middle">Lam them OT</span>
          </a>
        </li>

        <li class="sidebar-item">
          <a class="sidebar-link navItem" href="">
            <i class="align-middle" data-feather="file-plus"></i>
            <span class="align-middle">Bo sung cong so</span>
          </a>
        </li>

        <li class="sidebar-item">
          <a class="sidebar-link navItem" href="">
            <i class="align-middle" data-feather="file-text"></i>
            <span class="align-middle">Nghi phep</span>
          </a>
        </li>

        <li class="sidebar-item">
          <a class="sidebar-link navItem" href="">
            <i class="align-middle" data-feather="book"></i>
            <span class="align-middle">Huong dan su dung</span>
          </a>
        </li>
      </ul>

      <div class="sidebar-cta footBar">
        <a class="sidebar-brand" href="/" style="float: right">
          <i class="align-middle" data-feather="chevron-left"></i>
        </a>
      </div>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style scoped>
.headBar {
  background: #303c54;
}
.footBar {
  background: #303c54;
}
.footBar:hover {
  background: #212529;
}
.sidebar-nav {
  background: #3c4b64;
  text-align: left;
}
.sidebar-link {
  background: #3c4b64;
}
.sidebar-link:hover {
  background: #6610f2;
}
.nav-tag {
  padding: 0 5px;
}
.navItem {
  padding-top: 1.5em;
  padding-bottom: 1.5em;
}
</style>>
