<!--Scrip-->
<script lang="ts">
    const nameSrc: string = 'static/ELLWOOD.png';
</script>

<!--Markdown-->
<html>
<div class="content">
    <a href="/"><img src="{nameSrc}" alt="KEANU ELLWOOD" class="landing-header"></a>
</div>
</html>

<!--Styles-->
<style lang="scss">
  html {
    background: url(./static/images/landingLg.png) no-repeat center center fixed;
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    height: 100%;
    width: 100%;
  }

  .content {
    display: flex;
    justify-content: flex-start;
    align-items: center;

    & .landing-header {
      margin: 50px 50px;
    }
  }

  @media only screen and (max-width: 1200px) {
    html {
      background: url(./static/images/landingSm.png) no-repeat center center fixed !important;
      -webkit-background-size: cover;
      -moz-background-size: cover;
      -o-background-size: cover;
      background-size: cover;
    }
    .content {
      & .landing-header {
        width: 50%;
      }
    }
  }

  @media only screen and (max-width: 900px) {
    .content {
      & .landing-header {
        width: 100%;
      }
    }
  }
</style>