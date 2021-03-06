---
layout: "v2_fluid/docs_base"
version: "nightly"
versionHref: "/docs/v2"
path: ""
category: api
id: "{{Page | slugify}}"
title: "Page"
header_sub_title: "Function in module "
doc: "Page"
docType: "function"

---




<div class="improve-docs">
<a href='http://github.com/driftyco/ionic2/tree/master/ionic/config/decorators/page.ts#L1'>
View Source
</a>
&nbsp;
<a href='http://github.com/driftyco/ionic2/edit/master/ionic/config/decorators/page.ts#L1'>
Improve this doc
</a>
</div>





<h1 class="api-title">


Page






</h1>






<!-- description -->
<h2>Description</h2>

<p>For more information on how pages are created, see the <a href="../../components/nav/NavController/#creating_pages">NavController API reference</a></p>
<p>The Page decorator indicates that the decorated class is an Ionic
navigation component, meaning it can be navigated to using a NavController.</p>
<p>Pages have all <code>IONIC_DIRECTIVES</code>, which include all Ionic components and directives,
as well as Angular&#39;s <a href="https://angular.io/docs/js/latest/api/core/CORE_DIRECTIVES-const.html">CORE_DIRECTIVES</a>
and <a href="https://angular.io/docs/js/latest/api/core/FORM_DIRECTIVES-const.html">FORM_DIRECTIVES</a>,
already provided to them, so you only need to supply custom components and directives to your pages:</p>

<!-- @usage tag -->

<h2>Usage</h2>

<pre><code class="lang-ts">@Page({
  template: `
   &lt;ion-content&gt;
     I am a page!
   &lt;/ion-content&gt;
  `
})
class MyPage {}
</code></pre>
<p>Here <a href="../../../components/content/Content/">Content</a> will load because
it is in <code>IONIC_DIRECTIVES</code>, so there is no need to add a <code>directives</code> array.</p>
<p>Say you built a custom component that uses the an already exsiting Ionic component.
In this case, you would add <code>IONIC_DIRECTIVES</code> to your directives array.</p>
<pre><code class="lang-ts">import {IONIC_DIRECTIVES} from &#39;ionic/ionic&#39;;
@Component({
  selector: &#39;my-component&#39;
  template: `&lt;div class=&quot;my-style&quot;&gt;
                            &lt;ion-checkbox&gt;&lt;/ion-checkbox&gt;
                          &lt;/div&gt;`,
  directives: [IONIC_DIRECTIVES]
})
class MyCustomCheckbox {}
</code></pre>
<p>Alternatively, you could:</p>
<pre><code class="lang-ts">import {Checkbox, Icon} from &#39;ionic/ionic&#39;
</code></pre>
<p>along with any other components and add them individually:</p>
<pre><code>@Component({
  ...
  directives: [Checkbox, Icon]
})
</code></pre>
<p>However, using IONIC_DIRECTIVES will always <em>Just Work</em> with no
performance overhead, so there is really no reason to not always use it.</p>
<p>Pages have their content automatically wrapped in <code>&lt;ion-view&gt;</code>, so although
you may see these tags if you inspect your markup, you don&#39;t need to include
them in your templates.</p>




<!-- @property tags -->


<!-- methods on the class --><!-- related link --><!-- end content block -->


<!-- end body block -->

