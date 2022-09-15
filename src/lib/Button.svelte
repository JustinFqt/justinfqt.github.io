<script lang="ts">
  export let url: string;
  export let text: string;
  export let logo: string = "";
</script>

<a
  class="inline-block mx-2 px-8 py-3 text-sm font-medium text-blue-900 transition border border-current rounded hover:scale-110 hover:rotate-2 active:text-blue-500 focus:outline-none focus:ring dark:text-white"
  href={url}
>
  {logo}
  {text}
</a>
