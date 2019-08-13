<template>
    <div class="footer" id="footer">
        <div class="mainfooter">
            <strong>Copyright Ahmed Akhtar 2019 </strong>
            <br>
            <a class="button" :href="github_href">
                <img :src="github_logo" :width="50" :height="50">
            </a>
        </div>
    </div>
</template>

<script>
export default {
  name: 'Footer',
  data() {
      return {
          github_logo: 'https://cdn1.iconfinder.com/data/icons/capsocial/500/github-512.png',
          github_href: 'https://github.com/ahmedakhtar11'

      }
  }
}
</script>

<style scoped>
#footer {
background-color: lightskyblue;
border: 1px solid black;
position: relative;
bottom: 0;
width: 100%;
height: 5rem;  
}
</style>