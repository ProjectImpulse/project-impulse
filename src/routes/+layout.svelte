<script lang='ts'>
  import '../app.css';
  import { page } from '$app/stores';
  import { Navbar, NavBrand, NavLi, NavUl, NavHamburger } from 'flowbite-svelte';
  import { Footer, FooterBrand, FooterCopyright, FooterIcon, FooterLink, FooterLinkGroup } from 'flowbite-svelte';
  $: activeUrl = $page.url.pathname;
</script>

<div class="app">
  <Navbar let:NavContainer>
      <NavContainer class="navbar rounded-lg border bg-white px-8 py-8 dark:bg-gray-600">
          <NavBrand href="/">
              <img src="/images/logo-assets.png" class="sm:h-200 me-3 h-20" alt="PI Logo" />
          </NavBrand>
          <NavHamburger></NavHamburger>
          <NavUl {activeUrl} class="">
            <NavLi href="/people" style="font-size: 25px; font-family: 'Bruno Ace', sans-serif;">People</NavLi>
            <NavLi href="https://blog.kuberapp.net/" style="font-size: 25px; font-family: 'Bruno Ace', sans-serif;">Blog</NavLi>
          </NavUl>
          <NavUl>
            <NavLi href="/contact">
              <button type="button" class="px-5 py-3 text-base font-medium text-center inline-flex items-center text-white bg-[#050708] rounded-lg hover:bg-blue-800 focus:ring-4 focus:outline-none focus:ring-blue-300 dark:bg-blue-600 dark:hover:bg-blue-700 dark:focus:ring-blue-800">
              <svg class="w-4 h-4 text-white me-2" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 20 16">
              <path d="m10.036 8.278 9.258-7.79A1.979 1.979 0 0 0 18 0H2A1.987 1.987 0 0 0 .641.541l9.395 7.737Z"/>
              <path d="M11.241 9.817c-.36.275-.801.425-1.255.427-.428 0-.845-.138-1.187-.395L0 2.6V14a2 2 0 0 0 2 2h16a2 2 0 0 0 2-2V2.5l-8.759 7.317Z"/>
              </svg>
              Talk to Us
              </button>
            </NavLi>
        </NavUl>
      </NavContainer>
  </Navbar>

  <main>
      <slot></slot>
  </main>

  <Footer>
    <Navbar let:NavContainer>
      <NavContainer class="footer-background rounded-lg border bg-white px-8 py-8 dark:bg-gray-600">
        <FooterBrand href="/">
          <img src="/images/logo-assets.png" class="sm:h-200 me-3 h-40" alt="PI Logo" />
        </FooterBrand>
        <div class="footer-text grid grid-cols-2 gap-8 sm:gap-6 sm:grid-cols-3">
          <div>
            <FooterLinkGroup>
              <FooterLink liClass="mb-4" href="/https://github.com/ProjectImpulse" style="color: black;" >Github</FooterLink>
              <FooterLink liClass="mb-4" href="/" style="color: black;" >Twitter</FooterLink>
            </FooterLinkGroup>
          </div>
          <div>
            <FooterLinkGroup>
              <FooterLink liClass="mb-4" href="/" style="color: black;" >Youtube</FooterLink>
              <FooterLink liClass="mb-4" href="/" style="color: black;" >3am BS</FooterLink>
            </FooterLinkGroup>
          </div>
        </div>
        <hr class="my-6 border-gray-200 sm:mx-auto lg:my-12 dark:border-gray-700" />
        <FooterCopyright style="color: black;" href="https://projectimpulse.pages.dev/" by="Project Impulse"></FooterCopyright>
      </NavContainer>
    </Navbar>
  </Footer>  
</div>

<style>
  .footer-text {
    font-size: 25px;
  }

</style>