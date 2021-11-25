<template>
  <div class="page-wrapper">
    <div class="card">
      <div class="image-box">
        <img src="@/assets/img/image-equilibrium.jpg" alt="NFT image" class="image">
      </div>

      <h1 class="heading">Equilibrium #3429</h1>

      <p class="body">Our Equilibrium collection promotes balance and calm.</p>

      <div class="caption-box">
        <div class="row">
          <div class="price">
            <svg width="11" height="18" viewBox="0 0 11 18" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path fill-rule="evenodd" clip-rule="evenodd" d="M5.5 0L10.9961 9.16875L5.5 12.4312L0 9.16875L5.5 0ZM11 10.2165L5.5 18L0 10.2165L5.5 13.479L11 10.2165Z" fill="#00FFF8"/>
            </svg>

            <p class="caption strong">0.041 ETH</p>
          </div>

          <div class="timer">
            <svg width="17" height="17" viewBox="0 0 17 17" fill="none" xmlns="http://www.w3.org/2000/svg">
              <rect opacity="0.01" x="16.305" y="16.6739" width="16" height="16" transform="rotate(180 16.305 16.6739)" fill="black"/>
              <path fill-rule="evenodd" clip-rule="evenodd" d="M1.63834 8.67388C1.63834 4.99199 4.6231 2.00722 8.305 2.00722C10.0731 2.00722 11.7688 2.7096 13.019 3.95984C14.2693 5.21008 14.9717 6.90577 14.9717 8.67388C14.9717 12.3558 11.9869 15.3406 8.305 15.3406C4.6231 15.3406 1.63834 12.3558 1.63834 8.67388ZM8.305 9.34055H10.9717C11.3399 9.34055 11.6383 9.04207 11.6383 8.67388C11.6383 8.30569 11.3399 8.00722 10.9717 8.00722H8.97167V6.00722C8.97167 5.63903 8.67319 5.34055 8.305 5.34055C7.93681 5.34055 7.63834 5.63903 7.63834 6.00722V8.67388C7.63834 9.04207 7.93681 9.34055 8.305 9.34055Z" fill="#8BACD9"/>
            </svg>

            <p class="caption">3 days left</p>
          </div>
        </div>

        <div class="divider"></div>

        <div class="author">
          <img class="avatar" src="@/assets/img/image-avatar.png" alt="Author avatar">

          <p class="caption"><span>Creation of</span> Jules Wyvern</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  head() {
    return {
      title: {
        inner: 'Home'
      },
      meta: [
        {
          name: 'description',
          content: `${this.appTitle} home page`,
          id: 'desc'
        }
      ]
    }
  },
  computed: mapState('app', ['appTitle'])
}
</script>

<style lang="scss" scoped>
@import '../theme/variables';
@import '../theme/typography';

.page-wrapper {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100%;
  padding-left: 24px;
  padding-right: 24px;

  .card {
    width: 100%;
    max-width: 350px;
    padding: 24px 24px 32px;
    background: $darkBlue2;
    box-shadow: 0 25px 50px rgba(0, 0, 0, 0.0952917);
    border-radius: 15px;

    .image-box {
      position: relative;
      overflow: hidden;
      margin-bottom: 24px;
      border-radius: 8px;
      cursor: pointer;

      &:before {
        content: '';
        position: absolute;
        inset: 0;
        width: 100%;
        height: 100%;
        border-radius: 8px;
        background: $cyan;
        opacity: 0;
        mix-blend-mode: normal;
        transition: all .4s ease-in-out;
      }

      &:after {
        content: '';
        position: absolute;
        top: 50%;
        left: 50%;
        z-index: 1;
        width: 48px;
        height: 48px;
        background-image: url('data:image/svg+xml,<svg width="48" height="48" viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" clip-rule="evenodd" d="M24 9C14 9 5.46 15.22 2 24C5.46 32.78 14 39 24 39C34.01 39 42.54 32.78 46 24C42.54 15.22 34.01 9 24 9ZM24 34C18.48 34 14 29.52 14 24C14 18.48 18.48 14 24 14C29.52 14 34 18.48 34 24C34 29.52 29.52 34 24 34ZM18 24C18 20.69 20.69 18 24 18C27.31 18 30 20.69 30 24C30 27.31 27.31 30 24 30C20.69 30 18 27.31 18 24Z" fill="white"/></svg>');
        background-repeat: no-repeat;
        opacity: 0;
        transition: all .4s ease-in-out;
        transform: translate(-50%, -50%);
      }

      &:hover {
        &:before {
          opacity: 0.5;
        }

        &:after {
          opacity: 1;
        }
      }
    }

    .heading {
      margin-bottom: 16px;
      color: $white;
      transition: all .4s ease-in-out;
      cursor: pointer;

      &:hover {
        color: $cyan;
      }
    }

    .body {
      margin-bottom: 24px;
      color: $softBlue;
    }

    .row {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 24px;
    }

    .price {
      display: flex;
      align-items: center;

      svg {
        margin-right: 6.48px;
      }

      .caption {
        color: $cyan;
      }
    }

    .timer {
      display: flex;
      align-items: center;

      svg {
        margin-right: 7.7px;
      }

      .caption {
        color: $softBlue;
      }
    }

    .divider {
      width: 100%;
      height: 1px;
      margin-bottom: 16px;
      background: $darkBlue3;
    }

    .author {
      display: flex;
      align-items: center;

      .avatar {
        width: 33px;
        margin-right: 16px;
        border-radius: 50%;
        border: 1px solid $white;
      }

      .caption {
        color: $white;
        transition: all .4s ease-in-out;
        cursor: pointer;

        &:hover {
          color: $cyan;
        }

        span {
          color: $softBlue;
        }
      }
    }
  }
}
</style>
