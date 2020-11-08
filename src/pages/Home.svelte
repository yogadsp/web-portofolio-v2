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
      <h4 class="title-font">Informatics Engineering Fresh Graduate</h4>
      <div style="margin-bottom: 10%;"></div>
      <h5 class="desc-font">I am an informatics engineering student who has just graduated from Institut Teknologi Sumatera in Lampung. My final project entitled is <b>"Prototype of Automatic Trash Bin by Applying Internet of Things (IoT)"</b> where the trash bin can sort organic and inorganic trash and also can send full trash notifications to an Android-based mobile application. I love to learn new things to overcome my curiosity. I am a hard worker who is able to work both as a team and individually. I'm currently looking for job opportunities as a <b>back-end developer or another position that is still related to it</b>.<br>
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