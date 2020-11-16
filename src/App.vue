<template>
  <el-container>
    <el-header>
      <div class="flex">
        <span>王云峰</span>
        <span>
          <a href="#intro">个人介绍</a><i class="def"></i>
          <a href="#project">项目介绍</a><i class="def"></i>
          <a href="#interaction">给我留言</a>
        </span>
      </div>
    </el-header>
    <el-main>
      <el-row :gutter="2" id="intro">
        <el-col :span="6">
          <div class="grid-content bg-purple">
            <div>技能掌握</div>
            <!-- <h3 class="skills">技能掌握</h3> -->
            <ul>
              <li>Javascript</li>
              <li>CSS</li>
              <li>HTML</li>
              <li>Python</li>
              <li>SQL</li>
            </ul>
          </div>
        </el-col>
        <el-col :span="18">
          <div class="grid-content bg-purple">
              <el-tabs v-model="activeName2" type="card" @tab-click="handleClick">
                <el-tab-pane label="教育经历" name="first">
                  <dl>
                    <dt>2016-2020</dt>
                    <dd>浙江大学 信息与电子工程学院 信息工程专业</dd>
                    <dt>2020-2023</dt>
                    <dd>浙江大学 信息与电子工程学院 电子与通信工程专业</dd>
                  </dl>
                </el-tab-pane>
                <el-tab-pane label="工作经历" name="second">
                  <dl>
                    <dt>2019.08-2019.11</dt>
                    <dd>杭州湖西云百生科技有限公司 算法实习生</dd>
                    <dt>2020.09-2020.11</dt>
                    <dd>杭州传送门科技有限公司 前端实习生</dd>
                  </dl>
                </el-tab-pane>
                <el-tab-pane label="获奖情况" name="third">
                  <dl>
                    <dt>2017</dt>
                    <dd>学业三等奖学金</dd>
                    <dt>2018</dt>
                    <dd>学业三等奖学金</dd>
                    <dd>优秀学生三等奖学金</dd>
                    <dd>国家人才基地三等奖学金</dd>
                    <dt>2019</dt>
                    <dd>全国大学生电子设计竞赛浙江赛区二等奖</dd>
                    <dd>浙江大学光电设计竞赛一等奖</dd>
                  </dl>
                </el-tab-pane>
              </el-tabs>
          </div>
        </el-col>
      </el-row>
      <div id="project">
        <ul>
          <li>
            <div>医学图像分割</div>
            <div class="flex">
              <span>实习生<i class="def"></i>杭州湖西百生科技有限公司</span>
              <span>2019.08-2019.11</span>
            </div>
            <div>利用人体髋关节的CT扫描图像，认为标记背景、左腿、右腿、骨盆四部分。基于全卷积网络U-net，训练出一个可以 分割这四部分的模型，为人造髋关节手术提供便利条件。</div>
            <div>项目中使用的技术: <span>Tensorflow<i class="def"></i>Keras<i class="def"></i>TensorRT</span></div>
          </li>
          <li>
            <div>医学图像分割</div>
            <div class="flex">
              <span>实习生<i class="def"></i>杭州湖西百生科技有限公司</span>
              <span>2019.08-2019.11</span>
            </div>
            <div>利用人体髋关节的CT扫描图像，认为标记背景、左腿、右腿、骨盆四部分。基于全卷积网络U-net，训练出一个可以 分割这四部分的模型，为人造髋关节手术提供便利条件。</div>
            <div>项目中使用的技术: <span>Tensorflow<i class="def"></i>Keras<i class="def"></i>TensorRT</span></div>
          </li>
          <li>
            <div>医学图像分割</div>
            <div class="flex">
              <span>实习生<i class="def"></i>杭州湖西百生科技有限公司</span>
              <span>2019.08-2019.11</span>
            </div>
            <div>利用人体髋关节的CT扫描图像，认为标记背景、左腿、右腿、骨盆四部分。基于全卷积网络U-net，训练出一个可以 分割这四部分的模型，为人造髋关节手术提供便利条件。</div>
            <div>项目中使用的技术: <span>Tensorflow<i class="def"></i>Keras<i class="def"></i>TensorRT</span></div>
          </li>
          <li>
            <div>医学图像分割</div>
            <div class="flex">
              <span>实习生<i class="def"></i>杭州湖西百生科技有限公司</span>
              <span>2019.08-2019.11</span>
            </div>
            <div>利用人体髋关节的CT扫描图像，认为标记背景、左腿、右腿、骨盆四部分。基于全卷积网络U-net，训练出一个可以 分割这四部分的模型，为人造髋关节手术提供便利条件。</div>
            <div>项目中使用的技术: <span>Tensorflow<i class="def"></i>Keras<i class="def"></i>TensorRT</span></div>
          </li>
        </ul>
      </div>
      <div id="interaction">
        <div class="photoes">
          <el-carousel>
            <el-carousel-item v-for="item in 4" :key="item">
              <!-- <h3>{{ item }}</h3> -->
            </el-carousel-item>
          </el-carousel>
        </div>
      </div>
    </el-main>
    <el-footer>Stay hungry, stay foolish.</el-footer>
  </el-container>
</template>

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
  .el-carousel__item h3 {
    color: #475669;
    font-size: 14px;
    opacity: 0.75;
    line-height: 150px;
    margin: 0;
  }

  .el-carousel__item:nth-child(2n) {
     background-color: #99a9bf;
  }
  
  .el-carousel__item:nth-child(2n+1) {
     background-color: #d3dce6;
  }

  .flex {
    display: flex;
    justify-content: space-between;
  }
  i.def {
    display: inline-block;
    background-color: black;
    width: 1px;
    height: 1rem;
    margin: 0 3px;
  }
  .photoes {
    width: 630px;
  }
</style>
