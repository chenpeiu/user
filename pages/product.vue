<template>
  <div class="userpage flex h-screen w-screen ">
    <div class="sidebar h-screen flex-col bg-slate-200 w-full" :class="{additemright:additem}">
      <div class="topbar2 w-full h-[8%] border-b-3 border-green-800 shadow-md shadow-slate-500/30 ">
        <div class="wrap w-[95%] h-full m-auto relative">
          <NuxtLink to="/">
            <div class="logo w-[50px] h-[50px] pt-1">
              <img src="https://upload.wikimedia.org/wikipedia/zh/thumb/b/bf/Starbucks_Coffee.svg/1200px-Starbucks_Coffee.svg.png" alt="" class="w-full">
            </div>
          </NuxtLink>
          <!-- <div class="form flex items-center absolute top-1/2 -translate-y-1/2 px-3 rounded-md border-2 border-green-800 ">
            <fa :icon='["fas" , "magnifying-glass"]' class="text-slate-500 pr-2" />
            <input type="text" class="bg-transparent focus:outline-none py-1 text-slate-600" v-model="searchitem"/>
          </div> -->
        </div>
      </div>
      <div class="midbar h-[87%] overflow-y-auto">
        <div class="wrap m-auto py-[20px] w-[95%] relative">
          <button class="addbar p-3 px-5 bg-green-800 text-white absolute left-1/2 -translate-x-1/2 top-[20px] rounded-lg overflow-hidden min-w-max shadow-sm shadow-slate-300" @click="additem=true"> 
            Add New Product
          </button>
          <div class="items flex flex-col my-5 mt-14 lg:flex-row ">
            <div class="item lg:w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative m-3  min-w-max">
              <div class="icon mr-3">
                <fa :icon='["fas" , "basket-shopping"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2 text-pink-500/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider ">{{totalitem}}</div>
                <div class="text-slate-500 font-semibold">Products</div>
              </div>
            </div>
            <div class="item lg:w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative m-3  min-w-max">
              <div class="icon mr-3">
                <fa :icon='["fas" , "cart-shopping"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2 text-rose-600/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider">{{expectincome}}
                  <span class="text-base">TWD</span>
                </div>
                <div class="text-slate-500 font-semibold">Total Income</div>
              </div>
            </div>
            <div class="item lg:w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative m-3  min-w-max">
              <div class="icon mr-3">
                <fa :icon='["fas" , "circle-check"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2  text-orange-500/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider">{{availableitem}}</div>
                <div class="text-slate-500 font-semibold">Available Products</div>
              </div>
            </div>
          </div>
          <div class="tablebar">
            <table class="w-full rounded-xl bg-white text-center shadow overflow-hidden">
              <thead class="bg-green-900/50 ">
                <tr>
                  <th class="border-b-2 font-bold text-slate-800 py-3">Enable</th>
                  <th class="border-b-2 font-bold text-slate-800">Image</th>
                  <th class="border-b-2 font-bold text-slate-800 cursor-pointer" @click="changesort('content')">Item</th>
                  <th class="border-b-2 font-bold text-slate-800 cursor-pointer" @click="changesort('category')">Category</th>
                  <th class="border-b-2 font-bold text-slate-800 cursor-pointer" @click="changesort('origin_price')">Price</th>
                  <th class="border-b-2 font-bold text-slate-800"></th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="product in sortarray" :key="product.id">
                  <td class="text-slate-500 border-b border-gray-300 py-5">
                    <div v-if="product.enabled==true" ><fa :icon='["fas" , "circle-check"]' class="text-green-600 text-2xl"/></div>
                    <div v-if="product.enabled==false" ><fa :icon='["fas" , "circle-xmark"]' class="text-rose-500 text-2xl"/></div>
                  </td>
                  <td class="text-slate-500 border-b border-gray-300 w-1/6 ">
                    <div class="pic w-2/3 bg-green-200 m-auto">
                      <img :src="product.imageUrl" alt="" class="w-full">
                    </div>                    
                  </td>
                  <td class="text-slate-500 border-b border-gray-300 w-1/6">
                    <div class="text-lg">{{product.title}}</div>
                    <div class="text-sm text-slate-500/50">{{product.content}}</div>
                  </td>
                  <td class="text-slate-500 border-b border-gray-300 ">{{product.category}}</td>
                  <td class="text-slate-500 border-b border-gray-300">
                    <div class="text-center">
                      <div>售價：{{product.price}}/{{product.unit}}</div>
                      <div>原價：{{product.origin_price}}/{{product.unit}}</div>
                    </div>
                  </td>
                  <td class="text-slate-500 border-b border-gray-300  w-1/8">
                    <div>
                      <fa :icon='["fas" , "magnifying-glass-plus"]' class="text-green-700 cursor-pointer mr-3" @click="showdetail(product.id)"/>
                      <fa :icon='["fas" , "trash-can"]' @click="delitem(product.id)" class="text-rose-800 cursor-pointer"/>
                    </div>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <div class="footer w-full h-[5%] fixed bottom-0 relative hidden md:block">
        <div class="absolute top-1/2 -translate-y-1/2 px-8 text-slate-800/80 text-sm"></div>
      </div>
    </div>
    <div v-if="isdone==false" class="fixed w-screen h-screen bg-gray-500/50">
      <div class="absolute left-1/2 top-1/2 -tranlate-x-1/2 -tranlate-y-1/2">
        <fa :icon='["fas" , "spinner"]' class="animate-spin text-white text-lg" />
      </div>
    </div>
    <div v-if="additem==true" class="fixed top-0 right-0 left-0 bottom-0 bg-gray-200/30 backdrop-blur-[2px] border-2 border-green-900" @click="additem=false"></div>
    <div v-if="additem==true" >
      <div class="p-8 pt-14 fixed top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-1/2 h-[65%] bg-green-800 rounded-xl drop-shadow-xl  overflow-auto" >
        <div class="wrap pt-3 absolute top-1/2 -translate-y-1/2 w-[90%] border-b-4 border-dashed border-green-900 ">
          <div class="add">
            <div class="mb-2.5">
              <label for="name" class="inline-block w-1/5 text-white text-xl flex-row items-center">Name:</label>
              <input type="text" id="name" class="w-3/5 w-3/5 p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800 " v-model="newproduct.title"> 
            </div>
            <div class="mb-2.5">
              <label for="category" class="inline-block w-1/5 text-white text-xl flex-row items-center">Category:</label>
                <select name="Category" class="bg-green-200 rounded-md p-1 ml-2 text-green-900"  v-model="newproduct.category"> 
                  <option value=" " disabled selected> 選擇商品種類</option>
                  <option value="麵包">麵包</option>
                  <option value="輕食">輕食</option>
                  <option value="蛋糕">蛋糕</option>
                  <option value="飲品">飲品</option>
                  <option value="禮品">禮品</option>
                </select>
            </div>
            <div class="mb-2.5">
              <label for="content" class="inline-block w-1/5 text-white text-xl flex-row items-center">EglishName:</label>
              <input type="text" id="content" class="w-3/5 p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800" v-model="newproduct.content"> 
            </div>
            <div class="mb-2.5">
              <label for="description" class="inline-block w-1/5 text-white text-xl flex-row items-center">Description:</label>
              <input type="text" id="description" class="w-3/5 p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800" v-model="newproduct.description"> 
            </div>
            <div class="mb-2.5">
              <label for="imageUrl" class="inline-block w-1/5 text-white text-xl flex-row items-center">ImageUrl:</label>
              <input type="text" id="imageUrl" class="w-3/5 p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800" v-model="newproduct.imageUrl[0]"> 
            </div>
            <div class="mb-2.5">
              <label class="inline-block w-1/5 text-white text-xl flex-row items-center">Enabled:</label>
              <input type="radio" :value=true name="Enabled" class="p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800" v-model="newproduct.enabled"> True
              <input type="radio" :value=false name="Enabled" class="p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800" v-model="newproduct.enabled"> False
            </div>
            <div class="mb-2.5">
              <label for="origin_price" class="inline-block w-1/5 text-white text-xl flex-row items-center">Origin_price:</label>
              <input type="text" id="origin_price" class="w-3/5 p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800" v-model.number="newproduct.origin_price"> 
            </div>
            <div class="mb-2.5">
              <label for="price" class="inline-block w-1/5 text-white text-xl flex-row items-center">Price:</label>
              <input type="text" id="price" class="w-3/5 p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800" v-model.number="newproduct.price"> 
            </div>
            <div class="mb-2.5">
              <label for="unit" class="inline-block w-1/5 text-white text-xl flex-row items-center">Unit:</label>
              <input type="text" id="unit" class="w-3/5 p-1 bg-transparent border-2 border-white rounded-md ml-2 text-slate-800" v-model="newproduct.unit"> 
            </div>
          </div>
          <div class="check block w-full text-right " @click="additem=false & addproduct()">
            <button>
              <fa :icon='["fas","cart-plus"]' class=" text-4xl p-3 pb-0 text-white translate-x-0 hover:text-green-900 duration-150 hover:translate-x-3"/>
            </button>
          </div>
        </div>
      </div>
    </div>
    <div v-if="isshowdetail==true" class="fixed top-0 right-0 left-0 bottom-0 bg-slate-800/50" @click="isshowdetail=false"></div>
    <div v-if="isshowdetail==true" class="detail p-3 flex w-1/2 rounded-lg bg-green-900 fixed top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 ">
      <div class="w-1/2 text-left text-white"> 
        <div class="text-lg leading-10 mb-2 ">產品名稱：
          <input type="text" class="bg-green-400/20 px-2 rounded-md text-white" v-model="current.title">
        </div>
        <div class="text-lg leading-10 mb-2">產品分類：
          <input type="text" class="bg-green-400/20 px-2 rounded-md text-white" v-model="current.category">
        </div>
        <div class="text-lg leading-10 mb-2 ">英文名稱：
          <input type="text" class="bg-green-400/20 px-2 rounded-md text-white " v-model="current.content">
        </div>
        <div class="text-lg leading-10 mb-2 ">產品說明：
          <input type="text" class="bg-green-400/20 px-2 rounded-md text-white" v-model="current.description">
        </div>
        <div class="text-lg leading-10 mb-2 ">上架狀態：
          <input type="radio" :value=true name="Enabled" class="p-1 ml-2 " v-model="current.enabled"> True
          <input type="radio" :value=false name="Enabled" class="p-1 ml-2 " v-model="current.enabled"> False
        </div>
        <div class="text-lg leading-10 mb-2 ">產品原價：
          <input type="text" class="bg-green-400/20 px-2 rounded-md text-white" v-model="current.origin_price">
        </div>
        <div class="text-lg leading-10 mb-2 ">產品售價：
          <input type="text" class="bg-green-400/20 px-2 rounded-md text-white" v-model="current.price">
        </div>
        <div class="text-lg leading-10 mb-2 ">產品售價：
          <input type="text" class="bg-green-400/20 px-2 rounded-md text-white" v-model="current.unit">
        </div>
        <button class="w-[89%] rounded-md py-1 mt-2 bg-slate-100 text-center text-green-900 text-lg hover:bg-gray-300" @click="updateproduct(current.id)">
          <fa :icon='["fas" , "circle-check"]' class="" />
        </button>
      </div>  
      <div class="pic w-1/2 overflow-hidden ">
        <img :src=current.imageUrl alt="" class="rounded-md">
      </div>
    </div>
  </div>
