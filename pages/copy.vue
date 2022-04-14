<template>
  <div class="copypage w-screen">
    <nav class="fixed h-[50px] w-full text-white flex items-center border-b-2 border-white ">
      <NuxtLink to="/">
        <div class="brand ml-8 text-lg">PRINT</div>
      </NuxtLink>
      <div class="items absolute right-8 flex">
        <div class="px-4 text-sm">引言 INTRO</div>
        <div class="px-4 text-sm" >簡介 ABOUT</div>
        <div class="px-4 text-sm" >故事 STORY</div>
        <div class="px-4 text-sm" >未來 FUTURE</div>
      </div>
    </nav>
    <div class="topbar h-[600px] bg-slate-200 bg-cover bg-fixed ">
      <div class="wrap h-full flex justify-center items-center">
        <div class="txt text-center">
          <div class="text-5xl font-extrabold text-white">印刷術，知識的複製與革命</div>
          <hr class="w-[80px] border-2 border-amber-500 m-auto mt-5">
          <div  class="text-xl pt-2 text-slate-100/50">對人類文化知識的傳播起到了決定性的作用</div>
        </div>
      </div>
    </div>
    <div class="section_ask bg-orange-500 flex items-center ">
      <div class="wrap w-1/2 m-auto flex items-center">
        <div class="pic w-1/2 ">
          <img src="https://www.cup.com.hk/wp-content/uploads/2018/02/sushchnost-izobreteniya-236_o.jpg" alt="" class="mix-blend-multiply">
        </div>
        <div class="tex w/1/3 p-7 text-lg text-white">如果今天沒有印表機，一本書需要花多久產生呢?
        </div>
      </div>
    </div>
    <div class="section_story pt-5 ">
      <div class="wrap w-3/5 m-auto">
        <div class="py-3 text-xl border-b border-slate-500/50 font-semibold">印刷的故事</div>
        <div class="items flex mt-3">
          <div class="item w-1/3">
            <div class="pic h-2/5 overflow-hidden mb-3 drop-shadow-md">
              <img src="https://awiclass.monoame.com/img/web1_print/sec_print_1.jpeg" alt="" class="w-full">
            </div>
            <div class="tex">
              <div class="text-lg font-semibold ">起源</div>
              <p class="text-sm">由中國北宋1040年的畢昇發明。由當時著名科學家沈括的《夢溪筆談》記載保存，完整無遺地包括制字、貯字、排版、拆板和刷印等一整套活字印刷術工序，與後世鉛字排版的原理完全相同。畢昇發明的膠泥活字印刷經過精心設計，反覆試驗才獲得成功。早期活字印刷品的陸續發現和泥活字實證研究成果，證實了畢昇活字印刷術的真實性和科學性，有力地否定了國外學者對畢昇發明活字印刷術的質疑。</p>
            </div>
          </div>
          <div class="item w-1/3 ml-5">
            <div class="pic h-2/5 overflow-hidden mb-3 drop-shadow-md">
              <img src="https://awiclass.monoame.com/img/web1_print/sec_print_2.jpeg" alt="" class="w-full">
            </div>
            <div class="tex">
              <div class="text-lg font-semibold">活字印刷</div>
              <p class="text-sm">世界上最早的雕版印刷是中國發明的。十九世紀末曾有日本學者島田主張中國在6世紀的六朝就有雕版印刷，根據是北齊顏之推《顏氏家訓》有「書本」一詞；又根據明《河汾燕閑錄》中「隋開皇十三年十二月八日敕廢像遺經悉令雕版」一語，認為最晚在隋朝已有雕版印刷。</p>
            </div>
          </div>
          <div class="item w-1/3 ml-5">
            <div class="pic h-2/5 overflow-hidden mb-3 drop-shadow-md">
              <img src="https://www.cup.com.hk/wp-content/uploads/2018/02/sushchnost-izobreteniya-236_o-600x400.jpg" alt="" class="w-full">
            </div>
            <div class="tex"> 
              <div class="text-lg font-semibold">歐洲</div>
              <p class="text-sm">歐洲同中國一樣，最先出現的是雕版印刷，爾後出現的是活字印刷。歐洲人發現中國的活字印刷比雕版印刷效率更高於是很快就把雕版印刷淘汰掉了。關於中國印刷術傳入歐洲的路線，在很多著作中所談的有三條。一條是歐洲的傳教士和旅行家直接把中國的印刷術帶到歐洲；另一條是經由中亞、西亞、北非，最後傳到歐洲；第三條則是由俄國人傳到歐洲其他國家。</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="section_impact bg-black flex text-white h-[300px] ">
      <div class="pic w-2/5 bg-center"></div>
      <div class="text w-3/5 text-center flex flex-col items-center py-2 mx-8">
        <div class="w-full py-2 mb-2 border-b border-white text-xl">印刷對知識傳播的影響</div>
        <div class="icons w-full flex justify-around py-8">
          <div class="icon">
            <fa :icon='["fas" , "copy"]' class="text-3xl mb-1"/>
            <div>快速複製</div>
          </div>
          <div class="icon">
            <fa :icon='["fas" , "handshake-angle"]' class="text-3xl mb-1"/>
            <div>知識傳遞</div>
          </div>
          <div class="icon">
            <fa :icon='["fas" , "file-arrow-down"]' class="text-3xl mb-1"/>
            <div>文化保存</div>
          </div>
        </div>
        <div class="text text-xs pb-8">印刷機的開發使知識的傳播發生了革命性的變化：1469年在威尼斯成立第一家印刷社（即出版社），1500年該城就有印刷廠417家。1476年，威廉·卡克斯頓在英格蘭成立第一家印刷社°在1539年，西班牙人Juan Pablos在墨西哥的墨西哥城。Stephen Day於1628年在美國麻塞諸塞海灣地區建立了北美第一家印刷社，並協助成立了劍橋出版社。</div>
      </div>
    </div>
    <div class="section_cuurent">
      <div class="wrap w-3/5 m-auto my-6">
        <div class="py-3 text-xl border-b border-slate-500/50 font-semibold">現代印刷術</div>
        <div class="item flex items-center mt-3">
          <div class="pic w-1/2">
            <img src="https://awiclass.monoame.com/img/web1_print/new_print.jpeg" alt="" class="w-full">
          </div>
          <div class="text w-1/2 pl-5">
            <div class="mb-3">
              <fa :icon='["fas" , "print"]' class="text-2xl mb-1"/>
              <div class="font-semibold mb-1">電腦印刷</div>
              <p class="text-xs">文件可通過雷射印字機、噴墨印表機或其它電腦印表機。在最近幾年，計算機列印和工業化印刷工藝已經融合在一起，導致數位印刷的發展。在電子技術迅速發展的過程中，印刷進入了電子控制和自動化的時期，電子排版、電子分色、電子雕版廣泛應用，在印刷質量和效率上都得到了巨大提高。計算機的應用繼續將印刷帶入了數字印刷時代，使傳統工藝難於完成的小品種、多變化印刷得以順利實現。</p>
            </div>
            <div>
              <fa :icon='["fas" , "cubes"]' class="text-2xl mb-1"/>
              <div class="font-semibold mb-1">三維列印</div>
              <p class="text-xs">三維列印 是一種製造技術，物體是由三維文件和三維印表機生成。物體製造是通過一層層材料的疊加而列印出來. 在2012年, 一些公司例如Sculpteo或Shapeways提出網上的三維列印解決方案.</p>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="bottom_bar h-[300px] bg-center bg-cover flex justify-center items-center" style="background-image:url(https://awiclass.monoame.com/img/web1_print/print.jpeg)">
      <div class="wrap text-center text-white ">
        <div class="text-xl py-2">想了解更多印刷相關的故事嗎?</div>
        <input type="text" class="border border-white bg-transparent rounded-md focus:outline-none px-2 py-1" placeholder="Email">
        <hr class="w-[80px] border-2 border-amber-600 m-auto mt-5 mb-3">
        <button class="rounded-md bg-amber-800 text-white px-2 py-1 border border-amber-600/50 text-sm">訂閱故事</button>
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
  .topbar
    background-image: url(https://awiclass.monoame.com/img/web1_print/print.jpeg)
  .section_impact
    .pic
      background-image: url(https://awiclass.monoame.com/img/web1_print/map.gif)
      background-size: 100% auto
  



</style>

<script>

import axios from 'axios'
const header={"Authorization": `Bearer 43wG302EwjCySz1DJItW7eqL5gFFZqaQ979V9kSDoIhOkJBYR0D4Xleu3Sqa`}
export default {
  async fetch(){
    await this.refresh()
    this.isdone=true
    // console.log(this.productapi)
  },
  data(){
    return {
      searchitem:'',
      productapi:[],
      isdone: false,
      isactive: 5,
      additem: false,
      isshowdetail: false,
      newproduct:{
        title: "",
        category: "",
        content: "",
        imageUrl: [],
        enabled:  true, 
        origin_price: null,
        price: null,
        unit: "",
      },
      current:{},
    }
  },
  computed:{
    // showuser(){
    //   return this.userapi.filter( item => item.username.match(this.searchitem))
    // },
    expectincome(){
      try{
        let sum=0
        for(let i=0;i<this.productapi.data.length;i++){
          sum+=this.productapi.data[i].price
        }
        return sum
      }
      catch{
        return 0
      }
    },
    totalitem(){
      try{
        return this.productapi.data.length
      }
      catch{
        return 0
      }
    },
    availableitem(){
      try{
        let available=this.productapi.data.filter(item=>item.enabled==true)
        return available.length
      }
      catch{
        return 0
      }
    }
  },
  methods:{
    async refresh(){
      await axios({
        method:'get',
        url: 'https://course-ec-api.hexschool.io/api/4e36516d-bd95-49e6-9be0-881d82838857/admin/ec/products',
        headers:header,
      }).then(res=>this.productapi=res.data)
    },
    async addproduct(){
      this.isdone=false
      let data=this.newproduct
      await axios({
        method:'post',
        url:'https://course-ec-api.hexschool.io/api/4e36516d-bd95-49e6-9be0-881d82838857/admin/ec/product',
        data: data,
        headers: header
      }).then(res=>console.log(res)).catch(err=>console.log(err))
      await this.refresh()
      this.isdone=true
      this.newproduct.title=""
      this.newproduct.category=""
      this.newproduct.content=""
      this.newproduct.imageUrl=[]
      this.newproduct.enabled= true
      this.newproduct.origin_price=null
      this.newproduct.price=null
      this.newproduct.unit=""
    },
    async updateproduct(id){
      this.isshowdetail=false
      this.isdone=false
      
      let data=this.current
      await axios({
        method: 'patch',
        url: "https://course-ec-api.hexschool.io/api/4e36516d-bd95-49e6-9be0-881d82838857/admin/ec/product/"+id,
        data: data,
        headers: header
      })
      await this.refresh()
      this.isdone=true

    },
    async delitem(id){
      this.isdone=false
      await axios({
        method: "delete",
        url: "https://course-ec-api.hexschool.io/api/4e36516d-bd95-49e6-9be0-881d82838857/admin/ec/product/"+id,
        headers: header,
      }),
      await this.refresh()
      this.isdone=true
    },
    showdetail(id){
      this.current=this.productapi.data.find(item=>item.id==id)
      this.isshowdetail=true
    }
  }
}
</script>