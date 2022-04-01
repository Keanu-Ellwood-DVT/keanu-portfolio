<!--Script-->
<script>
    import FaInstagram from 'svelte-icons/fa/FaInstagram.svelte';
    import {page} from '$app/stores';

    console.log($page);
    const nav = [
        {title: 'Work', path: '/work'},
        {title: 'About', path: '/about'},
        {title: 'Contact', path: '/contact'},
    ]
</script>

<!--Markdown-->
<div class="nav">
    <div class="logo">
        <a href="/"><img src="static/KE.png" alt="KEANU ELLWOOD"></a>
    </div>
    <div class="nav-items">
        {#each nav as navItem}
            <a class:active={$page?.url.pathname === navItem.path} href={navItem.path}>{@html navItem.title}</a>
        {/each}
        <a href="https://www.instagram.com/keanuellwood/" class="icon">
            <FaInstagram/>
        </a>
    </div>
</div>
<div class="footer">
    <p>Copyright © Keanu Ellwood Photography | All rights reserved. </p>
</div>
<slot></slot>

<!--Styles-->
<style lang=scss>
  .nav {
    display: flex;
    justify-content: center;
    gap: 20px;
    margin: 20px auto;

    & .logo {
      width: 60px;
      height: 60px;
      border: 5px solid #fff;

      & img {
        max-height: 100%;
      }
    }

    & .nav-items {
      font-family: Tahoma, sans-serif;
      display: flex;
      align-items: center;
      gap: 15px;

      & a {
        position: relative;
        color: #fff;
        font-size: 22px;
        text-decoration: none;

        &.active {
          border-bottom: 3px solid #fff;
        }

        &:not(:last-child)::before {
          content: '';
          position: absolute;
          width: 100%;
          height: 2px;
          border-radius: 2px;
          background-color: #fff;
          bottom: 0;
          left: 0;
          transform-origin: right;
          transform: scaleX(0);
          transition: transform .3s ease-in-out;
        }

        &:hover::before {
          transform-origin: left;
          transform: scaleX(1);
        }

        &.icon {
          width: 25px;
          height: 25px;
        }
      }
    }
  }

  .footer {
    position: fixed;
    left: 0;
    bottom: 0;
    width: 100%;
    color: rgba(255, 255, 255, 0.6);
    text-align: left;

    & p {
      margin: 20px 50px;
    }
  }

  @media only screen and (max-width: 1200px) {
    .footer {
      text-align: center;
    }
  }
</style>