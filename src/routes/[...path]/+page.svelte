<script>
  import { SliceZone } from '@prismicio/svelte'
  import * as prismicH from '@prismicio/helpers';

  import { dev } from '$app/environment'

  import * as components from '$lib/slices'

  export let data
  console.log("Data",data)
</script>
<svelte:head>
	<title>{prismicH.asText(data?.document?.data?.title)}</title>
</svelte:head>

{#if !data.document}
  <pre>ok looks like you need some data 👀</pre>
{:else}
  <SliceZone slices={data?.document?.data?.body} {components} {dev} />
{/if}
