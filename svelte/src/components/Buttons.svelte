<script>
  export let transfer,close;
  let book = 0;
  function gen(){book=0;transfer(book);close()}
  function exo(){book=1;transfer(book);close()}
  function lev(){book=2;transfer(book);close()}
  function num(){book=3;transfer(book);close()}
  function deu(){book=4;transfer(book);close()}
  function jos(){book=5;transfer(book);close()}
  function jud(){book=6;transfer(book);close()}
  function rut(){book=7;transfer(book);close()}
  function samone(){book=8;transfer(book);close()}
  function samtwo(){book=9;transfer(book);close()}
</script>
<style>
  .small{font-size: 12px;text-align: left;}
  *{font-family: sans-serif;font-weight: 100;}
</style>
<button class="bc-text-white small bc-black bc-button-10 bc-r-0 bc-w-100">
  <em class="bc-text-gray">Pentateuch</em>
</button>
<button on:click={gen} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  Genesis
</button><br/>
<button on:click={exo} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  Exodus
</button><br/>
<button on:click={lev} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  Leviticus
</button><br/>
<button on:click={num} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  Numbers
</button><br/>
<button on:click={deu} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  Deuteronomy
</button><br/>
<button on:click={jos} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  Joshua
</button><br/>
<button on:click={jud} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  Judges
</button><br/>
<button on:click={rut} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  Ruth
</button><br/>
<button on:click={samone} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  1st Samuel
</button><br/>
<button on:click={samtwo} class="bc-black bc-text-white bc-hover-gray bc-button-10 bc-r-0 bc-w-100">
  2nd Samuel
</button>
