<script>
  import { scale, slide, fade, fly } from "svelte/transition";
  import { OnMount } from 'fractils';

// export let visible = false;
// let init = false

// onMount(() => {
//   init = true;
// });


</script>


  <img class="header-logo" src="logo-rectangle.png" width="114" alt="logo-rect" />
  <div class="container">
  
 
    <img src="logo-square-1.png"  width=40 alt="logo-square" />
    <h1>A <span style="color: #366CA5">better</span> way to generate leads</h1>
   
    <p>Resider is a smart, efficient and helpful way to qualify and schedule your prosepective tenants.</p>
    <OnMount>
      <div in:fly={{ y: +500, duration: 1000}}  >
        <img in:fade src="image-1.png" width=342 alt="hero-1">
      
    
    <div class="section2">
        <h2>Platform <span style="color: #366CA5">integrity</span></h2>
        <p class="p2">Resider solely consists of rental properties syndicated through data API’s. With up to date and accurate listings, your clients can browse with confidence.</p>
        <br/>
        <img style="padding-top: 45.69px" src="image-2.png" width=382 alt="card">
      </div>


      <div class="section2">
        <h2><span style="color: #366CA5">Move in date</span> filter</h2>
        <p class="p2">Qualified leads are our emphasis. Allowing users to narrow down exact availability by their move in date is the first step.</p>
        <br/>
        <img style="padding-top: 45.69px" src="image-move-date.png" width=382 alt="card">
      </div>



      <div class="section3">
          
      </div>
    </div>
    </OnMount>
    
  </div>
  

<style>
  * {
    font-family: "Gilroy", "Open Sans", -apple-system;
  }

  .container {
      display: flex;
      flex-direction: column;
      align-content: center;
      align-items: center;
      text-align: center;
      
    padding: 20px;
    padding-top: 26px;
  }

  .section2 {
      padding-top: 82px;
  }



  .header-logo {
    margin: 16px;
  }

  h1 {
    font-size: 36px;
    font-weight: 700;
    line-height: 48px;
    letter-spacing: 0.1px;
    color: #3C4043;
    max-width: 326px;
  }

  h2 {
    font-weight: 700;
    font-size: 28px;
    line-height: 38px;
    letter-spacing: 0.1px;
    color: #3C4043;
  }

  p {
      font-size: 18px;
      line-height: 30px;
      font-weight: 400;
      color: #606367;
      max-width: 326px;
      text-align: center;
;
  }

  .p2 {
      font-weight: 400;
      font-size: 16px;
      line-height: 28px;
      max-width: 326px;
      margin: auto;
      text-align: center;
  }

  @font-face {
  font-family: 'Gilroy';
  font-style: normal;
  font-weight: 400;
  font-display: swap;
  src: local('Gilroy'), local('Gilroy-Regular'),
    url('./regular.woff2') format('woff2'), url('./regular.woff') format('woff');
}

@font-face {
  font-family: 'Gilroy';
  font-style: normal;
  font-weight: 500;
  font-display: swap;
  src: local('Gilroy Medium'), local('Gilroy-Medium'),
    url('./medium.woff2') format('woff2'), url('./medium.woff') format('woff');
}

@font-face {
  font-family: 'Gilroy';
  font-style: normal;
  font-weight: 600;
  font-display: swap;
  src: local('Gilroy SemiBold'), local('Gilroy-SemiBold'),
    url('./semi-bold.woff2') format('woff2'),
    url('./semi-bold.woff') format('woff');
}

@font-face {
  font-family: 'Gilroy';
  font-style: italic;
  font-weight: 400;
  font-display: swap;
  src: local('Gilroy Italic'), local('Gilroy-Italic'),
    url('./italic-regular.woff2') format('woff2'),
    url('./italic-regular.woff') format('woff');
}

@font-face {
  font-family: 'Gilroy';
  font-style: italic;
  font-weight: 500;
  font-display: swap;
  src: local('Gilroy Medium Italic'), local('Gilroy-MediumItalic'),
    url('./italic-medium.woff2') format('woff2'),
    url('./italic-medium.woff') format('woff');
}

</style>

