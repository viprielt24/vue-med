<template>
  <section class="section2">
    <div class="container">
      <h2>{{ section2.title }}</h2>
      <p>{{ section2.text }}</p>
      <div class="slider">
        <div class="nav">
          <div class="nav__left circle"></div>
          <div class="nav__right circle"></div>
        </div>
        <div class="doctors">
          <div class="doctors__item"
               v-for='item in section2.items'
               :key="item.id"
          >
            <img class="doctors__item-image" v-bind:src=" require('../assets/images/' + item.img) " alt="">
            <div class="doctors__item-content">
              <a href="#" v-html="item.name" class="name"></a>
              <div class="position">{{ item.position }}</div>
              <div class="text">{{ item.text }}</div>
            </div>
          </div>
        </div>
      </div>
      <a href="#" class="all btn">Все специалисты центра</a>
    </div>
  </section>
</template>

<script>
export default {
  name: 'BestDoctors',
  data () {
    return {
      section2: {
        title: 'Лучшие врачи Москвы и МО',
        text: 'Онкологический центр Sofia является партнером передовых американских и израильских клиник. Наши врачи получали квалификацию в лучших онкологических центрах мира, благодаря чему наши клиенты получают качественное лечение по зарубежным стандартам Не покидая пределов Российской Федерации.',
        items: [
          {
            img: 'jukova.png',
            name: 'Жукова <br>Елена Николаевна',
            position: 'Онколог',
            text: 'Член Российского общества маммологов, член RUSSCO, член Европейского онкологического общества ESMO. Год начала врачебной практики - 2008',
            id: 1
          },
          {
            img: 'gilmanova.png',
            name: 'Гильманова <br>Дилара Раисовна',
            position: 'Врач-радиолог ПЭТ/КТ',
            text: 'Врач-радиолог ПЭТ/КТ. Год начала врачебной практики - 2013',
            id: 2
          },
          {
            img: 'vul.png',
            name: 'Вуль Ольга <br>Александровна',
            position: 'Онколог (химиотерапия)',
            text: 'Врач-онколог высшей квалификационной категории, член RUSSCO и ESMO. Год начала врачебной практики - 1992 стаж 12 лет',
            id: 3
          }
        ]
      }
    }
  }
}
</script>

<style lang="scss">
.section2{
  margin-top: 65px;
  padding-bottom: 100px;
  .container{
    h2{
      text-align: left;
      font-size: 37px;
      font-weight: 500;
      color: #2e2e2e;
      margin-bottom: 18px;
    }
    p{
      font-size: 15px;
      line-height: 20px;
      color: #797979;
      text-align: left;
      margin-bottom: 55px;
      max-width: 950px;
    }
    .slider {
      position: relative;
      margin-bottom: 51px;
      .nav {
        position: absolute;
        top: 89px;
        width: 100%;
        display: flex;
        justify-content: space-between;
        .circle {
          width: 45px;
          height: 45px;
          background: #006eb8;
          border-radius: 50%;
          z-index: 10;
          position: relative;
        }
        &__left {
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
        &__right {
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
      .doctors {
        display: flex;
        justify-content: space-between;
        position: relative;
        &__item {
          display: flex;
          flex-direction: row;
          justify-content: flex-start;
          width: 33%;
          max-width: 417px;
          min-height: 225px;
          background: #edeff3;
          border-radius: 5px;
          &-image {
            min-width: 180px;
            border-radius: 5px 0 0 5px;
          }
          &-content {
            width: 100%;
            max-width: 237px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            text-align: left;
            padding-left: 20px;
            padding-top: 3px;
            .name{
              color: #003887;
              font-weight: 700;
              font-size: 18px;
              line-height: 27px;
              text-decoration: underline;
              margin-bottom: 7px;
            }
            .position{
              margin-bottom: 10px;
              font-size: 14px;
              color: #474a49;
            }
            .text{
              font-size: 12px;
              line-height: 18px;
              color: #898b8d;
              max-width: 196px;
            }
          }
        }
      }
    }
    .all{
      background: #FFF;
      border-radius: 30px;
      border: 2px solid #006dbb;
      font-size: 15px;
      font-weight: 700;
      color: #006dbb;
      text-decoration: none;
      height: 45px;
      width: 280px;
      display: flex;
      justify-content: center;
      align-items: center;
      margin: auto;
    }
  }
}
</style>
