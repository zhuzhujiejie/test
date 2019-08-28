<template>
  <div class="main">
    <div class="nav">
      <a :class="{active:checked==1}" @click="sortList('typeId',1)">按分类排序</a>
      <a :class="{active:checked==2}" @click="sortList('createTime',2)">按时间排序</a>
    </div>
    <div class="content" v-for="(it,index) in dataList" :key="index">
      <h1 class="title">{{it.title}}</h1>
      <draggable v-model="it.photos" :options="{group:'group',}" class="wraper">
        <div class="item" v-for="(item,index) in it.photos" :key="'info'+index">
          <img :src="item.img" alt=""/>
          <div class="info">
            <p>名称：{{item.name}}</p>
            <p>创建时间：{{item.createTime}}</p>
          </div>
        </div>
      </draggable>
    </div>
  </div>
</template>

<script type="text/babel">
import draggable from 'vuedraggable'

export default {
  name: 'List',
  data () {
    return {
      checked: 0,
      dataList: [
        {
          title: '风景',
          photos: [
            {
              'img': './static/images/1.jpg',
              'name': 'huahua',
              'info': '详情信息1',
              'typeId': 1,
              'createTime': '2018-8-24'
            },
            {
              'img': './static/images/2.jpg',
              'name': 'liuliu',
              'info': '详情信息2',
              'typeId': 2,
              'createTime': '2018-8-23'
            },
            {
              'img': './static/images/3.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 3,
              'createTime': '2018-8-22'
            },
            {
              'img': './static/images/4.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 4,
              'createTime': '2018-8-21'
            },
            {
              'img': './static/images/5.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 5,
              'createTime': '2018-8-20'
            },
            {
              'img': './static/images/6.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 6,
              'createTime': '2018-8-19'
            },
            {
              'img': './static/images/7.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 7,
              'createTime': '2018-8-18'
            },
            {
              'img': './static/images/8.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 8,
              'createTime': '2018-8-17'
            },
            {
              'img': './static/images/9.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 9,
              'createTime': '2018-8-16'
            }
          ]
        },
        {
          title: '卡通动漫',
          photos: [
            {
              'img': './static/images/25.jpg',
              'name': 'huahua',
              'info': '详情信息3',
              'typeId': 10,
              'createTime': '2018-8-15'
            },
            {
              'img': './static/images/26.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 11,
              'createTime': '2018-8-14'
            },
            {
              'img': './static/images/29.jpg',
              'name': 'liuliu',
              'info': '详情信息2',
              'typeId': 14,
              'createTime': '2018-8-11'
            },
            {
              'img': './static/images/30.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 15,
              'createTime': '2018-8-31'
            },
            {
              'img': './static/images/32.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 16,
              'createTime': '2018-8-9'
            }
          ]
        },
        {
          title: '宠物',
          photos: [
            {
              'img': './static/images/17.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 17,
              'createTime': '2018-10-21'
            },
            {
              'img': './static/images/18.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 18,
              'createTime': '2018-10-20'
            },
            {
              'img': './static/images/19.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 19,
              'createTime': '2018-10-9'
            },
            {
              'img': './static/images/20.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 20,
              'createTime': '2018-10-8'
            },
            {
              'img': './static/images/21.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 21,
              'createTime': '2018-10-7'
            },
            {
              'img': './static/images/22.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 22,
              'createTime': '2018-10-6'
            },
            {
              'img': './static/images/23.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 23,
              'createTime': '2018-10-5'
            },
            {
              'img': './static/images/24.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 24,
              'createTime': '2018-10-4'
            }
          ]
        },
        {
          title: '明星',
          photos: [
            {
              'img': './static/images/33.jpg',
              'name': 'liuliu',
              'info': '详情信息1',
              'typeId': 1,
              'createTime': '2018-8-6'
            },
            {
              'img': './static/images/35.jpg',
              'name': 'liuliu',
              'info': '详情信息1',
              'typeId': 3,
              'createTime': '2018-8-4'
            },
            {
              'img': './static/images/36.jpg',
              'name': 'liuliu',
              'info': '详情信息2',
              'typeId': 4,
              'createTime': '2018-8-3'
            },
            {
              'img': './static/images/37.jpg',
              'name': 'liuliu',
              'info': '详情信息1',
              'typeId': 5,
              'createTime': '2018-8-2'
            },
            {
              'img': './static/images/38.jpg',
              'name': 'liuliu',
              'info': '详情信息1',
              'typeId': 5,
              'createTime': '2018-8-2'
            }
          ]
        },
        {
          title: '汽车',
          photos: [
            {
              'img': './static/images/13.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 29,
              'createTime': '2018-9-4'
            },
            {
              'img': './static/images/14.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 23,
              'createTime': '2018-9-3'
            },
            {
              'img': './static/images/15.jpg',
              'name': 'liuliu',
              'info': '详情信息3',
              'typeId': 24,
              'createTime': '2018-9-2'
            },
            {
              'img': './static/images/16.jpg',
              'name': 'liuliu',
              'info': '详情信息2',
              'typeId': 28,
              'createTime': '2018-9-1'
            }
          ]
        }
      ]
    }
  },
  methods: {
    sortList (type = 'typeId', index) {
      this.checked = index || 1
      let len = this.dataList.length
      for (let i = 0; i < len; i++) {
        let arr = this.dataList[i].photos
        arr.sort((a, b) => {
          if (type === 'createTime') {
            return new Date(b[type]) > new Date(a[type]) ? 1 : -1
          }
          return b[type] - a[type]
        })
      }
    }
  },
  components: {
    draggable
  }
}
</script>

<style lang="css" scoped>
  .main {
    width: 1200px;
    margin: 0 auto;
    overflow: hidden;

  }

  .main .nav {
    text-align: left;
    padding: 20px 0;
    border-bottom: solid 1px #ddd;
  }

  .main .nav > a {
    padding: 2px 0;
    margin-right: 20px;
    font-size: 14px;
    cursor: pointer;
    font-weight: 600;
  }

  .main .nav > a.active {
    color: red;
  }

  .main .content {
    text-align: left;
  }

  .content .title {
    padding: 15px 0 10px 0;
    font-size: 15px;
  }

  .content .wraper {
    margin: 10px 0;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    justify-content: flex-start;
    align-items: center;
    align-content: flex-start;
  }

  .content .wraper .item {
    flex-basis: 205px;
    padding: 10px;
    margin: 5px 12px 5px 0;
    border-radius: 8px;
    border: solid 1px #ddd;
    overflow: hidden;
    cursor: move;
  }

  .content .wraper .item > img {
    max-width: 100%;
    max-height: 100%;
  }

  .content .wraper .item div.info {
    padding: 5px 0 0;
  }

  .content .wraper .item div.info > p {
    line-height: 20px;
    font-size: 12px;
  }
</style>
