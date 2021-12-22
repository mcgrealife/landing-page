<script>
  	import { bounceOut } from 'svelte/easing'
  import { scale, slide, fade, fly } from "svelte/transition";
  // import { Fractils } from "fractils";
  import { OnMount } from "fractils";
  import Spacer from "../components/Spacer.svelte";
  // import { visibility } from 'fractils'
  import { inview } from "svelte-inview";
  import { screenH, screenW, scrollY } from "fractils";
  import { flip } from 'svelte/animate';


  // let visible, scrollDir, options = {threshold: .5}

  let isInView;
  let scrollDirection;
  const options = {
    rootMargin: '0px',
    unobserveOnEnter: false,
  };

  const handleChange = ({detail}) => {
    isInView = detail.inView;
    scrollDirection = detail.scrollDirection.vertical;
  }


  let isInView2;
  const options2 = {
    rootMargin: '0px',
    unobserveOnEnter: false,
  };
  const handleChange2 = ({detail}) => {
    isInView2 = detail.inView;
    scrollDirection = detail.scrollDirection.vertical;
  }


  let innerWindowWidth;
  let y;
  $: mobile = innerWindowWidth <= 900;

  $: desktop = !mobile;

  let color = {
    primaryBlue: "#366CA5",
    primaryDark: "3C4043",
  };

  let typeText = "Resider is a smart, efficient and helpful way to qualify and schedule your prosepective tenants."
  
  const handleClick = () => {
    alert("SUP");
  };
</script>