</template>
<style lang="sass">

  body
    min-height: 100px
    max-height: 560px
    min-width: 1200px
  .active
    background-color: rgba(229,231,235,.3)
    color: #fff
    border-left: 6px solid #fff
  .additemright
    width: 100vw

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
      sorttype:"",
      issort: true,
      newproduct:{
        title: "",
        category: "",
        content: "",
        description: "",
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
    },
    sortarray(){
      try{
        if(this.issort==true){
          let result=this.productapi.data.sort((a,b)=>a[this.sorttype]-b[this.sorttype])
          console.log(result)
          return result
        }
        else{
          let result=this.productapi.data.sort((a,b)=>b[this.sorttype]-a[this.sorttype])
          console.log(result)
          return result
        }
      }
      catch{
        return this.productapi.data
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
      this.newproduct.description=""
      this.newproduct.imageUrl=[]
      this.newproduct.enabled= true
      this.newproduct.origin_price=null
      this.newproduct.price=null
      this.newproduct.unit=""
    },
    async updateproduct(id){
      let data=this.current
      await axios({
        method: 'patch',
        url: "https://course-ec-api.hexschool.io/api/4e36516d-bd95-49e6-9be0-881d82838857/admin/ec/product/"+id,
        data: data,
        headers: header
      })
      await this.refresh()
      this.isshowdetail=false
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
    },
    changesort(type){
      if (this.sorttype==type){
        this.issort=!this.issort
      }
      else{
        this.issort=!this.issort
        this.sorttype=type
      }
    }
  }
}
</script>