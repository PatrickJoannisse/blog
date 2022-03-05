<template>
  <span
    class="
      inline-flex
      items-center
      px-2.5
      py-0.5
      rounded-md
      font-medium
      bg-[#3f37c9]
      hover:bg-[#4361ee]
      text-white
      transition
      duration-150
    "
    ><slot
  /></span>
</template>

<script>
export default {
  name: "Tag",
};
</script>
