<template>
  <footer class="block-above-product">
    <div class="footer-content">
      <div class="container">
        <div class="row footer-menu">
          <div v-if="settings.showHelp" class="col-md-3 col-6 order-2 order-md-1">
            <h3>Help</h3>
            <ul class="footer-links list-unstyled">
              <li v-for="helpItem in settings.helpItems" :key="helpItem.name">
                <a :href="helpItem.href">{{helpItem.name}}</a>
              </li>
            </ul>
          </div>
          <div v-if="settings.showAbout" class="col-md-3 col-6 order-2 order-md-1">
            <h3>About</h3>
            <ul class="footer-links list-unstyled">
              <li v-for="aboutItem in settings.aboutItems" :key="aboutItem.name">
                <a :href="aboutItem.href">{{aboutItem.name}}</a>
              </li>
            </ul>
          </div>
          <div class="offset-lg-1 col-lg-5 col-md-6 col-sm-12 order-1 order-md-3 pb-5 pb-md-0">
            <form
              class="validate newsletter-form"
              target="_blank"
              novalidate
            >
              <h3>Be a part of the CG Community</h3>
              <p class="font-weight-light">
                There is always something new happening in our Copenhagen Grooming beard
                growing community. Subscribe to our newsletter for the latest growth hacking videos, special offers and other
                juicy stuff from us below.
              </p>
              <div class="input-group input-group-lg pt-4">
                <input
                  type="email"
                  name="email"
                  class="form-control bg-dark required email"
                  placeholder="Your email address"
                  aria-label="Your email address"
                />
                <input
                  type="submit"
                  value="Sign Up"
                  name="subscribe"
                  class="btn filled inverted small form-control"
                />
              </div>
              <div style="position: absolute; left: -5000px;" aria-hidden="true">
                <input type="text" name="vXpqbWHS5zIa3FUG" autocomplete="nope" tabindex="-1" value />
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
    <div class="container footer-info text-center">
      <div class="row align-items-center">
        <div class="col-sm-6 col-lg-3 order-4 order-sm-1 footer-info-item">
          <div class="footer-info-copyright">©&nbsp;Copyright&nbsp;2019 Copenhagen&nbsp;Grooming</div>
        </div>
        <div
          v-if="settings.showSocial"
          class="col-sm-6 col-lg-3 order-2 order-sm-2 col-6 footer-info-item social-networks"
        >
          <span class="d-none d-sm-inline-block">Follow us</span>
          <a
            v-for="socialItem in settings.socialItems"
            :key="socialItem.name"
            :href="socialItem.href"
            target="_blank"
          >
            <i :class="socialItem.icon"></i>
          </a>
        </div>
        <div
          class="col-sm-6 col-lg-3 order-2 order-sm-3 col-6 footer-info-item footer-info-payment"
        >
          <span class="d-none d-sm-inline-block">Payment</span>
          <img
            class="img-fluid"
            src="image/catalog/logo/creditcard_dk.png"
            alt="image/catalog/logo/creditcard_dk.png"
          />
          <img
            class="img-fluid"
            src="image/catalog/logo/mobilepay.png"
            alt="image/catalog/logo/mobilepay.png"
          />
        </div>
        <div class="col-sm-6 col-lg-3 order-1 order-sm-4 country-change-html footer-info-item">
          <script>
  <!-- $(document).trigger("country:detected", "dk"); -->
          </script>
          <span class="text_country_shipping_to">Shipping to</span>:
          <span class="shipping-country">Denmark</span>
          <a class="country-change" href="javascript: void(0);">(Change)</a>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  props: {
    settings: {
      type: Object,
      default: () => {
        return {
          showHelp: true,
          helpItems: [
            { href: '/growth-guarantee', name: 'Growth Guarantee' },
            { href: '/terms-of-service', name: 'Terms of Service' },
            { href: '/delivery-and-return', name: 'Delivery & Return' },
            { href: '/payment-terms', name: 'Payment' },
            { href: '/track-my-order', name: 'Track My Order' }
          ],
          showAbout: true,
          aboutItems: [
            { href: '/about', name: 'About Us' },
            { href: '/contact', name: 'Contact' },
            { href: '/help', name: 'Need help bud?' },
            { href: '/careers', name: 'Careers' }
          ],
          showSocial: true,
          socialItems: [
            {
              name: 'facebook',
              icon: 'icon-facebook',
              href: 'https://www.facebook.com/CopenhagenGrooming'
            },
            {
              name: 'instagram',
              icon: 'icon-instagram',
              href: 'https://www.instagram.com/copenhagengrooming'
            },
            {
              name: 'youtube',
              icon: 'icon-youtube',
              href: 'https://www.youtube.com/channel/UCsLnoe_Fw2Dq-ffApPJvmSQ'
            }
          ]
        };
      }
    }
  }
};
</script>

<style lang="scss" scoped>
@import "~/assets/styles/common.scss";

footer {
  font-family: "IBM Plex Sans", sans-serif;
  position: relative;
}

.footer-content {
  background-color: $dark;
  color: $white;

  @include media-breakpoint-down(md) {
    > .container {
      padding: 0 25px;
    }
  }
}

.footer-menu {
  padding: 60px 0;

  @include media-breakpoint-up(lg) {
    padding: 130px 0;
  }

  h3 {
    font-size: 18px;
    line-height: 36px;
    color: $white;
    font-weight: 500;

    @include media-breakpoint-up(md) {
      font-size: 22px;
    }
  }

  form {
    p {
      font-size: 12px;
      line-height: 15px;
      color: $white;
    }
    .form-control {
      color: $white;
      font-size: 15px;
      line-height: 19px;
      border-radius: 0;

      &:focus {
        color: $white;
        border-color: $white;
      }

      &[type="submit"] {
        max-width: 150px;
        color:$black;
      }

      @include media-breakpoint-down(md) {
        width: 100%;

        &[type="submit"] {
          width: 100%;
          max-width: inherit;
          height: 60px;
        }
      }
    }
  }
}

.footer-links {
  margin: 0;

  a {
    color: $white;
    font-size: 12px;
    line-height: 36px;
    text-decoration: none;
  }
  @include media-breakpoint-up(md) {
    font-size: 15px;
  }
}

.footer-info {
  font-size: 14px;
  background-color: $white;

  > .row {
    padding: 18px 0;
  }

  .footer-info-item {
    @include media-breakpoint-down(md) {
      .social-networks, .footer-info-payment{
        margin: 20px 0;
        border-right: 1px solid #d8d8d8;
      }
    }
    @include media-breakpoint-down(lg) {
      line-height: 36px;
    }
    @include media-breakpoint-up(lg) {
      border-right: 1px solid #d8d8d8;

      &:first-child {
        text-align: left;
      }

      &:last-child {
        text-align: right;
        border: none;
      }
    }
  }

  .social-networks {
    > span {
      margin-right: 15px;
    }
    > a {
      color: $dark;
      padding: 0 8px;
    }
  }

  .footer-info-copyright {
    @include media-breakpoint-down(lg) {
      line-height: 21px;
    }
  }

  .country-change {
    color: #2dc291;

    &.disabled {
      opacity: 1;
    }
  }

  .footer-info-payment {
    > span {
      margin-right: 15px;
    }
    > img {
      max-height: 28px;
      max-width: 75px;
    }
  }
}

.block-above-product {
  z-index: 1045;
}
</style>
