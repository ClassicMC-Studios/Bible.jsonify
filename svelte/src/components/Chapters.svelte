<script>
  export let chapter,book,translation;
  import kjv from '../translations/kjv.json';
  import nrsv from '../translations/nrsv.json';
  import bbe from '../translations/bbe.json';
  import nkjv from '../translations/nkjv.json';
</script>
{#if translation == "nrsv"}
    {#each nrsv[0].chapters[chapter] as verse,i}
      <sup>{i+1}</sup>{verse}<br/>
    {/each}
    {:else if translation == "kjv"}
    {#each kjv[book].chapters[chapter] as verse,i}
      <sup>{i+1}</sup>{verse}<br/>
    {/each}
    {:else if translation == "bbe"}
    {#each bbe[book].chapters[chapter] as verse,i}
      <sup>{i+1}</sup>{verse}<br/>
    {/each}
    {:else if translation == "nkjv"}
    {#each bbe[book].chapters[chapter] as verse,i}
      <sup>{i+1}</sup>{nkjv.books[book].chapters[chapter].verses[i].text}<br/>
    {/each}
  {/if}
