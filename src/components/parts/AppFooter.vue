<template>
  <footer class="bg-background-secondary body-font">
    <div
      class="
        container
        px-5
        py-10
        md:py-24
        mx-auto
        flex
        md:items-center
        lg:items-start
        md:flex-row md:flex-nowrap
        flex-wrap flex-col
      "
    >
      <div class="flex-grow flex flex-wrap md:text-left text-center">
        <div class="lg:w-3/4 md:w-1/2 w-full px-8">
          <h2 class="title-font text-lg font-medium mb-3">Sobre la web:</h2>
          <div class="mb-5">
            <p>
              Este es un espacio en el cual expongo mis reflexiones sobre algunas experiencia.
            </p>
          </div>
        </div>
      </div>
      <div
        class="
          w-64
          flex-shrink-0
          md:mx-0
          mx-auto
          mb-5
          md:-mb-5 md:mt-0
          mt-5
          text-center
          md:text-left
        "
      >
        <a
          class="
            flex
            title-font
            font-medium
            items-center
            md:justify-start
            justify-center
            text-gray-900
          "
        >
          <span class="site-logo"><site-logo /></span>
        </a>
        <p class="mt-2 text-sm">
          {{ $static.metadata.siteDescription }}
        </p>
      </div>
    </div>
    <div class="bg-background-tertiary">
      <div
        class="container mx-auto py-4 px-5 flex flex-wrap flex-col sm:flex-row"
      >
        <p class="text-sm text-center sm:text-left">
          {{ `© ${new Date().getFullYear()} ${$static.metadata.siteName}` }} —
          <a
            :href="$static.metadata.siteAuthorUrl"
            rel="noopener noreferrer"
            class="text-gray-500 ml-1"
            target="_blank"
            >{{ `@${$static.metadata.siteAuthor}` }}</a
          >
        </p>
      </div>
    </div>
  </footer>
</template>

<static-query>
query {
  metadata {
    siteName
    siteDescription
    siteAuthor
    siteAuthorUrl
  }
}
</static-query>

<script>
export default {
  components: {
    SiteLogo: () => import('~/components/SiteLogo.vue'),
  },
}
</script>
