<template>
  <div class="userpage flex h-screen w-screen overflow-hidden">
    <div class="sidebar_left h-screen w-1/6 bg-cyan-800 text-white px-4 overflow-y-auto hidden lg:block">
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
    <div class="sidebar_right h-screen flex-col bg-slate-200 w-full lg:w-5/6">
      <div class="topbar w-full h-[8%] flex-none border-b-4 border-cyan-800 ">
        <div class="wrap w-[95%] h-full m-auto relative">
          <div class="form flex items-center absolute top-1/2 -translate-y-1/2 px-3 rounded-md border-2 border-cyan-800 ">
            <fa :icon='["fas" , "magnifying-glass"]' class="text-slate-500 pr-2"/>
            <input type="text" class="bg-transparent focus:outline-none py-1 text-slate-600"/>
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
      <div class="midbar h-[87%] overflow-y-auto">
        <div class="wrap m-auto py-[20px] w-[95%]">
          <div class="text">
            <span class="text-gray-500">Dashboard</span>
            <fa :icon='["fas" , "angle-right"]' class="px-2 text-cyan-800"/>
          </div>
          <div class="items flex flex-col my-5 lg:flex-row ">
            <div class="item w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative m-3  min-w-max ">
              <div class="icon">
                <fa :icon='["fas" , "circle-user"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2 text-pink-500/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider ">1287.2</div>
                <div class="text-slate-500 font-semibold">New Users</div>
              </div>
            </div>
            <div class="item w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative m-3  min-w-max">
              <div class="icon">
                <fa :icon='["fas" , "circle-up"]' class="pr-[30px] text-[70px] absolute top-1/2 -translate-y-1/2 text-rose-600/80"/>
              </div>
              <div class="tex ml-[90px]">
                <div class="number text-slate-700 font-extrabold text-[30px] font-['Lobster'] tracking-wider">728</div>
                <div class="text-slate-500 font-semibold">Total Orders</div>
              </div>
            </div>
            <div class="item w-1/3 flex bg-white rounded-xl p-3 pl-5 shadow relative m-3  min-w-max">
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
                <tr v-for="user in userapi" :key="user.id">
                  <td class="text-slate-500 border-b border-gray-300 py-5">{{user.id.slice(0,2)}}</td>
                  <td class="text-slate-500 border-b border-gray-300 ">{{user.username}}</td>
                  <td class="text-slate-500 border-b border-gray-300 ">Indianapolis</td>
                  <td class="text-slate-500 border-b border-gray-300  tracking-[1em]">
                    <fa :icon='["fas" , "pen-to-square"]' class="text-teal-600 cursor-pointer mr-2"/>
                    <fa :icon='["fas" , "trash-can"]' class="text-rose-800 cursor-pointer"/>
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
    // await axios.post("https://fiilm-back.herokuapp.com/user",{
    //             "username": this.newname
    //             })
    // await axios.delete("https://fiilm-back.herokuapp.com/user",{
    //             data:{"username":123}
    //             })
    await axios.get("https://fiilm-back.herokuapp.com/user")
                .then( res => {
                  this.userapi=res.data
                  console.log(this.userapi)
                })
  },
  data(){
    return {
    newname: '456',
    userapi:[]
    }
  }
}
</script>
