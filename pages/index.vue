<template>
  <div class="userpage flex h-screen w-screen ">
    <div class="sidebar_left h-screen w-1/6 bg-cyan-800 text-white px-4 overflow-y-auto hidden lg:block">
      <div class="logo text-center text-2xl py-5">
        <!-- <fa :icon='["fas" , "star-of-david"]' /> -->
        <span class="font-semibold font-['Lobster'] tracking-widest">VueBoard</span>
      </div>
      <ul class="">General
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30" @click="isactive=1" :class="{active:isactive==1}">
              <fa :icon='["fas" , "heart"]' class="pr-3"/>
              <span>Dashboard</span>
            </li>
          </a>
      </ul>
      <ul class="">Excampls
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30" @click="isactive=2" :class="{active:isactive==2}">
              <fa :icon='["fas" , "chess-queen"]' class="pr-3"/>
              <span>UI Element</span>
            </li>
          </a>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30" @click="isactive=3" :class="{active:isactive==3}">
              <fa :icon='["fas" , "flag"]' class="pr-3"/>
              <span>Tables</span>
            </li>
          </a>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30" @click="isactive=8" :class="{active:isactive==8}">
              <fa :icon='["fas" , "cloud-arrow-down"]' class="pr-3"/>
              <span>Forms</span>
            </li>
          </a>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30" @click="isactive=4" :class="{active:isactive==4}">
              <fa :icon='["fas" , "comment-sms"]' class="pr-3"/>
              <span>Cards</span>
            </li>
          </a>
          <NuxtLink to="/product">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30" @click="isactive=5" :class="{active:isactive==5}">
              <fa :icon='["fas" , "cubes"]' class="pr-3"/>
              <span>Product</span>
            </li>
          </NuxtLink>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30" @click="isactive=6" :class="{active:isactive==6}">
              <fa :icon='["fas" , "elevator"]' class="pr-3"/>
              <span>Github</span>
           </li>
          </a>
      </ul>
      <ul class="">About        
        <a href="">
          <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30" @click="isactive=7" :class="{active:isactive==7}">
            <fa :icon='["fas" , "file-circle-check"]' class="pr-3"/>
            <span>Model</span>
          </li>  
        </a>
      </ul>
    </div>
    <div class="sidebar_right h-screen flex-col bg-slate-200 w-full lg:w-5/6">
      <div class="topbar w-full h-[8%] flex-none border-b-4 border-cyan-800 ">
        <div class="wrap w-[95%] h-full m-auto relative">
          <div class="form flex items-center absolute top-1/2 -translate-y-1/2 px-3 rounded-md border-2 border-cyan-800 ">
            <fa :icon='["fas" , "magnifying-glass"]' class="text-slate-500 pr-2" />
            <input type="text" class="bg-transparent focus:outline-none py-1 text-slate-600" v-model="searchitem"/>
          </div>
          <div class="usericon flex items-center absolute top-1/2 -translate-y-1/2 right-0">
            <div class="icon px-4">
              <fa :icon='["fas" , "bell"]' class="text-cyan-800 text-[25px]"/>
            </div>
            <div class="pic bg-white w-10 h-10 rounded-full overflow-hidden border-2 border-cyan-800">
              <img class="max-w-[130%] mt-[5px] -ml-[6px]" src="https://st.depositphotos.com/1269204/1219/i/600/depositphotos_12196477-stock-photo-smiling-men-isolated-on-the.jpg" alt="">
            </div>
          </div>
        </div>
      </div>
      <div class="midbar h-[87%] overflow-y-auto flex-col">
        <div class="wrap m-auto py-[20px] w-[95%] relative">
          <div class="addbar px-3 lg:w-[26%] flex items-center bg-cyan-800 absolute left-1/2 -translate-x-1/2 top-[20px] rounded-lg overflow-hidden min-w-max w-full">
            <label for="adduser" class="pr-3 bg-cyan-800 text-gray-200/90">New User</label>
            <input type="text" id="adduser" class="focus:outline-none pr-2 py-1 bg-cyan-800 text-white " autocomplete="off" v-model="newname" @keydown.enter="adduser"/> 
            <fa :icon='["fas" , "circle-plus"]' class="px-3 bg-cyan-800 text-gray-200/80 cursor-pointer absolute right-0 " @click="adduser"/>
          </div>
          <div class="items flex flex-col my-5 mt-10 lg:flex-row ">
            <div class="item lg:w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative my-3 ">
              <div class="icon">
                <fa :icon='["fas" , "circle-user"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2 text-pink-500/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider ">{{userapi.length}}</div>
                <div class="text-slate-500 font-semibold">New Users</div>
              </div>
            </div>
            <div class="item lg:w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative m-0 lg:m-3">
              <div class="icon">
                <fa :icon='["fas" , "circle-up"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2 text-rose-600/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider">728</div>
                <div class="text-slate-500 font-semibold">Total Orders</div>
              </div>
            </div>
            <div class="item lg:w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative my-3 ">
              <div class="icon">
                <fa :icon='["fas" , "circle-xmark"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2  text-orange-500/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider">63</div>
                <div class="text-slate-500 font-semibold">Available Products</div>
              </div>
            </div>
          </div>
          <div class="tablebar">
            <table class="w-full rounded-xl bg-white text-center shadow overflow-hidden">
              <thead class="bg-gray-300 ">
                <tr>
                  <th class="border-b-2 font-bold text-slate-600 py-3">ID</th>
                  <th class="border-b-2 font-bold text-slate-600">User</th>
                  <th class="border-b-2 font-bold text-slate-600">Status</th>
                  <th class="border-b-2 font-bold text-slate-600">Role</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="user in showuser" :key="user.id">
                  <td class="text-slate-500 border-b border-gray-300 py-5">{{user.id.slice(0,2)}}</td>
                  <td class="text-slate-500 border-b border-gray-300 ">{{user.username}}</td>
                  <td class="text-slate-500 border-b border-gray-300 ">Indianapolis</td>
                  <td class="text-slate-500 border-b border-gray-300  tracking-[1em]">
                    <fa :icon='["fas" , "pen-to-square"]' class="text-teal-600 cursor-pointer mr-2"/>
                    <fa :icon='["fas" , "trash-can"]' @click="deluser(user.id)" class="text-rose-800 cursor-pointer"/>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <div class="footer w-full h-[5%] fixed bottom-0 relative hidden md:block">
        <div class="absolute top-1/2 -translate-y-1/2 px-8 text-slate-800/80 text-sm">© Copyright 2022</div>
      </div>
    </div>
    <div v-if="isdone==false" class="fixed w-screen h-screen bg-gray-500/50">
      <div class="absolute left-1/2 top-1/2 -tranlate-x-1/2 -tranlate-y-1/2">
        <fa :icon='["fas" , "spinner"]' class="animate-spin text-white text-lg" />
      </div>
    </div>
  </div>
