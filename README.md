# Bible in JSON

The Bible JSONify project is designed to allow *anyone* access to *any* bible version in JSON format.

The Bible JSONify project is headed by [@WestonSchnee](https://github.com/ClassicMC-Studios) 

> There are **3** Bible versions currently ready for use

1. NKJV *(alternate source code structure)*
2. KJV
3. BBE

> The next version in production is the **NRSV**

> Example code in html

```html
<!DOCTYPE html>
<html>
<style>
  *{font-family:sans-serif;font-weight:100;}
</style>
<body>

<h1>BibleJSONified</h1>
<p id="kjv">
  <!--KJV GOES HERE-->
</p>
<script type="module">
  import kjv from 'https://classicmc-studios.github.io/Bible.jsonify/jsonified/KJV.json' assert { type: 'json' };
  document.getElementById("kjv").innerHTML = `<sup>1</sup> ${kjv[0].chapters[0][0]} <sup>2</sup> ${kjv[0].chapters[0][1]}<br/> &nbsp;&nbsp;- ${kjv[0].name} 1:1-2`;
</script>

</body>
</html>

```
