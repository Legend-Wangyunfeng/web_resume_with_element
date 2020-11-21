<template>
  <el-container>
    <el-header>
      <div class="flex header">
        <div class="name">王云峰</div>
        <div class="nav">
          <a href="#intro">个人介绍</a><i class="def"></i>
          <a href="#project">项目介绍</a><i class="def"></i>
          <a href="#interaction">给我留言</a>
          <img :src="require('./imgs/照片wy.jpg')" alt="">
        </div>
      </div>
    </el-header>
    <div class="main">
      <div class="intro">
        <h2>前端工程师</h2>
        <p>电子邮件: 845203476@qq.com</p>
        <p>联系电话: 18868108113</p>
      </div>
      <el-row :gutter="2" id="intro">
        <el-col :span="6" class="skills grid-content bg-purple">
            <h4 class="title">技能掌握</h4>
            <!-- <h3 class="skills">技能掌握</h3> -->
            <ul>
              <li v-for="item in skills" :key="item.tool">
                <span class="tools">{{item.tool}}</span>
                <span class="level">
                  <el-col :span="parseInt(24*item.level)"></el-col>
                </span>
              </li>
            </ul>      
        </el-col>
        <el-col :span="18" class="experiments">
          <div class="grid-content bg-purple">
            <el-tabs v-model="activeName2" type="card">
              <el-tab-pane label="教育经历" name="first">
                <ul>
                  <li v-for="item in education" :key="item.time">
                    <div class="time">{{item.time}}</div>
                    <div class="detail">
                      {{item.university}} {{item.school}} {{item.major}}
                    </div>
                  </li>
                </ul>
              </el-tab-pane>
              <el-tab-pane label="工作经历" name="second">
                <ul>
                  <li v-for="item in work" :key="item.time">
                    <div class="time">{{item.time}}</div>
                    <div class="detail">{{item.company}} {{item.job}}</div>
                  </li>
                </ul>
              </el-tab-pane>
              <el-tab-pane label="获奖情况" name="third">
                <ul>
                  <li v-for="item in awards" :key="item.time">
                    <div class="time">{{item.time}}</div>
                    <div class="detail" v-for="title in item.titles" :key="title">{{title}}</div>
                  </li>
                </ul>
              </el-tab-pane>
            </el-tabs>
          </div>
        </el-col>
      </el-row>
      <div id="project">
        <ul>
          <li v-for="project in projects" :key="project.id">
            <h4>{{project.title}}</h4>
            <div v-html="project.detail"></div>
            <div>项目中使用的技术: <span v-for="(tec, index) in project.tec" :key="tec">{{tec}}<i class="def" v-if="index < project.tec.length - 1"></i></span></div>
          </li>
        </ul>
      </div>
      <div id="interaction" class="flex">
        <div class="photoes">
          <el-carousel>
            <el-carousel-item v-for="item in imgs" :key="item">
              <img :src="item" alt="">
            </el-carousel-item>
          </el-carousel>
        </div>
        <div class="guestbook">
          <p>留言板</p>
          <div class='img-content'>
            <div class="flex" v-for="item in interaction" :key="item[0]">
              <div class="img-name">
                <img :src="require('./imgs/avatar.jpg')" alt="">
                <p class="name">{{item.name}}</p>
              </div>
              <div class="content">{{item.message}}</div>
            </div>
            <!-- <div class="even flex">
              <div class="img-name">
                <img src="/imgs/avatar.jpg" alt="">
                <p class="name">Simon</p>
              </div>
              <div class="content"></div>
            </div> -->
          </div>
          <el-form>
            <el-input class="message" type="text" placeholder="input your message" v-model="input_message" clearable></el-input>
            <div class="flex">
              <el-input class="name" type="text" placeholder="input your name" v-model="input_name" clearable></el-input>
              <el-button @click="handle()">Submit</el-button>
            </div>
          </el-form>          
        </div>
      </div>
    </div>
    <el-footer>You are the one who can fill the world with sunshine.</el-footer>
  </el-container>
</template>

