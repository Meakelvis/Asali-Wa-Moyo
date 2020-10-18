<template>
  <div>
    <div class="w-10/12 lg:max-w-full lg:flex mx-auto my-4 border shadow-md">
      <div
        class="h-48 lg:h-auto lg:w-1/4 flex-none bg-cover text-center overflow-hidden"
        style="background-image: url('event.image_url')"
        title="Woman holding a mug"
      ></div>
      <div class="bg-white p-4 flex flex-col justify-between leading-normal">
        <div class="mb-8">
          <div class="text-gray-900 font-bold text-xl mb-2">
            {{ event.title }}
          </div>
          <p class="text-gray-700 text-base">
            {{ event.description }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["event"],
};
</script>