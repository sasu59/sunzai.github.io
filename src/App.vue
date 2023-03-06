<template>
  <div id="app">
    <div class="bigGreen">
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
      
    </div>
    <tbody>
      <tr>
        <td>11111111</td>
        <td>
          <input type="checkbox" name="sun" value="111" />
        </td>
      </tr>
    </tbody>
    
  </div>
</template>

<script>
//import pdf from './components/pdf.vue'

export default {
  name: 'App',
  data(){
    return{
      textVal: '',
      list:[

      ]
    }
  },
  //components: {pdf},
  methods:{
    run(){
      $this.$router.push('/pdf')
    },
    adding(){
      const str = this.textVal
      this.list.unshift(str)
      this.textVal = ''

    },
    deleteNow(item,index){
      this.$confirm('此操作将永久删除, 是否继续?', '提示', {
          confirmButtonText: '确定',
          cancelButtonText: '取消',
          type: 'warning'
        }).then(() => {
          this.list.splice(index,1)
          });
      }
    }
  
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
</style>