<script>
export default {
  data() {
    return {
      activeName2: 'first',
      imgs: [
        require('./imgs/one.jpg'),
        require('./imgs/two.jpg'),
        require('./imgs/three.jpg'),
        require('./imgs/four.jpg'),
        require('./imgs/five.jpg'),
        require('./imgs/six.jpg'),
        require('./imgs/seven.jpg')
      ],
      skills: [
        {tool: 'Javascript', level: 0.8},
        {tool: 'CSS', level: 0.7},
        {tool: 'HTML', level: 0.9},
        {tool: 'Vue', level: 0.75},
        {tool: 'Python', level: 0.85}
      ],
      education: [
        {
          time: '2016 - 2020',
          university: "浙江大学",
          school: "信息与电子工程学院",
          major: "信息工程专业"
        },
        {
          time: '2020 - 2022',
          university: "浙江大学",
          school: "信息与电子工程学院",
          major: "电子与通信工程专业"
        }
      ],
      work: [
        {
          time: '2020.09 - 2020.11', 
          company:"杭州传送门科技有限公司",
          job: "前端实习生"
        },
        {
          time: '2019.08 - 2019.11', 
          company:"杭州湖西云百生科技有限公司",
          job: "算法实习生"
        }
      ],
      awards: [
        {
          time: "2017",
          titles: ["学业三等奖学金"]
        },
        {
          time: "2018",
          titles: ["学业三等奖学金", "优秀学生三等奖学金", "国家人才基地三等奖学金"]
        },
        {
          time: "2019",
          titles: ["全国大学生电子设计竞赛浙江赛区二等奖", "浙江大学光电设计竞赛一等奖"]
        }
      ],
      projects: [
        {
          id: 1,
          title: "Web个人主页",
          detail: "详见<a href='https://legend-wangyunfeng.github.io/web_resume_vue/' target='_blank'>https://legend-wangyunfeng.github.io/web_resume_vue/</a>",
          tec: ["Vue", "Element-UI"]
        },
        {
          id: 2,
          title: "仿手机端Boss直聘网站",
          detail: "仿Boss直聘手机官网，做了三个页面，包括主页、列表页、详情页。<br/>详见<a href='https://github.com/Legend-Wangyunfeng/boss_zhipin' target='_blank'>https://github.com/Legend-Wangyunfeng/boss_zhipin</a>",
          tec: ["Vue", "Nuxt.js"]
        },
        {
          id: 3,
          title: "医学图像分割",
          detail: "利用人体髋关节的CT扫描图像，认为标记背景、左腿、右腿、骨盆四部分。基于全卷积网络U-net，训练出一个可以 分割这四部分的模型，为人造髋关节手术提供便利条件。",
          tec: ["Tensorflow", "Keras", "TensorRT"]
        },
        {
          id: 4,
          title: "基于用户通信数据的重要位置识别",
          detail: "根据运营商端用户通信数据，提取用户在各个基站上的行为特征，用非监督和监督学习方法对用户重要位置进行预测，并对城市功能进行 推断。",
          tec: ["聚类", "随机森林"]
        },
        {
          id: 5,
          title: "基于OpenCV 的疲劳驾驶检测系统",
          detail: "利用摄像头实时获取图像信息，捕捉司机眼部区域并计算眼部闭合度，当小于阈值时给予警报提醒。(获得浙江大学本科 生科研成果评选三等奖)",
          tec: ["OpenCV", "dlib"]
        },
      ],
      input_message: "",
      input_name: "",
      interaction: [],
      index: 1
    }
  },
  methods: {
    handle() {
      const content = {
        id: this.index,
        name: this.input_name,
        message: this.input_message
      }
      this.interaction.push(content)
      this.input_message = ""
      this.input_name = ""
      this.index += 1
      // console.log(this.interaction)
    }
  }
}
</script>

