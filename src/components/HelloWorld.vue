<template>
  <div class="hello">
    <div class="top-background">
      <!--导航栏 -->
      <div class="topnav-box">
        <div class="topnav">
          <div class="img topnav-logo"></div>
          <div class="top-title-container">
            <div
              :class="
                'topnav-title ' + 'topnav-title-' + index + ' topnav-title-font'
              "
              v-for="(value, index) in topBarData"
              :key="index"
            >
              {{ value }}
            </div>
          </div>
        </div>
      </div>

      <!--连接部分 -->
      <div class="connection">
        <div class="connection-title">
          National Intellectual Property Operation Public Service Platfor
        </div>
        <div class="connection-mulch"></div>
      </div>
      <!--页面内容部分 -->
      <div class="content">
        <!--图片新闻 -->
        <div class="content-news-and-img">
          <div class="news-titles">
            <div class="news-title">
              习近平在江西考察并主持召开推动中部地区崛起工作座谈会
            </div>
            <div class="news-data">2020-06-02</div>
          </div>
          <div class="news-img">
            <!-- 圆点 -->
            <div class="news-img-circles">
              <div class="news-img-circle"></div>
              <div class="news-img-circle"></div>
              <div class="news-img-circle circle-active"></div>
              <div class="news-img-circle"></div>
              <div class="news-img-circle"></div>
            </div>
          </div>
        </div>

        <!--要闻动态和企业服务 -->
        <div class="content-importantNews-and-companyService">
          <div class="content-importantNews">
            <div class="content-importantNews-title">
              <div class="content-importantNews-title-left">要闻动态</div>
              <div class="content-importantNews-title-right">更多</div>
            </div>
            <div>
              <div class="content-importantNews-content">
                <ul>
                  <li v-for="(value, index) in latestNews" :key="index">
                    <div class="content-importantNews-title-and-news">
                      <div class="content-importantNews-content-left-font">
                        {{ value.content }}
                      </div>
                      <div class="content-importantNews-content-right-font">
                        {{ value.time }}
                      </div>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <div class="content-importantNews-and-companyServices-mid"></div>
          <div class="content-companyService">
            <div class="content-companyService-title">
              <div class="content-companyService-title-left">企业服务</div>
              <div class="content-companyService-title-right">
                <div style="margin-right: 25px">换一换</div>
              </div>
            </div>
            <div class="content-companyService-content">
              <div
                :class="
                  'content-companyService-content-card  ' +
                  ' content-companyService-content-card' +
                  (index + 1) +
                  '  content-companyService-content-text-font '
                "
                v-for="(value, index) in companyServices"
                :key="index"
              >
                {{ value }}
              </div>
            </div>
          </div>
        </div>

        <!--中间横幅 -->
        <div class="content-midBanner"></div>
        <div class="content-gray-block"></div>

        <!--政策和专利数据 -->
        <div class="mid-content-policy-and-patentData">
          <div class="mid-content-policy">
            <div class="mid-content-policy-title">
              <div class="mid-content-policy-title-left">政策</div>
              <div class="mid-content-policy-title-right">更多</div>
            </div>
            <div>
              <div class="mid-content-policy-content">
                <ul>
                  <li v-for="(value, index) in policy" :key="index">
                    <div class="mid-content-policy-title-and-news">
                      <div class="mid-content-policy-content-left-font">
                        {{ value.content }}
                      </div>
                      <div class="mid-content-policy-content-right-font">
                        {{ value.time }}
                      </div>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <div class="mid-content-patentData">
            <div class="mid-content-patentData-title">
              <div class="mid-content-patentData-title-left">专利数据</div>
              <div class="mid-content-patentData-title-right">更多</div>
            </div>
            <div>
              <div class="mid-content-patentData-content">
                <ul>
                  <li v-for="(value, index) in patentData" :key="index">
                    <div class="mid-content-patentData-title-and-news">
                      <div class="mid-content-patentData-content-left-font">
                        {{ value.content }}
                      </div>
                      <div class="mid-content-patentData-content-right-font">
                        {{ value.time }}
                      </div>
                    </div>
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
        <div class="blank"></div>

        <!-- <div>
          <div v-for="(value, index) in img" :key="index">
            <img :src="value.url" width="42" height="42" /><br />{{
              value.test
            }}
          </div>
        </div> -->

        <!--国防专题 -->
        <div class="content-defense">
          <div class="content-defense-title">
            <div class="content-defense-title-left">国防专题</div>
            <div class="content-defense-title-right">更多</div>
          </div>
          <div class="content-defense-content">
            <ul>
              <li v-for="(value, index) in defense" :key="index">
                <div class="content-defense-title-and-news">
                  <div class="content-defense-content-left-font">
                    {{ value.content1 }} <span>{{ value.content2 }}</span>
                  </div>
                  <div class="content-defense-content-right-font">
                    {{ value.time }}
                  </div>
                </div>
              </li>
            </ul>
          </div>
        </div>
        <div class="content-gray-block"></div>

        <!--机构  -->
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data() {
    return {
      // img: [
      //   {
      //     url: require("../assets/logo.png"),
      //     test: "aa",
      //   },
      // ],

      topBarData: [
        "首页",
        "新闻动态",
        "企业服务",
        "政策库",
        "专利数据",
        "国防专题",
        "机构服务",
      ],
      latestNews: [
        {
          content: "习近平在江西考察并主持召开推动中部地区崛起工作座谈",
          time: "2018-06-15",
        },
        {
          content:
            "刘奇在军民融合发展座谈会上强调:聚焦重点领域 创新发展模式 聚焦重点发文发文发文发...",
          time: "2018-06-15",
        },
        {
          content: "刘奇主持召开省委理论学习中心组军民融合专题集体学习会",
          time: "2018-06-15",
        },
        {
          content: "易炼红:抢机遇 增优势 创高地 加快推进军民融合深度发展",
          time: "2018-06-15",
        },
        {
          content: "国有企业和优势民营企业走进赣南革命老区",
          time: "2018-06-15",
        },
        {
          content: "中央军民融合办常委副主任金壮龙在江西调研军民融合发展情况",
          time: "2018-06-15",
        },
      ],
      companyServices: [
        "知识产权服务",
        "工商财税",
        "人力社保",
        "软件开发",
        "法律服务",
        "投融资服务",
      ],
      policy: [
        {
          content: "习近平在江西考察并主持召开推动",
          time: "2018-06-15",
        },
        {
          content: "刘奇在军民融合发展座谈会上强调:聚焦重点领域",
          time: "2018-06-15",
        },
        {
          content:
            "刘奇主持召开省委理论学习中心组军民融合专题集体学专题集体学学...",
          time: "2018-06-15",
        },
        {
          content: "易炼红:抢机遇 增优势 创高地 ",
          time: "2018-06-15",
        },
        {
          content: "国有企业和优势民营企业走进赣南革命老区",
          time: "2018-06-15",
        },
        {
          content: "中央军民融合办常委副主任金壮龙在江西调研",
          time: "2018-06-15",
        },
      ],
      patentData: [
        {
          content: "一种实现人工智能展示感觉的方法",
          time: "2018-06-15",
        },
        {
          content:
            "一种基于人工智能与物联网的可视化编程工具系统工具系统系统系...",
          time: "2018-06-15",
        },
        {
          content: "人工智能伤口评估综合管理系统",
          time: "2018-06-15",
        },
        {
          content: "一种实现游戏人工智能真实感视觉的方法",
          time: "2018-06-15",
        },
        {
          content: "一种人工智能自适应互动教学系统",
          time: "2018-06-15",
        },
        {
          content: "一种基于人工智能的体态分析助手系统及传输方法",
          time: "2018-06-15",
        },
      ],
      defense: [
        {
          content1: "一种基于人工智能的体态分析助手系统及传输方法",
          content2: "（华为研究所）",
          time: "2018-06-15",
        },
        {
          content1: "一种人工智能自适应互动教学系统",
          content2: "（山东浪潮人工智能研究院有限公司） ",
          time: "2018-06-15",
        },
        {
          content1: "一种实现游戏人工智能真实感视觉的方法",
          content2: "（广州创梦空间人工智能科技有限公司）",
          time: "2018-06-15",
        },
        {
          content1: "人工智能伤口评估综合管理系统",
          content2: "（杭州黑胡桃人工智能研究院）",
          time: "2018-06-15",
        },
        {
          content1: "一种基于人工智能与物联网的可视化编程工具系统",
          content2: "（墨子人工智能技术有限公司）",
          time: "2018-06-15",
        },
        {
          content1: "一种实现人工智能展示感觉的方法",
          content2: "（广州创梦空间人工智能科技有限公司）",
          time: "2018-06-15",
        },
      ],
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
/*背景*/
.top-background {
  width: 1921px;
  height: 978px;
  background-image: url("../assets/background-top.png");
  background-repeat: no-repeat;
  background-position: center top;
}

/*导航条*/
.topnav-box {
  width: 1920px;
  height: 65px;
  background-color: white;
  .topnav {
    width: 1200px;
    height: 64px;
    margin: 0 auto;
    //background-color: white;
    display: flex;
    justify-content: center;
    .topnav-logo {
      width: 217px;
      height: 65px;
      background-image: url("../assets/logo.png");
      &.img {
        background-repeat: no-repeat;
        background-position: center;
      }
    }
    .top-title-container {
      display: flex;
      .topnav-title {
        flex: 1;
        width: 128px;
        height: 65px;
        display: flex;
        justify-content: center;
        align-items: center;
        &.topnav-title-0 {
          background-color: #12558a;
          color: white;
        }
        .topnav-title-font {
          font-family: "微软雅黑";
          font-size: 16px;
          font-weight: 400;
          line-height: 20px;
        }
      }
    }
  }
}

/*导航栏与内容连接处 */
.connection {
  width: 1200px;
  padding-right: 16px;
  height: 161px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  //background-color: #bff7c3;
  .connection-title {
    align-self: flex-end;
    height: 108px;
    font-size: 16px;
    line-height: 108px;
    color: white;
    overflow: hidden;
  }
  .connection-mulch {
    align-self: center;
    width: 450px;
    height: 44px;
    background-image: url("../assets/connectionMulch.png");
  }
}

/*页面内容 */
.content {
  padding-right: 16px;
  width: 1201px;
  margin: 0 auto;
  //background-color: #07f53a;
}

/*图片新闻 */
.content-news-and-img {
  background-color: white;
  .news-titles {
    height: 117px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    .news-title {
      margin-top: 5px;
      color: #12558a;
      font-family: "微软雅黑";
      font-size: 24px;
      font-weight: 400;
      line-height: 40px;
    }
    .news-data {
      margin-top: 18px;
      font-family: "宋体";
      font-size: 14px;
      font-weight: 400;
      line-height: 22px;
    }
  }
  .news-img {
    width: 1200px;
    height: 570px;
    display: flex;
    justify-content: center;
    background-image: url("../assets/photoNews.png");
    .news-img-circles {
      display: flex;
      align-self: flex-end;
      margin-bottom: 20px;
      .news-img-circle {
        border-radius: 50%;
        background-color: rgba(255, 255, 255, 0.4);
        width: 12px;
        height: 12px;
      }
      .news-img-circle:not(:first-child) {
        margin-left: 8px;
      }
      .circle-active {
        background-color: #12558a;
      }
    }
  }
}

.content-importantNews-and-companyService {
  background-color: white;
  padding-top: 36px;
  display: flex;
  //flex-direction: row;
}

/*要闻动态 */
.content-importantNews {
  width: 746px;
  height: 229px;
  .content-importantNews-title {
    display: flow-root;
    .content-importantNews-title-left {
      margin-left: 48px;
      float: left;
      width: 64px;
      text-align: left;
      border-bottom: 1px solid #12558a;
      padding-bottom: 8px;
      margin-bottom: 4px;
      color: #12558a;
      font-size: 16px;
      font-weight: bold;
      line-height: 32px;
    }
    .content-importantNews-title-right {
      margin-right: 32px;
      float: left;
      width: 602px;
      text-align: right;
      border-bottom: 1px solid #e8e8e8;
      padding-bottom: 8px;
      font-size: 14px;
      font-weight: 400;
      line-height: 32px;
    }
  }
  .content-importantNews-content {
    margin-left: 30px;
    display: flex;
    justify-content: space-between;
    .content-importantNews-title-and-news {
      width: 90%;
      display: inline-flex;
      justify-content: space-between;
      margin-top: 2px;
      .content-importantNews-content-left-font {
        font-size: 14px;
        text-align: left;
        line-height: 24px;
        display: flex;
        justify-content: space-between;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
      .content-importantNews-content-right-font {
        font-family: "宋体";
        font-size: 12px;
        line-height: 30px;
      }
    }
  }
}

.content-importantNews-and-companyServices-mid {
  display: flow-root;
  width: 4px;
  background: gray;
  height: 229px;
}

/*企业服务 */
.content-companyService {
  width: 450px;
  height: 229px;
  //background-color: rgb(202, 177, 226);
  .content-companyService-title {
    display: flow-root;
    .content-companyService-title-left {
      margin-left: 34px;
      float: left;
      width: 80px;
      text-align: left;
      border-bottom: 1px solid #12558a;
      padding-bottom: 8px;
      margin-bottom: 4px;
      color: #12558a;
      font-size: 16px;
      font-weight: bold;
      line-height: 32px;
    }
    .content-companyService-title-right {
      margin-right: 48px;
      float: left;
      width: 288px;
      text-align: right;
      border-bottom: 1px solid #e8e8e8;
      padding-bottom: 8px;
      font-size: 14px;
      font-weight: 400;
      line-height: 32px;
      background-image: url("../assets/circle1.png");
      background-repeat: no-repeat;
      background-position: right;
    }
  }
  .content-companyService-content {
    margin-left: 34px;
    width: 368px;
    height: 184px;
    display: flex;
    flex-wrap: wrap;
    align-content: space-between;
    justify-content: space-between;
    .content-companyService-content-card {
      margin-top: 20px;
      width: 94px;
      height: 74px;
      background-position: center top;
      background-repeat: no-repeat;
      &.content-companyService-content-card1 {
        background-image: url("../assets/companyService1.png");
      }
      &.content-companyService-content-card2 {
        background-image: url("../assets/companyService2.png");
      }
      &.content-companyService-content-card3 {
        background-image: url("../assets/companyService3.png");
      }
      &.content-companyService-content-card4 {
        background-image: url("../assets/companyService4.png");
      }
      &.content-companyService-content-card5 {
        background-image: url("../assets/companyService5.png");
      }
      &.content-companyService-content-card6 {
        background-image: url("../assets/companyService6.png");
      }
      &.content-companyService-content-text-font {
        font-size: 14px;
        text-align: left;
        line-height: 120px;
        text-align: center;
      }
    }
  }
}

/*中部横幅 */
.content-midBanner {
  width: 1200px;
  height: 148px;
  padding-bottom: 7px;
  background-image: url("../assets/banner.png");
  background-position: center;
  background-repeat: no-repeat;
  //background-color: rgb(210, 230, 171);
}
.content-gray-block {
  background-color: #e5f2fd;
  height: 22px;
}

/*政策和专利数据 */
.mid-content-policy-and-patentData {
  //background-color: white;
  display: flex;
  //flex-direction: row;
  .mid-content-policy {
    width: 607px;
    height: 266px;
    //background-color: #b4eeb7;
    .mid-content-policy-title {
      display: flow-root;
      padding-top: 36px;
      .mid-content-policy-title-left {
        margin-left: 47px;
        float: left;
        width: 42px;
        text-align: left;
        border-bottom: 1px solid #12558a;
        padding-bottom: 8px;
        margin-bottom: 4px;
        color: #12558a;
        font-size: 16px;
        font-weight: bold;
        line-height: 32px;
      }
      .mid-content-policy-title-right {
        margin-right: 31px;
        float: left;
        width: 486px;
        text-align: right;
        border-bottom: 1px solid #e8e8e8;
        padding-bottom: 8px;
        font-size: 14px;
        font-weight: 400;
        line-height: 32px;
      }
    }
    .mid-content-policy-content {
      display: flex;
      justify-content: space-between;
      padding: 0 14px 0 30px;
      .mid-content-policy-title-and-news {
        width: 90%;
        display: inline-flex;
        justify-content: space-between;
        margin-top: 2px;
        .mid-content-policy-content-left-font {
          font-size: 14px;
          text-align: left;
          line-height: 24px;
          display: flex;
          justify-content: space-between;
          overflow: hidden;
          text-overflow: ellipsis;
          white-space: nowrap;
        }
        .mid-content-policy-content-right-font {
          font-family: "宋体";
          font-size: 12px;
          line-height: 30px;
        }
      }
    }
  }

  .mid-content-patentData {
    width: 593px;
    height: 266px;
    //background-color: #aacafa;
    .mid-content-patentData-title {
      display: flow-root;
      padding-top: 36px;
      .mid-content-patentData-title-left {
        margin-left: 25px;
        float: left;
        width: 83px;
        text-align: left;
        border-bottom: 1px solid #12558a;
        padding-bottom: 8px;
        margin-bottom: 4px;
        color: #12558a;
        font-size: 16px;
        font-weight: bold;
        line-height: 32px;
      }
      .mid-content-patentData-title-right {
        margin-right: 47px;
        float: left;
        width: 438px;
        text-align: right;
        border-bottom: 1px solid #e8e8e8;
        padding-bottom: 8px;
        font-size: 14px;
        font-weight: 400;
        line-height: 32px;
      }
    }
    .mid-content-patentData-content {
      margin-right: 30px;
      display: flex;
      justify-content: space-between;
      .mid-content-patentData-title-and-news {
        width: 90%;
        display: inline-flex;
        justify-content: space-between;
        margin-top: 2px;
        .mid-content-patentData-content-left-font {
          font-size: 14px;
          text-align: left;
          line-height: 24px;
          display: flex;
          justify-content: space-between;
          overflow: hidden;
          text-overflow: ellipsis;
          white-space: nowrap;
        }
        .mid-content-patentData-content-right-font {
          font-family: "宋体";
          font-size: 12px;
          line-height: 30px;
        }
      }
    }
  }
}

// 政策和专利数据下的空白
.blank {
  width: 1200px;
  height: 104px;
  //background-color: #f77d7d;
}
//国防专题
.content-defense {
  width: 1201px;
  height: 273px;
  //background-color: aqua;
  .content-defense-title {
    display: flow-root;
    .content-defense-title-left {
      margin-left: 48px;
      float: left;
      width: 80px;
      text-align: left;
      border-bottom: 1px solid #12558a;
      padding-bottom: 8px;
      margin-bottom: 4px;
      color: #12558a;
      font-size: 16px;
      font-weight: bold;
      line-height: 32px;
    }
    .content-defense-title-right {
      margin-right: 48px;
      float: left;
      width: 1024px;
      text-align: right;
      border-bottom: 1px solid #e8e8e8;
      padding-bottom: 8px;
      font-size: 14px;
      font-weight: 400;
      line-height: 32px;
    }
  }
  .content-defense-content {
    display: flex;
    justify-content: space-between;
    .content-defense-title-and-news {
      width: 90%;
      display: inline-flex;
      justify-content: space-between;
      margin-top: 2px;
      .content-defense-content-left-font {
        font-size: 14px;
        text-align: left;
        line-height: 24px;
        display: flex;
        justify-content: space-between;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
      .content-defense-content-left-font span {
        font-size: 14px;
        line-height: 24px;
        color: rgba(0, 0, 0, 0.35);
      }
      .content-defense-content-right-font {
        font-family: "宋体";
        font-size: 12px;
        line-height: 30px;
      }
    }
  }
}

//机构
.content-institutions {
  width: 1200px;
  height: 472px;
  .title {
  }
  .institutions {
    .institution {
      .institution-icon {
      }
      .institution-detail {
        .title {
        }
        .sub-title {
        }
        .btns {
          .btn {
          }
        }
      }
    }
  }
}

ul {
  list-style-type: square;
  list-style-position: inside;
  //margin: 0px;
  //padding: 0px;
  width: 100%;
  //padding: 0 15px;
}
</style>
