# CSS hack

A CSS hack is a coding technique used to hide or show CSS markup depending on the browser, version number, or capabilities. Browsers have different interpretations of CSS behavior and different levels of support for the W3C standards. [Wikipedia](https://en.wikipedia.org/wiki/CSS_hack)

```
<style>
  .dynamic-block
  { /* Default for Chrome and others */
    color: #fff;
    background: #000;
  } /* Override for Safari */
  .dynamic-block.safari {
    color: #000;
    background: #fff;
  }
</style>

<div class="dynamic-block">
  This is a dynamic block. Look at this block in Chrome and Safari browser. What's the difference?
</div>

<script>
  // Function to detect Safari
  function isSafari() {
    return /^((?!chrome|android).)*safari/i.test(navigator.userAgent);
  }

  // Apply Safari-specific class if needed
  if (isSafari()) {
    document.querySelector('.dynamic-block').classList.add('safari');
  }
</script>
```
