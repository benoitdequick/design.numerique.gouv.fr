<template>
  <div>

    <header>
      <g-link class="header__logos" to="/" title="DesignGouv - Retour à l'accueil">
        <LogoRF class="header__logo-rf" role="img" title="Logo Républiqe Française"/>
        <LogoDG class="header__logo-dg" role="img" title="Logo DesignGouv"/>
      </g-link>

      <nav>
        <Menu />
      </nav>
    </header>

    <main class="layout">
      <slot/>
      <Newsletter />
    </main>

    <footer>

      <g-link to="/" title="DesignGouv - Retour à l'accueil">
        <LogoRF class="footer__logo-rf" role="img" title="Logo République Française" />
      </g-link>

      <div class="footer__content">

        <div class="footer__description">
          <g-link to="/" title="DesignGouv - Retour à l'accueil">
            <LogoDG class="footer__logo-dg" role="img" title="Logo DesignGouv" />
          </g-link>
          <p>
            DesignGouv est propulsé par la <a href="https://numerique.gouv.fr" target="_blank">direction interministérielle du numérique</a>.</br>
            Le <a href="https://github.com/DISIC/design.numerique.gouv.fr" target="_blank">code source</a> est disponible en licence libre.
          </p>
        </div>

        <div class="footer__websites">
          <div>
            DesignGouv
            <ul>
              <li><g-link to="/equipe/">Notre équipe</g-link></li>
              <li><a href="https://twitter.com/design_gouv" target="_blank">
                Twitter <font-awesome :icon="['fab', 'twitter']"/>
                </a></li>
              <li><a href="mailto:contact@design.numerique.gouv.fr" target="_blank">
                  Contact <font-awesome :icon="['fas', 'paper-plane']" transform="shrink-2"/>
                  </a></li>
              <li><g-link to="/recrutement/">Recrutement</g-link></li>
              <li><g-link to="/misc/accessibilite/">Accessibilité</g-link></li>
              <li><g-link to="/misc/donnees-personnelles/">Données personnelles</g-link></li>
              <li><g-link to="/misc/mentions-legales/">Mentions légales</g-link></li>
            </ul>
          </div>
          <div>
            Autres services
            <ul>
              <li><a href="https://observatoire.numerique.gouv.fr" target="_blank">L'observatoire du numérique</a></li>
              <li><a href="https://demarches-simplifiees.fr" target="_blank">Demarches simplifiées</a></li>
              <li><a href="https://franceconnect.gouv.fr" target="_blank">FranceConnect</a></li>
              <li><a href="https://voxusagers.gouv.fr" target="_blank">Voxusagers</a></li>
            </ul>
          </div>
          <div>
            Autres univers
            <ul>
              <li><a href="https://etalab.gouv.fr" target="_blank">etalab.gouv.fr</a></li>
              <li><a href="https://beta.gouv.fr" target="_blank">beta.gouv.fr</a></li>
              <li><a href="https://data.gouv.fr" target="_blank">data.gouv.fr</a></li>
              <li><a href="https://api.gouv.fr" target="_blank">api.gouv.fr</a></li>
            </ul>
          </div>
        </div>

        <div class="footer__sites-publics">
          <span>Les sites publics :</span>
          <a href="https://elysee.fr" target="_blank">Elysee.fr</a>
          <a href="https://gouvernement.fr" target="_blank">gouvernement.fr</a>
          <a href="https://www.service-public.fr" target="_blank">service-public.fr</a>
          <a href="https://legifrance.gouv.fr" target="_blank">legifrance.gouv.fr</a>
        </div>
      </div>

    </footer>

  </div>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
import Menu from "~/components/Menu.vue"
import Newsletter from "~/components/Newsletter.vue"
import LogoRF from "~/assets/images/logoRF.svg"
import LogoDG from "~/assets/images/logoDG.svg"

export default {
  components: {
    Menu,
    Newsletter,
    LogoRF,
    LogoDG,
  },
  props: {
    logoLarge: {
      default: false,
      type: Boolean
    },
  }
}
</script>

