<template>
  <header>
    <nav class="flex max-w-screen-lg px-4 py-4 mx-auto space-x-8">
      <NavbarNavLink to="/">Home</NavbarNavLink>
      <NavbarNavLink to="/about">About</NavbarNavLink>
      <NavbarNavLink to="#"
        ><svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-4 w-4 mt-0.5 mr-1"
          fill="none"
          viewBox="0 0 24 24"
          stroke="currentColor"
          stroke-width="2"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            d="M6 5c7.18 0 13 5.82 13 13M6 11a7 7 0 017 7m-6 0a1 1 0 11-2 0 1 1 0 012 0z"
          />
        </svg>
        RSS</NavbarNavLink
      >
    </nav>
  </header>
</template>

<script>
export default {
  name: "Navbar",
};
</script>
