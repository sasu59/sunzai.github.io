<template>
  <div id="app">
    <!-- <router-view></router-view> -->
    <!-- <div class="bigGreen">
      <div class="card">
        <div style="height:100px">
          <img class="img1" src="./img/5.jpg"/>
          <div>张三</div>
          <div>
            <el-input v-model="textVal" round style="width: 50%;" placeholder="请填写待完成事项"/>
            <el-button round type="success" style="width:30%" @click="adding">新增</el-button>
          </div>
          <div style="margin-top: 30px">
            <el-tag v-for="(item,index) in list" :key="index">
              <el-tag class="cards" shadow="always">
                {{item}}
              </el-tag>
              <el-button @click="deleteNow(item, $index)" style="height: 30px;">删除</el-button>
            </el-tag>
          </div>
        </div>
        
      </div>
      
    </div> -->
  

    <div>
      <el-menu
        mode="horizontal"
        default-active="1"
        class="el-menu-vertical-demo"
        @open="handleOpen"
        @close="handleClose"
        background-color="#545c64"
        text-color="#fff"
        active-text-color="#ffd04b">
        <el-submenu index="1">
          <template slot="title">
            <i class="el-icon-user-solid"></i>
            <span>个人简介</span>
          </template>
          <el-menu-item index="1-7" @click="run">选项1</el-menu-item>
          <el-menu-item index="1-8">选项2</el-menu-item>
        </el-submenu>
        <el-submenu index="2">
          <template slot="title">
            <i class="el-icon-video-camera-solid"></i>
            <span>作品简介</span>
          </template>
          <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item index="2-1">选项1</el-menu-item>
            <el-menu-item index="2-2">选项2</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="分组2">
            <el-menu-item index="2-3">选项3</el-menu-item>
            <el-menu-item index="2-4">选项4</el-menu-item>
          </el-menu-item-group>
          <!-- <el-submenu index="2-4">
            <template slot="title">选项4</template>
            <el-menu-item index="2-4-1">选项1</el-menu-item>
          </el-submenu> -->
        </el-submenu>
        <el-submenu index="3">
          <template slot="title">
            <i class="el-icon-scissors"></i>
            <span>好看的剪辑</span>
          </template>
          <el-menu-item-group>
            <template slot="title">分组一</template>
            <el-menu-item index="3-1">选项1</el-menu-item>
            <el-menu-item index="3-2">选项2</el-menu-item>
          </el-menu-item-group>
          <el-menu-item-group title="分组2">
            <el-menu-item index="3-3">选项3</el-menu-item>
          </el-menu-item-group>
          <el-submenu index="3-4">
            <template slot="title">选项4</template>
            <el-menu-item index="3-4-1">选项1</el-menu-item>
          </el-submenu>
        </el-submenu>
      </el-menu>
    </div>
    

  <div>
    <router-view></router-view>
  </div>
    


  </div>
</template>

<script>
//import pdf from '@/components/pdf.vue'

import router from './router';

export default {
    name: "App",
    data() {
        return {
            textVal: "",
            list: []
        };
    },
    //components: {pdf},
    methods: {
        run() {
          this.$router.push("/pdf");
        },
        handleOpen(key, keyPath) {
          console.log(key, keyPath);
        },
        handleClose(key, keyPath) {
          console.log(key, keyPath);
        }
        // adding(){
        //   const str = this.textVal
        //   this.list.unshift(str)
        //   this.textVal = ''
        // },
        // deleteNow(item,index){
        //   this.run()
        //   this.$confirm('此操作将永久删除, 是否继续?', '提示', {
        //       confirmButtonText: '确定',
        //       cancelButtonText: '取消',
        //       type: 'warning'
        //     }).then(() => {
        //       this.list.splice(index,1)
        //       });
        //   }
    },
    components: { router }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.bigGreen{
  height: 900px;
  background-color: aquamarine;
  display: flex;
  align-items: center;    /* 垂直居中 */
  justify-content: center;  /* 水平居中 */
}
.card{
  width: 400px;
  height: 600px;
  background-color: cadetblue;
  border-radius: 10%;
}
.img1{
  width: 70px;
  height: 70px;
  margin-top: 20px;
  border-radius: 50%;
}
.cards{
  width: 200px;
  height: 30px;
  background-color: gray;
  text-shadow: 2px;

}
.booter{
  bottom: 0px;
}
::v-deep .el-aside .el-menu{
  border-right:none;
}
</style>