<style lang="scss">

  @import "src/assets/scss/_vars.scss";

  @font-face {
    font-family: "Marianne";
    font-weight: 400;
    src: url("../assets/fonts/Marianne/Marianne-Regular.ttf") format("ttf"),
         url("../assets/fonts/Marianne/Marianne-Regular.woff") format("woff2"),
         url("../assets/fonts/Marianne/Marianne-Regular.woff2") format("woff");
    font-display: fallback;
  }

  @font-face {
    font-family: "Marianne";
    font-weight: 700;
    src: url("../assets/fonts/Marianne/Marianne-Bold.ttf") format("ttf"),
         url("../assets/fonts/Marianne/Marianne-Bold.woff") format("woff2"),
         url("../assets/fonts/Marianne/Marianne-Bold.woff2") format("woff");
    font-display: fallback;
  }

  @font-face {
    font-family: "Marianne";
    font-weight: 800;
    src: url("../assets/fonts/Marianne/Marianne-ExtraBold.ttf") format("ttf"),
         url("../assets/fonts/Marianne/Marianne-ExtraBold.woff") format("woff2"),
         url("../assets/fonts/Marianne/Marianne-ExtraBold.woff2") format("woff");
    font-display: fallback;
  }

  @font-face {
    font-family: "Inter";
    font-style: normal;
    font-weight: 400;
    src: url("../assets/fonts/Inter/Inter-Regular-Reduced.woff") format("woff2"),
         url("../assets/fonts/Inter/Inter-Regular-Reduced.woff2") format("woff");
    font-display: fallback;
  }

  @font-face {
    font-family: "Inter";
    font-style: italic;
    font-weight: 400;
    src: url("../assets/fonts/Inter/Inter-Italic-Reduced.woff") format("woff2"),
         url("../assets/fonts/Inter/Inter-Italic-Reduced.woff2") format("woff");
    font-display: fallback;
  }

  @font-face {
    font-family: "Inter";
    font-style: normal;
    font-weight: 500;
    src: url("../assets/fonts/Inter/Inter-Medium-Reduced.woff") format("woff2"),
         url("../assets/fonts/Inter/Inter-Medium-Reduced.woff2") format("woff");
    font-display: fallback;
  }

  @font-face {
    font-family: "Inter";
    font-style: italic;
    font-weight: 500;
    src: url("../assets/fonts/Inter/Inter-MediumItalic-Reduced.woff") format("woff2"),
         url("../assets/fonts/Inter/Inter-MediumItalic-Reduced.woff2") format("woff");
    font-display: fallback;
  }

  @font-face {
    font-family: "Inter";
    font-style: normal;
    font-weight: 700;
    src: url("../assets/fonts/Inter/Inter-Bold-Reduced.woff") format("woff2"),
         url("../assets/fonts/Inter/Inter-Bold-Reduced.woff2") format("woff");
    font-display: fallback;
  }

  @font-face {
    font-family: "Inter";
    font-style: italic;
    font-weight: 700;
    src: url("../assets/fonts/Inter/Inter-BoldItalic-Reduced.woff") format("woff2"),
         url("../assets/fonts/Inter/Inter-BoldItalic-Reduced.woff2") format("woff");
    font-display: fallback;
  }

  .layout {
    max-width: 760px;
    margin: 0 auto;
    padding: 0 30px;

    @media only screen and (max-width: $mobile-max-width) {
      padding: 0 12px;
    }
  }

  header {
    display: flex;
    justify-content: space-between;
    align-items: center;

    .header__logos {
      display: flex;
      justify-content: flex-start;
      align-items: center;
      border: none;
    }

    .header__logo-rf {
      flex-shrink: 0;
      width: 121px;
      margin: 30px 40px 0px 30px;

      @media only screen and (max-width: $mobile-max-width) {
        width: 64px;
        margin: 12px 24px 0px 12px;
      }
    }

    .header__logo-dg {
      max-width: 260px;
      width: 100%;
      padding-top: 16px;

      @media only screen and (max-width: $mobile-max-width) {
        width: 160px;
        padding-top: 4px;
      }
    }

    nav {
      padding: 7px 30px 0 30px;

      @media only screen and (max-width: $mobile-max-width) {
        padding: 0px 12px;
      }
    }
  }

  footer {
    padding: 20px 20px 24px 20px;
    margin-top: 120px;
    border-top: 6px solid $gray;
    color: $black;
    display: flex;
    justify-content: center;

    a {
      border: none;
    }

    @media only screen and (max-width: $mobile-max-width) {
      padding: 20px 12px 24px 12px;
      margin-top: 64px;
      display: inline-block;
    }

    .footer__logo-rf {
      width: 121px;
      margin: 20px;

      @media only screen and (max-width: $mobile-max-width) {
        margin: 0 0 20px 0;
      }
    }

    .footer__logo-dg {
      width: 260px;
      max-width: 80%;
    }

    .footer__content {
      margin: 18px 40px 0px 40px;

      @media only screen and (max-width: $mobile-max-width) {
        margin: 0;
      }
    }

    .footer__description {
      max-width: 640px;
    }

    .footer__websites {
      margin: 32px 0 8px 0;
      display: flex;
      flex-flow: row wrap;
      justify-content: space-between;

      div {
        margin-right: 48px;
        margin-bottom: 16px;
      }

      ul {
        padding: 0;

        li {
          list-style-type: none;
        }
      }
    }

    .footer__sites-publics {
      font-size: .875em;
      display: flex;
      flex-direction: row;
      flex-wrap: wrap;

      a, span {
        margin-right: 12px;
      }
    }
  }

</style>
