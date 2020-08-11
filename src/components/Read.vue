<template>
  <section class="section1">
    <div class="container">
      <h2>{{ section1.title }}</h2>
      <div class="slider">
        <div class="nav">
          <div class="nav__left circle"></div>
          <div class="nav__right circle"></div>
        </div>
        <div class="articles">
          <div class="articles__item"
               v-for='item in section1.items'
               :key="item.id"
          >
            <img class="articles__item-image" v-bind:src=" require('../assets/images/' + item.img) " alt="">
            <div class="articles__item-content">
              <div class="date">
                <a href="#">{{ item.date }}</a>
              </div>
              <div class="tags">
                <a href="#" class="tags__item"
                   v-for="tag in item.tags"
                   :key="tag.tag"
                >
                  {{ tag }}
                </a>
              </div>
              <h2 v-html="item.title"></h2>
<!--              <h2>{{item.title}}</h2>-->
            </div>
          </div>
        </div>
      </div>
      <div class="hr"></div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Read',
  data () {
    return {
      section1: {
        title: 'Читайте также',
        items: [
          {
            img: '1.png',
            date: '8 октября 2019',
            tags: {
              tag1: '#ПЕТ',
              tag2: '#ПЕТ/КТ'
            },
            title: 'Делать ли ПЭТ <br> после КТ',
            id: 'art1'
          },
          {
            img: '2.png',
            date: '28 августа 2018',
            tags: {
              tag1: '#ПЕТ/КТ'
            },
            title: 'Благодарность <br> сотрудникам ПЭТ/КТ',
            id: 'art2'
          }
        ]
      }
    }
  }
}
</script>

<style lang="scss">
.section1{
  .container{
    h2{
      text-align: left;
      font-size: 37px;
      color: #2e2e2e;
      margin-bottom: 45px;
    }
    .slider{
      position: relative;
      .nav{
        position: absolute;
        top: 89px;
        width: 100%;
        display: flex;
        justify-content: space-between;
        .circle{
          width: 45px;
          height: 45px;
          background: #006eb8;
          border-radius: 50%;
          z-index: 10;
        }
        &__left{
          margin-left: -20px;
          position: relative;
          &:before{
            content: "";
            background-color: transparent;
            position: absolute;
            left: 19px;
            top: 19px;
            width: 8px;
            border-bottom: 2px solid #FFF;
            height: 8px;
            border-right: 2px solid #FFF;
            transform: rotate(135deg);
          }
        }
        &__right{
          margin-right: -20px;
          position: relative;
          &:before{
            content: "";
            background-color: transparent;
            position: absolute;
            left: 17px;
            top: 19px;
            width: 8px;
            border-bottom: 2px solid #FFF;
            height: 8px;
            border-right: 2px solid #FFF;
            transform: rotate(-45deg);
          }
        }
      }
      .articles {
        display: flex;
        justify-content: space-between;
        position: relative;
        &__item{
          display: flex;
          width: 50%;
          max-width: 643px;
          background: #edeff3;
          &-images{
            width: 275px;
          }
          &-content{
            width: 100%;
            max-width: 368px;
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            padding-left: 43px;
            padding-top: 24px;
            .date{
              margin-bottom: 13px;
              a{
                color: #5c5c5e;
                font-size: 15px;
                line-height: 15px;
                text-decoration: none;
              }
            }
            .tags{
              display: flex;
              flex-direction: row;
              justify-content: flex-start;
              &__item{
                text-decoration: none;
                margin-right: 12px;
                font-size: 10px;
                padding: 3px 11px;
                border: 1px solid #989b9a;
                border-radius: 3px;
                color: #989b9a;
              }
            }
            h2{
              text-align: left;
              font-size: 20px;
              line-height: 28px;
              color: #3b3d41;
            }
          }
        }
      }
    }
  }
  .hr{
    width: 100%;
    height: 1px;
    background: #e0e0e0;
    margin-top: 76px;
  }
}
</style>