<svelte:window bind:innerWidth={innerWindowWidth} bind:scrollY={y} />


  <!-- <Fractils /> -->
  <div id="square" in:fly={{ y: +500, duration: 1000 }}></div>
  <h1 in:fly={{ y: +500, duration: 1000 }}>hello</h1>

  {#if desktop}
    <div class="desktop-header">
      <img
        style="margin: 12px 0px 10px 24px"
        src="logo-rectangle.png"
        alt="logo-rect"
        width="101"
        height="50"
      />
      <button class="btn-primary" on:click={handleClick}>Schedule Demo</button>
    </div>
  {:else}
    <img
      style="margin-left: 28px; margin-top: 24px;"
      src="logo-rectangle.png"
      alt="logo-rect"
      width="114"
      height="57"
    />
  {/if}

  <Spacer m="36" d="48" />



  <div class="container">
    <img src="logo-square-1.png" width={desktop ? 56 : 40} alt="logo-square" />
    <Spacer m="28" d="28" />

    <h1 class:h1-desktop={desktop}>
      A <span style="color: {color.primaryBlue}">better </span> way to generate leads
    </h1>
  


    <Spacer m="16" d="16" />


    <div class={desktop? "typeDesktop" :"typeMobile"}>
      <p class:p-desktop={desktop}>
        {typeText.substring(0,y)}
      </p>
    </div>
   

    <div></div>
    <!-- <OnMount> -->
      <Spacer m="45" d="24" />
      <div in:fly={{ y: +500, duration: 1000 }}>
        <div class="lottie">
          <lottie-player
            src="source.json"
            background="transparent"
            speed="1"
            style="width: {desktop ? '492px' : '300px'}; height: {desktop
              ? '492px'
              : '342px'}"
            autoplay
          />
        </div>
        <!-- <img in:fade src="image-1.png" width={desktop ? 492 : 342} alt="hero-1" > -->

        <Spacer m="82" d="82" />
        <div class="section2">
          <h2>Platform <span style="color: #366CA5">integrity</span></h2>
          <p class="p2">
            Resider solely consists of rental properties syndicated through data
            API’s. With up to date and accurate listings, your clients can
            browse with confidence.
          </p>
          <br />
          <Spacer m="46" d="46" />
          <img src="image-2.png" width="382" alt="card" />
        </div>

        <!-- <Spacer m="82" d="82" /> -->


  <div class="inViewExample">
    <div use:inview={options} on:change={handleChange}>
      <div 
        class:animate={isInView}
        class:animateFromBottom={scrollDirection === 'down'}
        class:animateFromTop={scrollDirection === 'up'}>
        
        {#if scrollDirection === 'up'}
        Scroll past me, then scroll back up
        
        {:else if scrollDirection === 'down'}
        Now I'm red
        
        {:else}
        hello
        {/if}
      </div>
    </div>
  </div>




        <h2><span style="color: #366CA5">Move in date</span> filter</h2>
        <p class="p2">
          Qualified leads are our emphasis. Allowing users to narrow down exact
          availability by their move in date is the first step.
        </p>
        <br />

        <Spacer m="46" d="46" />
        <img src="image-move-date.png" width="382" alt="card" />
      </div>
    <!-- </OnMount> -->
  </div>



  <div class="inViewExample2" in:scale={{ delay: 5000, duration: 10000 }} >
        <div class="col1">
          <div id="square"></div>
          <p>fly</p>
        </div>

        <div class="col2">
          <div id="square"></div>
          <p>fly</p>
        </div>

        <div class="col3">
          <div id="square"></div>
          <p>fly</p>
        </div>
      </div>




<!-- 
  <div>
    <div use:inview={options2} on:change={handleChange2}>
      <div 
        class:inViewExample2={isInView2}
        class:down={scrollDirection === 'down'}
        class:top={scrollDirection === 'up'}>
        

        <div class="col1">
          <img src="resider-favicon.png" alt="shape1" width="40" height="40">
          <p>text</p>
        </div>

        <div class="col2">
          <img src="resider-favicon.png" alt="shape2" width="40" height="40">
          <p>text</p>
        </div>

        <div class="col3">
          <img src="resider-favicon.png" alt="shape3" width="40" height="40">
          <p>text</p>
        </div>
      </div>
    </div>
  </div> -->

  <Spacer m=500 d=500 />

  




<style>
  * {
    font-family: "Gilroy", "Open Sans", -apple-system;
    overflow-x: hidden;
    padding: 0;
    margin: 0;
  }

  .typeDesktop {
    height: 144px
  }

  .typeMobile{
    height: 90px
  }


  .inViewExample2 {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
    align-items: flex-start;
  }

 

  .up {
    transform: translate3d(0px, 0px, 0px) scale(0,0)
  }

  .down{
    transform: translate3d(0px, 0px, 0px) scale(0,0)
    
  }

  #square {
  width: 100px;
  height: 100px;
  background: #366ca5;
}
  
  
  .inViewExample {
    height: 100px;
  }
  .animate {
    font-size: 30px;
    transition-duration: 3s;
    transition-property: font-size;
  }

  .animateFromBottom {
    background-color: red;
    color: white;
    font-size: 10px;
    transition-duration: 3s;
    transition-property: font-size;
  }

  .animateFromTop {
    background-color: #366ca5;
    color: white;
    font-size: 30px;
    transition-duration: 3s;
    transition-property: font-size;
  }

  .container {
    display: flex;
    flex-direction: column;
    align-content: center;
    align-items: center;
    text-align: center;
  }

  .desktop-header {
    width: 100%;
    height: 72px;
    box-shadow: 0px 2px 6px rgba(0, 0, 0, 0.12);
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .lottie {
    display: flex;
    flex-direction: column;
    text-align: center;
    align-content: center;
    align-items: center;
  }

  .header-logo {
    margin-left: 28px;
    margin-top: 24px;
  }

  .btn-primary {
    background-color: #366ca5;
    color: white;
    border: none;
    width: 153px;
    height: 48px;
    font-family: "Gilroy", "Open Sans", -apple-system;
    font-weight: 600;
    font-size: 14px;
    line-height: 20px;
    letter-spacing: 0.2px;
    border-radius: 4px;
    margin: 12px;
    cursor: pointer;
  }

  h1 {
    font-size: 36px;
    font-weight: 700;
    line-height: 48px;
    letter-spacing: 0.1px;
    color: #3c4043;
    max-width: 326px;
  }

  .h1-desktop {
    font-size: 64px;
    font-weight: 700;
    line-height: 76px;
    letter-spacing: 0.1px;
    color: #3c4043;
    max-width: 531px;
  }

  h2 {
    font-weight: 700;
    font-size: 28px;
    line-height: 38px;
    letter-spacing: 0.1px;
    color: #3c4043;
  }

  p {
    font-size: 18px;
    line-height: 30px;
    font-weight: 400;
    color: #606367;
    max-width: 326px;
    text-align: center;
  }

  .p-desktop {
    font-size: 24px;
    line-height: 36px;
    font-weight: 400;
    color: #606367;
    max-width: 326px;
    text-align: center;
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
    font-family: "Gilroy";
    font-style: normal;
    font-weight: 400;
    font-display: swap;
    src: local("Gilroy"), local("Gilroy-Regular"),
      url("./regular.woff2") format("woff2"),
      url("./regular.woff") format("woff");
  }

  @font-face {
    font-family: "Gilroy";
    font-style: normal;
    font-weight: 500;
    font-display: swap;
    src: local("Gilroy Medium"), local("Gilroy-Medium"),
      url("./medium.woff2") format("woff2"), url("./medium.woff") format("woff");
  }

  @font-face {
    font-family: "Gilroy";
    font-style: normal;
    font-weight: 600;
    font-display: swap;
    src: local("Gilroy SemiBold"), local("Gilroy-SemiBold"),
      url("./semi-bold.woff2") format("woff2"),
      url("./semi-bold.woff") format("woff");
  }

  @font-face {
    font-family: "Gilroy";
    font-style: italic;
    font-weight: 400;
    font-display: swap;
    src: local("Gilroy Italic"), local("Gilroy-Italic"),
      url("./italic-regular.woff2") format("woff2"),
      url("./italic-regular.woff") format("woff");
  }

  @font-face {
    font-family: "Gilroy";
    font-style: italic;
    font-weight: 500;
    font-display: swap;
    src: local("Gilroy Medium Italic"), local("Gilroy-MediumItalic"),
      url("./italic-medium.woff2") format("woff2"),
      url("./italic-medium.woff") format("woff");
  }
</style>
