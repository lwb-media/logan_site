<script lang="ts">
 import { onMount } from 'svelte';

 export let url: string;

 onMount(() => {
   const script = document.createElement('script');
   script.src = 'https://assets.calendly.com/assets/external/widget.js';
   script.async = true;
   document.body.appendChild(script);
 });
//  
</script>

<div
 class="calendly-inline-widget"
 id="calendly"
 data-url={url}
 style="min-width:320px;height:100vh;"
></div>