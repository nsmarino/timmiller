<script>
  import { SliceZone } from '@prismicio/svelte'
  import { dev } from '$app/environment'

  import * as components from '$lib/slices'

  export let data
</script>

{#if !data.document}
  <pre>ok looks like you need some data 👀</pre>
{:else}
  <SliceZone slices={data?.document?.data?.body} {components} {dev} />
{/if}
