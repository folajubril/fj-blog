<template>
  <nav class="navbar navbar-expand-lg fixed-top navbar-dark bg-dark">
    <a 
      class="navbar-brand text-white" 
      href="/">FJ</a>
    <button 
      class="navbar-toggler" 
      type="button" 
      data-toggle="collapse" 
      data-target="#navbarSupportedContent" 
      aria-controls="navbarSupportedContent" 
      aria-expanded="false" 
      aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"/>
    </button>
    <div 
      id="navbarSupportedContent" 
      class="collapse navbar-collapse" >
      <ul class="navbar-nav ml-auto">
        <li class="nav-item active">
          <a 
            class="nav-link" 
            href="/">Home <span 
              class="sr-only">(current)</span></a>
        </li>
        <li 
          class="nav-item">
          <a 
            class="nav-link"
            href="/about/about">About</a>
        </li>
        <li 
          class="nav-item">
          <a
            class="nav-link"
            href="/mission/mission">Mission</a>
        </li>
        <li 
          class="nav-item">
          <a 
            class="nav-link" 
            href="/insights/insights">Insights</a>
        </li>
        <li 
          class="nav-item">
          <a 
            class="nav-link" 
            href="#">Contact</a>
        </li>
      </ul>
    </div>
  </nav>
</template>
<script>
export default {}
</script>
<style scoped>
nuxt-link {
  text-decoration: none;
  font-family: 'Lato', 'sans-serif';
  color: #faebd7;
}
.active {
  color: #faebd7;
}
.nav-link:hover {
  color: #faebd7;
}
</style>
