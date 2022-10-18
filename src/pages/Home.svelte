<script>
  import Footer from './Footer.svelte';
  import { fade, fly} from 'svelte/transition';
  let pageName="Home";
</script>

<!-- change title bar name with svelte special tags -->
<svelte:head>
    <title>Yoga Dwi Septana | {pageName}</title>
</svelte:head>

<!-- space from nav to title page -->
<div style="margin-bottom: 10%;"></div>

<div class="container" in:fade="{{delay: 100, duration: 450}}">
  <div class="row">
    <div class="col-md-12 home-content">
      <h1 class="title-font">Yoga Dwi Septana</h1>
      <h4 class="title-font">Full-Stack Developer</h4>
      <div style="margin-bottom: 10%;"></div>
      <h5 class="desc-font">A person who loves to solve problems that can help many people achieve their goals. Experience in various programming languages, tools, or frameworks such as Code Igniter, Laravel, MySQL, Bootstrap, jQuery, Javascript, Java, C++, Flutter, Python, and Unity. With curiosity, I evolved into a Software Developer who is always glad to learn something new. I'm currently looking for job opportunities as a <b>full-stack developer</b> or another position that is still related to it.<br>
        If you want to know more about me, please contact at
          <b>
            <a href="mailto:yogaseptana@gmail.com" style="color: black">yogaseptana(at)gmail(dot)com</a></b>.
        </h5>
    </div>
  </div>
  <div class="row akun-container">
    <div class="col-md-12">
      <a target="_blank" href="https://linkedin.com/in/yogaseptana">
        <img src="assets/img/icon/linkedin.svg" alt="LinkedIn Logo" title="LinkedIn">
      </a>
      <a target="_blank" href="https://github.com/yogadsp">
        <img src="assets/img/icon/github.svg" alt="Github Logo" title="Github">
      </a>
      <a target="_blank" href="https://www.hackerrank.com/yogaseptana">
        <img src="assets/img/icon/hackerrank.png" alt="HackerRank Logo" title="HackerRank">
      </a>
      <a target="_blank" href="https://profile.codersrank.io/user/yogadsp">
        <img src="assets/img/icon/codersrank.svg" alt="CodersRank Logo" title="CodersRank">
      </a>
    </div>
  </div>
  <Footer /> <!-- load footer page -->
</div>