<template>
  <div class="container main-container">
    <div class="layout">

      <header id="banner" class="header">
      <h1>
        <g-link to="/">{{ $static.metaData.siteName }}</g-link>
      </h1>
      <div class="top-divider"></div>
      
      <slot name="nav">
        <nav class="nav">
          <g-link class="nav__link" to="/">Home</g-link>
          <g-link class="nav__link" to="/about/">About</g-link>
        </nav>
      </slot>  
    </header>
      <slot/>
    </div>
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style>

</style>
