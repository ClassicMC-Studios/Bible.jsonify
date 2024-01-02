<script>
  import kjv from './translations/kjv.json';
  import nrsv from './translations/nrsv.json';
  import bbe from './translations/bbe.json';
  import nkjv from './translations/nkjv.json'
  import Buttons from './components/Buttons.svelte'
  import Chapter from './components/Chapter.svelte'
  import { get } from 'svelte/store';
  let selected = true;
  let translation= "kjv";
  let translector = true;
  let book = 0;
  function showSelector(){if(selected){selected=false;translector=true;}else{selected=true}}
  function showSelectortrans(){if(translector){translector=false;selected=true;}else{translector=true}}
  function nrsvV(){translation = "nrsv";selected= true}
  function kjvV(){translation = "kjv";selected= true;}
  function bbeV(){translation = "bbe";selected= true;}
  function nkjvV(){translation = "nkjv";selected=true;}
  function getBook(dsus=0){book=dsus;}
  function closed(){translector=true;selected=true;}
</script>
<style>
  *{font-family: sans-serif;font-weight: 100;}
main{margin-left: 10%;margin-right: 10%;}
.dsus{display: none;}
.bc-w-custom{width:172.9px;}
.toldin{
  display: none;
}
.tellin{
  transition: 0.3s;
}
.tellin:hover > .toldin{
  display: block;
  cursor: not-allowed;
}
.tellin:hover > s{
  display: none;
}
h2{color:gray;}
</style>
<main class="bc-text-align"><br/>
  <h1>Bibel++</h1>
  <p><b>DEBUG</b>: <b>TranslationSelect</b>:{selected}, <b>Translation</b>:{translation}, <b>BookSelect</b>:{translector}, <b>Book</b>:{book}</p>
  <h3>As simple as the bible comes</h3><br/>
  <button class="bc-black bc-hover-gray bc-r-0" on:click={showSelector}>Translation</button>&nbsp;&nbsp;<button on:click={showSelectortrans} class="bc-black bc-hover-gray bc-r-0">&nbsp;&nbsp;&nbsp;&nbsp;Book&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</button>
  <div class:dsus={selected} class="bc-black bc-r-0 bc-text-white bc-w-custom bc-true-half">
    <button class="tellin bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
      <s class="bc-text-white">NRSV</s>
      <span class="toldin"><s style="color:white">WIP</s></span>
    </button><br/>
    <button on:click={kjvV} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
      KJV
    </button><br/>
    <button on:click={bbeV} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
      BBE
    </button>
    <button on:click={nkjvV} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
      NKJV
    </button>
  </div>
  <div class:dsus={translector} class="bc-black bc-r-0 bc-text-white bc-w-custom bc-true-half">
    <Buttons transfer={getBook} close={closed}/>
  </div><br/><br/>
  <div class="bc-border-bottom">dsus</div>
  <br/><br/>
  {#each kjv[book].chapters as length,i}
    {#if i == 0}
      <h1>{kjv[book].name}</h1>
      <h2>{translation.toUpperCase()}</h2>
    {/if}
    <br/>
    <h1>Chapter {i+1}</h1>
    <br/>
    <Chapter chapter={i} book={book} translation={translation}/>  
  {/each}<br/>
</main>
