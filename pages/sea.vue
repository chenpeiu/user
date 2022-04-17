<template>
  <div class="seapage">
    <div class="topbar3 w-screen h-[500px] bg-center bg-cover flex justify-center items-center" style="background-image:url(https://static.pexels.com/photos/8807/sopot.jpg)">
      <div class="wrap w-2/5 text-center text-white font-bold">
        <div class="text-2xl text-white/80">城市向海的一隅</div>
        <NuxtLink to="/">
          <div class="text-[60px]">餘光，啟航</div>
        </NuxtLink>
      </div>
    </div>
    <div class="section_ask">
      <div class="wrap w-3/5 m-auto p-5 py-12 flex flex-col justify-center items-center">
        <div class="text text-center mb-3">
          <div class="text-3xl font-bold text-slate-800">最後一次看見海是什麼時候呢?</div>
          <div class="text-slate-600/50 py-2">上一次看見的海，仍然藍的深邃</div>
        </div>
        <div class="items w-full flex text-center ">
          <div class="item w-1/3 flex flex-col items-center">
            <div class="pic mb-3 ">
              <img src="https://www.timeforkids.com/wp-content/uploads/2021/07/turtle1-1.jpg" alt="" class=" w-[170px] h-[170px] rounded-full shadow-lg ">
            </div>
            <div class="tex text-slate-800" >
              <div >一望無際的海</div>
              <div >就像沒有邊際的人生</div>
            </div>
          </div>
          <div class="item w-1/3 flex flex-col items-center">
            <div class="pic mb-3">
              <img src="http://wallup.net/wp-content/uploads/2016/01/198527-nature-landscape-sea-grass.jpg" alt="" class=" w-[170px] h-[170px] rounded-full shadow-lg ">
            </div>
            <div class="tex text-slate-800" >
              <div>一望無際的海</div>
              <div>就像沒有邊際的人生</div>
            </div>
          </div>
          <div class="item w-1/3 flex flex-col items-center">
            <div class="pic mb-3">
              <img src="https://www.madamagazine.com/wp-content/uploads/2017/05/Emerald-Sea-3.jpg" alt="" class=" w-[170px] h-[170px] rounded-full shadow-lg ">
            </div>
            <div class="tex text-slate-800" >
              <div>一望無際的海</div>
              <div>就像沒有邊際的人生</div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="section_story  bg-gray-200">
      <div class="wrap w-3/5 m-auto flex flex-col items-center py-10">
        <div class="top text-center">
          <fa :icon='["fas" , "water"]' class="text-5xl text-slate-600 py-2"/>
          <div class="text-3xl font-bold text-slate-800">海洋的故事</div>
          <div class="text-slate-600/50 py-2 mb-2">要成為海，定義上其實蠻不容易的</div>
        </div>
        <div class="items flex">
          <div class="item text-center mx-5">
            <div class="text-2xl font-bold text-slate-800">3.5525億平方公里</div>
            <p class="text-sm text-gray-800/80 mt-2">海洋即「海」和「洋」的總稱。地球的71%的面積被海洋覆蓋。總面積大約為3億5525萬5千平方公里。一般人們將這些占地球很大面積的鹹水水域稱為「洋」，大陸邊緣的水域被稱為「海」。</p>
          </div>
          <div class="item text-center mx-5">
            <div class="text-2xl font-bold text-slate-800">3.5%</div>
            <p class="text-sm text-gray-800/80 mt-2">海水所含的鹽分各處不同，平均約為3.5%。這些溶解在海水中的無機鹽，最常見的是氯化鈉，即日用的食鹽。有些鹽來自海底的火山，但大部分來自地殼的岩石。</p>
          </div>
        </div>
      </div>
    </div>
    <div class="section_deep flex">
      <div class="item w-1/2 py-32 text-white bg-center " style="background-image:url(https://i.pinimg.com/originals/15/c0/76/15c0768b10265a32ca27a6027ff56f60.jpg)" >
        <div class="tex text-center">
          <div class="text-3xl font-bold">深海的生物們</div>
          <div class="tex2 text-white py-2 ">目前科學家探索的深海面貌不到1%</div>
        </div>  
      </div>
      <div class="item w-1/2 py-32 text-white bg-center" style="background-image:url(https://www.wired.com/images_blogs/wiredscience/2013/06/chair15-cc2.jpg)">
        <div class="tex text-center">
          <div class="text-3xl font-bold">人造物的侵襲</div>
          <div class="tex2 text-white py-2">每年有數萬噸的人造物沉入黑暗的海</div>
        </div>
      </div>
    </div>
    <div class="bottombar py-20 flex justify-center items-center bg-sky-900 text-white">
      <div class="tex text-center">
        <div class="text-3xl font-bold">你對海有什麼想像呢?</div>
        <div class="py-2 text-slate-300/50">說說關於你，關於海洋，關於世界的故事</div>
        <input type="text" class="focus:outline-none rounded-md bg-transparent border border-white px-2">
      </div>
    </div>

  </div>
</template>
<style lang="sass">
  body
    min-height: 100px
    min-width: 1200px
    height: 1200px
    width: 100vw
    box-sizing: border-box
    padding: 0
    margin: 0
  .section_deep
    .item
      background-size: 100% auto
      transition: 1s
      position: relative
      .tex .tex2
        opacity: 0.4
        transition: 1s
      &:hover
        background-size: 120% auto
        .tex .tex2
          opacity: 1
      // .tex
      //   &::before
      //     content:""
      //     position: absolute
      //     top: 0
      //     right: 0
      //     bottom: 0
      //     left: 0
      //     background-color: rgba(0,0,0,.3)
      //     display: flex
      //     justify-content: center
      //     align-items: center
      //     z-index: 0



</style>

<script>

</script>