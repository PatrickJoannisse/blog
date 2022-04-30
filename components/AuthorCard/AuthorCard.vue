<template>
  <div
    class="w-full p-3 my-6 bg-white rounded-lg shadow-md  md:p-6 md:flex md:space-x-6 dark:bg-gray-800"
  >
    <div class="inline-flex items-center w-full md:w-1/6">
      <img
        src="~/assets/img/me.png"
        class="w-40 mx-auto rounded-full ring-gray-100 ring-2"
        alt="Hey, that's a photo of me"
      />
    </div>
    <div class="md:w-5/6">
      <h2
        class="py-2 text-xl font-bold text-center  md:text-left md:text-3xl dark:text-white"
      >
        Hi! I'm Patrick Joannisse
      </h2>
      <p class="text-center dark:text-gray-400 md:text-left">
        I'm a senior software developer, public servant and overall geek. Lorem
        ipsum dolor, sit amet consectetur adipisicing elit. Aliquid iusto fugit
        quo consequatur atque optio, libero eveniet perferendis officiis magni
        omnis quae dignissimos esse, voluptatem at molestiae in! Cum, debitis!
      </p>
      <div class="flex items-center mt-6 -ml-2 space-x-4 md:space-x-2">
        <AuthorCardSocialLink href="https://twitter.com/MrJoannisse">
          <svg
            class="w-5 h-5 mt-0.5"
            fill="currentColor"
            viewBox="0 0 20 20"
            aria-hidden="true"
          >
            <path
              d="M6.29 18.251c7.547 0 11.675-6.253 11.675-11.675 0-.178 0-.355-.012-.53A8.348 8.348 0 0020 3.92a8.19 8.19 0 01-2.357.646 4.118 4.118 0 001.804-2.27 8.224 8.224 0 01-2.605.996 4.107 4.107 0 00-6.993 3.743 11.65 11.65 0 01-8.457-4.287 4.106 4.106 0 001.27 5.477A4.073 4.073 0 01.8 7.713v.052a4.105 4.105 0 003.292 4.022 4.095 4.095 0 01-1.853.07 4.108 4.108 0 003.834 2.85A8.233 8.233 0 010 16.407a11.616 11.616 0 006.29 1.84"
            />
          </svg>
          <span class="md:sr-only">Twitter</span>
        </AuthorCardSocialLink>
        <AuthorCardSocialLink href="http://linkedin.com/in/patrick-joannisse">
          <svg
            class="w-5 h-5 mt-0.5"
            viewBox="0 0 15 15"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path
              d="M2 1C1.44772 1 1 1.44772 1 2V13C1 13.5523 1.44772 14 2 14H13C13.5523 14 14 13.5523 14 13V2C14 1.44772 13.5523 1 13 1H2ZM3.05 6H4.95V12H3.05V6ZM5.075 4.005C5.075 4.59871 4.59371 5.08 4 5.08C3.4063 5.08 2.925 4.59871 2.925 4.005C2.925 3.41129 3.4063 2.93 4 2.93C4.59371 2.93 5.075 3.41129 5.075 4.005ZM12 8.35713C12 6.55208 10.8334 5.85033 9.67449 5.85033C9.29502 5.83163 8.91721 5.91119 8.57874 6.08107C8.32172 6.21007 8.05265 6.50523 7.84516 7.01853H7.79179V6.00044H6V12.0047H7.90616V8.8112C7.8786 8.48413 7.98327 8.06142 8.19741 7.80987C8.41156 7.55832 8.71789 7.49825 8.95015 7.46774H9.02258C9.62874 7.46774 10.0786 7.84301 10.0786 8.78868V12.0047H11.9847L12 8.35713Z"
              fill="currentColor"
              fill-rule="evenodd"
              clip-rule="evenodd"
            ></path>
          </svg>
        </AuthorCardSocialLink>
        <AuthorCardSocialLink href="https://github.com/PatrickJoannisse">
          <svg
            class="w-5 h-5 mt-0.5"
            fill="currentColor"
            viewBox="0 0 24 24"
            aria-hidden="true"
          >
            <path
              fill-rule="evenodd"
              d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504.5.092.682-.217.682-.483 0-.237-.008-.868-.013-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.029-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.379.202 2.398.1 2.651.64.7 1.028 1.595 1.028 2.688 0 3.848-2.339 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.019 10.019 0 0022 12.017C22 6.484 17.522 2 12 2z"
              clip-rule="evenodd"
            />
          </svg>
          <span class="md:sr-only">Github</span>
        </AuthorCardSocialLink>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AuthorCard",
};
</script>