</template>
<style lang="sass">
  body
    min-height: 100px
    min-width: 1200px
  .active
    background-color: rgba(229,231,235,.3)
    color: #fff
    border-left: 6px solid #fff

</style>
<script>
import axios from 'axios'
export default {
  async fetch(){
    await axios.get("https://fiilm-back.herokuapp.com/user")
                .then( res => {
                  this.userapi=res.data
                  this.isdone=true
                  console.log(this.userapi)
                })
  },
  data(){
    return {
      searchitem:'',
      newname: '',
      userapi:[],
      isdone: false,
      isactive: '',
    }
  },
  computed:{
    showuser(){
      return this.userapi.filter( item => item.username.match(this.searchitem))
    },
  },
  methods:{
    async adduser(){
      if (this.newname!=""){
        await axios.post("https://fiilm-back.herokuapp.com/user",{
          "username": this.newname
        })
        this.isdone=false
        this.newname=""
        await axios.get("https://fiilm-back.herokuapp.com/user")
                    .then( res => this.userapi=res.data)
        this.isdone=true
      }
    },
    async deluser(id){
      await axios.delete("https://fiilm-back.herokuapp.com/user?user_id="+id)
      this.isdone=false
      await axios.get("https://fiilm-back.herokuapp.com/user")
                  .then(res=> this.userapi=res.data)
      this.isdone=true
    }
  }
}
</script>
