<template>

  <div class="container-fluid navigation">
    <Modal v-show="isModalVisible" @close="closeModal"/>

    <b-navbar class="px-0" toggleable="xl">

      <div class="d-flex flex-row d-xl-none navigation__hamburger">
        <b-navbar-toggle target="nav-collapse"><img src="~/static/gamburger.svg" alt=""></b-navbar-toggle>
        <b-navbar-brand class="logo" to="/">
          <div class="double-logo d-flex flex-column d-block d-xl-none">
            <h4 class="navigation__hamburger-title">Федеральный</h4>
            <h4 class="navigation__hamburger-title">Центр НМО</h4>
          </div>
        </b-navbar-brand>
      </div>

      <b-navbar-brand class="logo d-md-none d-xl-block" to="/">
        <h4 class="navigation__title d-none d-xl-flex">Федеральный Центр НМО</h4>
        <span class="navigation__description secondary-text">Дистанционное обучение врачей, медсестер и фармацевтов</span>
      </b-navbar-brand>


      <div class="navigation__phone d-none d-md-flex flex-column order-1 order-xl-2">
        <div>+7 (984) 888-45-42</div>
        <div class="navigation__phone-callMe">Заказать звонок</div>
      </div>

      <div class="phone-icon d-sm-flex d-md-none">
        <div><a href="tel:+7 (812) 409-97-36" class="email-text"><img src="../static/phone.svg" alt=""></a></div>
      </div>

      <div class="navigation__btn d-none d-md-flex order-2 order-xl-3" @click="showModal">Вход или регистрация</div>

      <b-collapse id="nav-collapse" is-nav class="navigation__main-menu order-3 order-xl-1">
        <b-navbar-nav>
          <b-nav-item exact no-prefetch active-class="active" class="navigation__link" to="/webinar">
            Вебинары
          </b-nav-item>
          <b-nav-item active-class="active" class="navigation__link" to="/programs">
            Программы НМО
          </b-nav-item>
          <b-nav-item active-class="active" class="navigation__link" to="/help">
            Помощь
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>

    </b-navbar>
  </div>

</template>

<script>
  import Modal from '~/components/Modal'

  export default {
    data() {
      return {
        isModalVisible: false,
      };
    },
    methods: {
      showModal() {
        this.isModalVisible = true;
      },
      closeModal() {
        this.isModalVisible = false;
      }
    },
    components: {
      Modal
    }
  }
</script>

<style lang="scss" scoped>

  .navigation {
    .logo {
      padding-right: 0 !important;
      cursor:pointer;
    }

    &__title {
      @media (min-width: 576px) {
        font-weight: bold;
        font-size: 18px;
        line-height: 21px;
        margin-bottom: 0 !important;
      }
      @media (min-width: 1024px) {
      }
    }

    &__description {
      font-size: 16px;
      line-height: 19px;
      display: none;
      @media (min-width: 1680px) {
        display: block;
      }
    }


    &__hamburger {
      button {
        border: none;
        outline: none;
        color: $text-color;
        padding-left: 0;
        padding-right: 23px;
      }

      &-title {
        font-weight: bold;
        font-size: 18px;
        line-height: 15px;

        &:first-child {
          margin-bottom: 5px;
        }
      }
    }

    &__main-menu {
      @media (max-width: 1580px) and (min-width: 1024px) {
        text-indent: -999em;
      }
    }

    &__link {
    color: orangered;
      &:hover {
        color: $active-color;
      }
    }

    &__phone {
      font-weight: 600;
      font-size: 19px;
      line-height: 24px;
      @media (min-width: 1024px) {
        transform: translate(-66px, 0);
      }
      @media (max-width: 1100px) and (min-width: 1024px) {
        font-size: 17px;
      }

      &-callMe {
        font-size: 18px;
        font-weight: normal;
        color: $active-color;
        border-bottom: 1px dashed;
        height: 21px;
        width: 130px;
        cursor: pointer;
      }
    }

    &__btn {
      justify-content: center;
      align-items: center;
      margin: 5px 0;
      color: white;
      height: 66px;
      width: 244px;
      background: $active-color;
      cursor: pointer;
      transition: background .3s ease, box-shadow .3s ease;

      @media (max-width: 1124px) {
        width: 190px;
      }

      &:hover {
        background: lighten($active-color, 10%);
        box-shadow: 0 7px 70px rgba(0, 50, 123, 0.3);
      }
    }

  }


</style>