<style lang="scss">
  
 .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    height: 300px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
  // .el-carousel__item h3 {
  //   color: #475669;
  //   font-size: 14px;
  //   opacity: 0.75;
  //   line-height: 150px;
  //   margin: 0;
  // }

  // .el-carousel__item:nth-child(2n) {
  //    background-color: #99a9bf;
  // }
  
  // .el-carousel__item:nth-child(2n+1) {
  //    background-color: #d3dce6;
  // }
  .el-container {
    // width: fit-content;
  }
  .flex {
    display: flex;
    justify-content: space-between;
  }
  
  .header {
    font-family: 'Courier New', Courier, monospace;
    width: 960px;
    height: 100%;
    margin: 0 auto;
    align-items:center;
    
  }
  .header .name {
    display: inline-block;
    font-weight: bold;
    font-size: 25px;
  }
  .header .nav {
    height: 100%;
    display: flex;
    align-items: center;
  }
  .header .nav a{
    text-decoration: none;
    font-size: 15px;
    color: black;
  }
  .header .nav img {
    height: 60px;
    width: 60px;
    border-radius: 60px;
    margin-left: 40px;
  }
  .header .nav a:hover {
    font-weight: bold;
  }
  .header .nav a:visited {
    color: #000;
  }

  .main {
    width: 960px;
    margin: 0 auto;
    padding: 20px 0;
  }
  .intro {
    margin-bottom: 10px;
  }
  .intro h2{
    margin-top: 0;
    margin-bottom: 5px;
    padding: 0;
  }
  .intro p {
    margin: 0;
  }
  .skills h4{
    margin: 10px;
    text-align: center;
  }
  .skills ul {
    list-style: none;
    padding: 0;
  }
  .skills li {
    display: flex;
    justify-content: center;
    margin-bottom: 8px;
  }
  .skills li .tools {
    display: inline-block;
    width: 50%;
    text-align: end;
    padding-right: 2px;
  }
  .skills li .level {
    display: inline-block;
    width: 50%;
    // background-color: cornflowerblue;
    padding-left: 2px;
    
  }
  .skills li .level .el-col {
    background-color: cornflowerblue;
    height: 100%;
    // width: 70%;
    border-radius: 5px;
  }

  .experiments li{
    padding-bottom: 8px;
  }
  .experiments li .time {
    line-height: 1.2rem;
  }
  i.def {
    display: inline-block;
    background-color: black;
    width: 1px;
    height: 0.8rem;
    margin: 0 3px;
  }

  #project {
    font-size: 1rem;
  }
  #project ul {
    padding: 0;
    list-style: none;
  }
  #project h4 {
    margin: 5px 0;
  }
  #project li .desc {
    margin: 5px 0;
  }
  #project a {
    text-decoration: none;
    color: black;
    display: inline-block;
    margin-left: 5px;
  }
  #project a:hover {
    font-weight:bold;
  }

  #interaction {
    height: 370px;
  }
  .photoes {
    height: 100%;
    width: 630px;
    display: inline-block;
  }
  .photoes div {
    height: 100%;
  }
  .photoes img {
    height: 100%;
    width: 100%;
  }
  .guestbook {
    display: inline-block;
    height: 100%;
    flex: 1;
  }
  .guestbook p {
    text-align: center;
    margin: 0;
  }
  .guestbook .img-content{
    box-sizing: border-box;
    width: 300px;
    height: 250px;
    margin: 5px auto;
    border: 2px dotted;
    overflow: auto;
  }
  .guestbook .img-content > div {
    width: 100%;
    height: 80px;
    margin-bottom: 5px;
    // display: none;
  }
  .guestbook .img-content .img-name {
    box-sizing: border-box;
    height: 100%;
    width: 60px;
    margin: 0 5px;
    text-align: center;
  }
  // .guestbook .img-content .even .content {
  //   order: -1;
  // }
  .guestbook img {
    width: 50px;
    height: 50px;
    border: 1px solid gray;
    border-radius: 50px;
    position: relative;
    top: 5px;
    // background: url(./imgs/avatar.jpg);
    // background-size: 100% 100%;
  }
  .guestbook .name {
    position: relative;
    top: 5px;
  }
  .guestbook .content {
    height: 100%;
    box-sizing: border-box;
    width: 220px;
    border: 1px solid;
    padding: 4px;
    border-radius: 5px;
    overflow: auto;
  }
  .guestbook .el-form{
    padding: 0 10px;
  }
  .guestbook  form .name {
    // position: absolute;
    // left: 0;
    width: 200px;
  }
  .guestbook button {
    position: relative;
    top: 10px;
    right: 0;
  }
  .guestbook .el-button :active {
    color: #606266;
    border-color: #DCDFE6;
  }

  .el-footer {
    background-color: slategrey;
    text-align: center;
    line-height: 60px;
    font-size: 30px;
    font-family: STKaiti;
    width: 100%;
  }
</style>
