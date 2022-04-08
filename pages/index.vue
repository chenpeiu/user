<template>
  <div class="userpage flex h-screen w-full">
    <div class="sidebar_left w-1/6 bg-cyan-800 text-white px-4">
      <div class="logo text-center text-2xl py-5">
        <fa :icon='["fas" , "star-of-david"]' />
        <span class="font-semibold font-['Lobster'] tracking-widest">VueBord</span>
      </div>
      <ul class="">General
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30">
              <fa :icon='["fas" , "heart"]' class="pr-3"/>
              <span>Dashboard</span>
            </li>
          </a>
      </ul>
      <ul class="">Excampls
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30">
              <fa :icon='["fas" , "chess-queen"]' class="pr-3"/>
              <span>UI Element</span>
            </li>
          </a>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30">
              <fa :icon='["fas" , "flag"]' class="pr-3"/>
              <span>Tables</span>
            </li>
          </a>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30">
              <fa :icon='["fas" , "cloud-arrow-down"]' class="pr-3"/>
              <span>Forms</span>
            </li>
          </a>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30">
              <fa :icon='["fas" , "comment-sms"]' class="pr-3"/>
              <span>Cards</span>
            </li>
          </a>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30">
              <fa :icon='["fas" , "cubes"]' class="pr-3"/>
              <span>Blank</span>
            </li>
          </a>
          <a href="">
            <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30">
              <fa :icon='["fas" , "elevator"]' class="pr-3"/>
              <span>Github</span>
           </li>
          </a>
      </ul>
      <ul class="">About        
        <a href="">
          <li class="pl-7 py-3 -mx-4 hover:bg-gray-200/30 ">
            <fa :icon='["fas" , "file-circle-check"]' class="pr-3"/>
            <span>Model</span>
          </li>  
        </a>
      </ul>
    </div>
    <div class="sidebar_right w-5/6 flex-col bg-slate-200">
      <div class="searchbar relative w-full h-[8%] flex-none border-b-4 border-cyan-800 ">
        <div class="form flex items-center absolute top-1/2 -translate-y-1/2 ml-5 px-3 rounded-md border-2 border-cyan-800 ">
          <fa :icon='["fas" , "magnifying-glass"]' class="text-slate-500 pr-2"/>
          <input type="text" class="bg-transparent focus:outline-none py-1 text-slate-600"/>
        </div>
        <div class="usericon flex absolute right-[10px] top-1/2 -translate-y-1/2">
          <div class="icon px-3">
            <fa :icon='["fas" , "bell"]' class="text-slate-800 text-[25px] mt-3"/>
          </div>
          <div class="pic bg-white w-10 h-10 rounded-full overflow-hidden border-2 border-cyan-800">
            <img class="w-full mt-[7px]" src="https://st.depositphotos.com/1269204/1219/i/600/depositphotos_12196477-stock-photo-smiling-men-isolated-on-the.jpg" alt="">
          </div>
        </div>
      </div>
      <div class="midbar h-[87%] overflow-y-scroll">
        <div class="wrap m-auto my-[20px] w-[95%]">
          <div class="text">
            <span class="text-gray-500">Dashboard</span>
            <fa :icon='["fas" , "angle-right"]' class="px-2 text-cyan-800"/>
          </div>
          <div class="items flex my-5">
            <div class="item w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative">
              <div class="icon">
                <fa :icon='["fas" , "circle-user"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2 text-pink-500/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider">1287.2</div>
                <div class="text-slate-500 font-semibold">New Users</div>
              </div>
            </div>
            <div class="item w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative ml-5">
              <div class="icon">
                <fa :icon='["fas" , "circle-up"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2 text-rose-600/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider">728</div>
                <div class="text-slate-500 font-semibold">Total Orders</div>
              </div>
            </div>
            <div class="item w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative ml-5">
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
            <table class="w-full rounded-xl bg-white border-collapse text-center shadow">
              <thead class="">
                <tr>
                  <th class="border border-slate-300 font-bold text-slate-600 py-2">ID</th>
                  <th class="border border-slate-300 font-bold text-slate-600">User</th>
                  <th class="border border-slate-300 font-bold text-slate-600">Status</th>
                  <th class="border border-slate-300 font-bold text-slate-600">Role</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="user in userapi" :key="user.id">
                  <td class="border border-slate-300 text-slate-500 py-3">{{user.id.slice(0,2)}}</td>
                  <td class="border border-slate-300 text-slate-500">{{user.username}}</td>
                  <td class="border border-slate-300 text-slate-500">Indianapolis</td>
                  <td class="border border-slate-300 text-slate-500">Indianapolis</td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
      <div class="footer w-full h-[5%] flex-none fixed bottom-0">
        <div class="absolute top-1/2 -translate-y-1/2 px-8 text-slate-800/80">© Copyright 2022</div>
      </div>
    </div>

  </div>
</template>
<style lang="sass">
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
                  console.log(this.userapi)
                })
  },
  name: 'IndexPage',
  userapi:[]
}
</script>
