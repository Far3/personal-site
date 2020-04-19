---
title: Expand Collapse toggle button.
summary: "How to create an expand/collapse toggle button with bootstrap."
date: 2016-04-14
tags: [bootstrap, css]
---

<p>
I really really enjoy bootstrap. I use it constantly at work and it solves a lot of problems that Front-End Dev’s have had for a while. Probably the biggest one is its grid system, but it’s also got build in JavaScript components. I recently used <strong>Collapse.js</strong> to create an expand/collapse functionality so the user can view the entire news article or just the teaser.  
</p>



<p> 
  You can find more about <strong>Collapse.js</strong> <a href="http://getbootstrap.com/javascript/#collapse" target="_blank">here</a>
</p>

It needs a few important things to work.

 1. A container of what you want to show hide and that container must have an ID. In my case it was `id="article-1-expanded"`
 2. Set the class of that container to `class=”collapse”`
 3. A Button that toggles the show/hide functionality that must have.
    * `data-toggle=”collapse”`
    * `data-target=”Must match ID in step 1"`
    
    
    {% codeblock html %}

    <li class="media" id="article-1">
      <h3 class="h3 media-heading">This Is a News Article</h3>
      <div class="text-muted small">
        Wednesday, March 16, 2016 | By <a href="javascript:void(0);">Franklyn Roth</a></div>
      <p>
        ua. Ut enim ad minim veniam, quis nostrud exercitation ullamco quis nostrud.
      </p>
      <div id="article-1-expanded" class="collapse">
        <p>
          et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo.
        </p>
      </div>
      <button class="btn btn-link btn-toggle collapsed" data-toggle="collapse" data-target="#article-1-expanded"><span class="sr-only">Expand to full article</span></button>
    </li>
        {% endcodeblock %}


In the CSS I am switching the content to display + Expand/- Collapse with: 
<img src="/images/btn-toggle.PNG" alt="CSS Code of content: '+Expand' " />  
It could probably have been done with JavaScript/jQuery, but CSS makes it easy with a one liner and that lets you leverage Collapse.js which is already written for you by the smart people at Bootstrap.

Naming the class took me a while. I eventually settled on btn-toggle because...

1. It’s a button at the end of the day.
2. Its main purpose is to toggle and it can be added to the Buttons.less file as a modifier.  


Bonus: Add in `<span class=”sr-only”>Expand to full article</span>` so that a user with a screen reader knows what the functionality of the button is.
The entire code  and working example can be viewed at the codepen below.
<p data-height="500" data-theme-id="0" data-slug-hash="wGyVQQ" data-default-tab="result" data-user="franklynroth" data-embed-version="2" class="codepen">See the Pen <a href="http://codepen.io/franklynroth/pen/wGyVQQ/">wGyVQQ</a> by Franklyn (<a href="http://codepen.io/franklynroth">@franklynroth</a>) on <a href="http://codepen.io">CodePen</a>.</p>
<script async src="//assets.codepen.io/assets/embed/ei.js"></script>