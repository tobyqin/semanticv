<template>
  <div id="app">
    <router-view />
  </div>
</template>

<style>
.hidden.menu {
  display: none;
}

html,
body {
  height: 100%;
}
.main-body {
  min-height: 78vh;
}

#main-menu {
  background: #056dae;
  background-image: url(/static/images/bg.jpg);
  background-repeat: no-repeat;
  background-size: 100% 100%;
  -moz-background-size: 100% 100%;
  padding-bottom: 40px;
}

#main-menu > .ui.container h2 {
  margin-bottom: 30px;
}

.page-logo {
  width: 50%;
  margin-top: 80px;
  filter: drop-shadow(2px 2px 5px black);
}

#logo-img {
  margin-bottom: -10px;
  width: 35px;
  filter: drop-shadow(1px 1px 3px black);
}

.masthead.segment {
  min-height: 500px;
  padding: 1em 0em;
}

.masthead .logo.item img {
  margin-right: 1em;
}

.masthead .ui.menu .ui.button {
  margin-left: 0.5em;
}

.masthead h1.ui.header {
  margin-top: 1em;
  margin-bottom: 0em;
  font-size: 4em;
  font-weight: normal;
}

.masthead h2 {
  font-size: 1.7em;
  font-weight: normal;
}

.ui.vertical.stripe {
  padding: 8em 0em;
}

.ui.vertical.stripe h3 {
  font-size: 2em;
}

.ui.vertical.stripe .button + h3,
.ui.vertical.stripe p + h3 {
  margin-top: 3em;
}

.ui.vertical.stripe .floated.image {
  clear: both;
}

.ui.vertical.stripe p {
  font-size: 1.33em;
}

.ui.vertical.stripe .horizontal.divider {
  margin: 3em 0em;
}

.quote.stripe.segment {
  padding: 0em;
}

.quote.stripe.segment .grid .column {
  padding-top: 5em;
  padding-bottom: 5em;
}

.footer.segment {
  padding: 5em 0em;
}

.secondary.pointing.menu .toc.item {
  display: none;
}

.ui.secondary.pointing.menu .item.text.router-link-exact-active {
  color: #fff !important;
  font-weight: 700 !important;
  border-bottom-color: #fff;
  border-bottom-style: solid;
  border-bottom-width: 2px;
}

body {
  color: #444;
  font-weight: 300;
  line-height: 1.45;
}

@media only screen and (max-width: 700px) {
  .ui.fixed.menu {
    display: none !important;
  }

  .secondary.pointing.menu .item,
  .secondary.pointing.menu .menu {
    display: none;
  }

  .secondary.pointing.menu .toc.item {
    display: block;
  }

  .masthead.segment {
    min-height: 350px;
  }

  .masthead h1.ui.header {
    font-size: 2em;
    margin-top: 1.5em;
  }

  .masthead h2 {
    margin-top: 0.5em;
    font-size: 1.5em;
  }
}
</style>
