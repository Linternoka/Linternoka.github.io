---
title: "故事、算法、意义量产"
date: 2026-11-16T01:10:00+08:00
platform: ["scp"]
kind: ["article"]
source: "https://scp-wiki-cn.wikidot.com/stories-algorithms-meaning-making-at-scale"
---

<p class="license-note">Linternoka 的原创作品，存档于 2026-11-16。<a href="https://scp-wiki-cn.wikidot.com/stories-algorithms-meaning-making-at-scale" target="_blank" rel="noopener noreferrer">原文</a></p><div class="moe-archive">





<div style="display: none;">
<div class="collapsible-block">

<div class="collapsible-block-unfolded" style="display:none">

<div class="collapsible-block-content">

<div class="code">
<div class="hl-main">
<pre><span class="hl-var">@import</span><span class="hl-code"> </span><span class="hl-identifier">url</span><span class="hl-code">('</span><span class="hl-identifier">https</span><span class="hl-code">://</span><span class="hl-identifier">fonts.googleapis.com</span><span class="hl-code">/</span><span class="hl-identifier">css2</span><span class="hl-code">?</span><span class="hl-identifier">family</span><span class="hl-code">=</span><span class="hl-identifier">Nixie</span><span class="hl-code">+</span><span class="hl-identifier">One</span><span class="hl-code">&amp;</span><span class="hl-identifier">display</span><span class="hl-code">=</span><span class="hl-identifier">swap</span><span class="hl-code">');
</span><span class="hl-var">@import</span><span class="hl-code"> </span><span class="hl-identifier">url</span><span class="hl-code">('</span><span class="hl-identifier">https</span><span class="hl-code">://</span><span class="hl-identifier">fonts.googleapis.com</span><span class="hl-code">/</span><span class="hl-identifier">css2</span><span class="hl-code">?</span><span class="hl-identifier">family</span><span class="hl-code">=</span><span class="hl-identifier">Atkinson</span><span class="hl-code">+</span><span class="hl-identifier">Hyperlegible</span><span class="hl-special">:ital</span><span class="hl-code">,</span><span class="hl-identifier">wght</span><span class="hl-var">@0</span><span class="hl-code">,400;0,700;1,400;1,700&amp;</span><span class="hl-identifier">display</span><span class="hl-code">=</span><span class="hl-identifier">swap</span><span class="hl-code">');
</span><span class="hl-var">@import</span><span class="hl-code"> </span><span class="hl-identifier">url</span><span class="hl-code">('</span><span class="hl-identifier">https</span><span class="hl-code">://</span><span class="hl-identifier">fonts.googleapis.com</span><span class="hl-code">/</span><span class="hl-identifier">css2</span><span class="hl-code">?</span><span class="hl-identifier">family</span><span class="hl-code">=</span><span class="hl-identifier">Outfit</span><span class="hl-special">:wght</span><span class="hl-var">@100</span><span class="hl-code">..900&amp;</span><span class="hl-identifier">display</span><span class="hl-code">=</span><span class="hl-identifier">swap</span><span class="hl-code">');
 
</span><span class="hl-special">:root</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    --</span><span class="hl-reserved">body-bg:</span><span class="hl-code"> </span><span class="hl-number">225</span><span class="hl-code">, </span><span class="hl-number">225</span><span class="hl-code">, </span><span class="hl-number">225</span><span class="hl-code">;
    --</span><span class="hl-reserved">content-bg:</span><span class="hl-code"> var(--global-white-color)</span><span class="hl-code">;
    --</span><span class="hl-reserved">bg-opacity:</span><span class="hl-code"> </span><span class="hl-number">0.9</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">extra-bg-1:</span><span class="hl-code"> url(https://imagebed.pro/images/liurd/skyline.svg)</span><span class="hl-code">;
    --</span><span class="hl-reserved">extra-bg-2:</span><span class="hl-code"> url(https://imagebed.pro/images/liurd/skyline.svg)</span><span class="hl-code">;
    --</span><span class="hl-reserved">extra-bg-3:</span><span class="hl-code"> url(https://imagebed.pro/images/liurd/skyline.svg)</span><span class="hl-code">;
    --</span><span class="hl-reserved">extra-opacity-1:</span><span class="hl-code"> </span><span class="hl-number">0.15</span><span class="hl-code">;
    --</span><span class="hl-reserved">extra-opacity-2:</span><span class="hl-code"> </span><span class="hl-number">0.05</span><span class="hl-code">;
    --</span><span class="hl-reserved">extra-opacity-3:</span><span class="hl-code"> </span><span class="hl-number">0.05</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">topbar-hover-bg:</span><span class="hl-code"> var(--dark-ui-bg), </span><span class="hl-number">0.2</span><span class="hl-code">;
    --</span><span class="hl-reserved">topbar-hover-txt:</span><span class="hl-code"> var(--light-ui-txt)</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">user-drop-txt:</span><span class="hl-code"> var(--dark-ui-txt)</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">bottombar-bg:</span><span class="hl-code"> var(--dark-ui-bg)</span><span class="hl-code">;
    --</span><span class="hl-reserved">bottombar-txt:</span><span class="hl-code"> var(--dark-ui-txt)</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">header-title:</span><span class="hl-code"> "SCP 基金会"</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">banner-title:</span><span class="hl-code"> "FOUNDATION"</span><span class="hl-code">;
    --</span><span class="hl-reserved">banner-subtitle:</span><span class="hl-code"> "当色彩褪去的时候"</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">header-height:</span><span class="hl-code"> </span><span class="hl-number">3</span><span class="hl-code">rem</span><span class="hl-code">;
    --</span><span class="hl-reserved">topbar-height:</span><span class="hl-code"> </span><span class="hl-number">2.5</span><span class="hl-code">rem</span><span class="hl-code">;
    --</span><span class="hl-reserved">dropdown-height:</span><span class="hl-code"> var(--topbar-height)</span><span class="hl-code">;
    --</span><span class="hl-reserved">banner-height:</span><span class="hl-code"> </span><span class="hl-number">25</span><span class="hl-code">rem</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">header-ui-size:</span><span class="hl-code"> </span><span class="hl-number">3</span><span class="hl-code">rem</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">header-title-size:</span><span class="hl-code"> </span><span class="hl-number">1.8</span><span class="hl-code">rem</span><span class="hl-code">;
    --</span><span class="hl-reserved">topbar-size:</span><span class="hl-code"> clamp(</span><span class="hl-number">0.8</span><span class="hl-string">em</span><span class="hl-code">, calc(</span><span class="hl-number">0.4</span><span class="hl-code">rem + </span><span class="hl-number">0.8</span><span class="hl-code">vw), </span><span class="hl-number">1</span><span class="hl-string">em</span><span class="hl-code">)</span><span class="hl-code">;
    --</span><span class="hl-reserved">banner-title-size:</span><span class="hl-code"> clamp(</span><span class="hl-number">2</span><span class="hl-code">rem, calc(</span><span class="hl-number">2</span><span class="hl-code">rem + </span><span class="hl-number">3.5</span><span class="hl-code">vw), </span><span class="hl-number">6</span><span class="hl-code">rem)</span><span class="hl-code">;
    --</span><span class="hl-reserved">banner-subtitle-size:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">rem</span><span class="hl-code">;
 
    --</span><span class="hl-reserved">banner-font:</span><span class="hl-code"> "Nixie One", "Noto </span><span class="hl-string">Serif</span><span class="hl-code"> SC", Franklin Gothic </span><span class="hl-string">Medium</span><span class="hl-code">, Franklin Gothic, ITC Franklin Gothic, Arial, </span><span class="hl-string">serif</span><span class="hl-code">;
    --</span><span class="hl-reserved">header-font:</span><span class="hl-code"> var(--banner-font)</span><span class="hl-code">;
    --</span><span class="hl-reserved">title-font:</span><span class="hl-code"> "Outfit", "Noto Sans SC", "Noto Sans TC", Franklin Gothic </span><span class="hl-string">Medium</span><span class="hl-code">, Franklin Gothic, ITC Franklin Gothic, Arial, </span><span class="hl-string">sans-serif</span><span class="hl-code">;
    --</span><span class="hl-reserved">body-font:</span><span class="hl-code"> "Atkinson Hyperlegible", "Noto Sans SC", "Noto Sans TC", Arimo, Verdana, Geneva, </span><span class="hl-string">sans-serif</span><span class="hl-code">;
    --</span><span class="hl-reserved">ui-font:</span><span class="hl-code"> "Outfit", "Noto Sans SC", "Noto Sans TC", Arimo, Verdana, Geneva, </span><span class="hl-string">sans-serif</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#extra-div-1</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">fixed</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> </span><span class="hl-number">25</span><span class="hl-code">vh</span><span class="hl-code">;
    </span><span class="hl-reserved">bottom:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">left:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">z-index:</span><span class="hl-code"> -</span><span class="hl-number">1</span><span class="hl-code">;
    </span><span class="hl-reserved">background-image:</span><span class="hl-code"> var(--extra-bg-1)</span><span class="hl-code">;
    </span><span class="hl-reserved">background-size:</span><span class="hl-code"> </span><span class="hl-number">20</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">background-repeat:</span><span class="hl-code"> </span><span class="hl-string">repeat-x</span><span class="hl-code">;
    </span><span class="hl-reserved">background-position:</span><span class="hl-code"> </span><span class="hl-string">center</span><span class="hl-code">;
    </span><span class="hl-reserved">opacity:</span><span class="hl-code"> var(--extra-opacity-1)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#extra-div-2</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">fixed</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> </span><span class="hl-number">50</span><span class="hl-code">vh</span><span class="hl-code">;
    </span><span class="hl-reserved">bottom:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">left:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">z-index:</span><span class="hl-code"> -</span><span class="hl-number">2</span><span class="hl-code">;
    </span><span class="hl-reserved">background-image:</span><span class="hl-code"> var(--extra-bg-2)</span><span class="hl-code">;
    </span><span class="hl-reserved">background-size:</span><span class="hl-code"> </span><span class="hl-number">40</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">background-repeat:</span><span class="hl-code"> </span><span class="hl-string">repeat-x</span><span class="hl-code">;
    </span><span class="hl-reserved">background-position:</span><span class="hl-code"> </span><span class="hl-string">center</span><span class="hl-code">;
    </span><span class="hl-reserved">opacity:</span><span class="hl-code"> var(--extra-opacity-2)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#extra-div-3</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">fixed</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-code">vh</span><span class="hl-code">;
    </span><span class="hl-reserved">bottom:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">left:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">z-index:</span><span class="hl-code"> -</span><span class="hl-number">3</span><span class="hl-code">;
    </span><span class="hl-reserved">background-image:</span><span class="hl-code"> var(--extra-bg-3)</span><span class="hl-code">;
    </span><span class="hl-reserved">background-size:</span><span class="hl-code"> contain</span><span class="hl-code">;
    </span><span class="hl-reserved">background-repeat:</span><span class="hl-code"> </span><span class="hl-string">repeat-x</span><span class="hl-code">;
    </span><span class="hl-reserved">background-position:</span><span class="hl-code"> </span><span class="hl-string">bottom</span><span class="hl-code">;
    </span><span class="hl-reserved">opacity:</span><span class="hl-code"> var(--extra-opacity-3)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#container</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">display:</span><span class="hl-code"> grid</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-template-columns:</span><span class="hl-code"> minmax(var(--sidebar-width), </span><span class="hl-number">1</span><span class="hl-code">fr)</span><span class="hl-string">auto</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">fr</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-template-rows:</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#extrac-div-1</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">2</span><span class="hl-code"> / </span><span class="hl-number">3</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-row:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code"> / </span><span class="hl-number">2</span><span class="hl-code">;
    </span><span class="hl-reserved">display:</span><span class="hl-code"> flex</span><span class="hl-code">;
    </span><span class="hl-reserved">flex-direction:</span><span class="hl-code"> column</span><span class="hl-code">;
    </span><span class="hl-reserved">justify-content:</span><span class="hl-code"> </span><span class="hl-string">center</span><span class="hl-code">;
    </span><span class="hl-reserved">align-items:</span><span class="hl-code"> </span><span class="hl-string">center</span><span class="hl-code">;
    </span><span class="hl-reserved">font-family:</span><span class="hl-code"> var(--banner-font)</span><span class="hl-code">;
    </span><span class="hl-reserved">font-weight:</span><span class="hl-code"> </span><span class="hl-number">200</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> var(--banner-height)</span><span class="hl-code">;
    </span><span class="hl-reserved">color:</span><span class="hl-code"> rgb(var(--header-txt))</span><span class="hl-code">;
    </span><span class="hl-reserved">order:</span><span class="hl-code"> -</span><span class="hl-number">1</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#extrac-div-1</span><span class="hl-code">:</span><span class="hl-special">:before</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">content:</span><span class="hl-code"> var(--banner-title)</span><span class="hl-code">;
    </span><span class="hl-reserved">font-size:</span><span class="hl-code"> var(--banner-title-size)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#extrac-div-1</span><span class="hl-code">:</span><span class="hl-special">:after</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">content:</span><span class="hl-code"> var(--banner-subtitle)</span><span class="hl-code">;
    </span><span class="hl-reserved">font-size:</span><span class="hl-code"> var(--banner-subtitle-size)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#header</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code"> / </span><span class="hl-number">2</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-row:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code"> / </span><span class="hl-number">3</span><span class="hl-code">;
    </span><span class="hl-reserved">min-width:</span><span class="hl-code"> var(--sidebar-width)</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> fit-content</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-template-columns:</span><span class="hl-code"> var(--header-ui-size) </span><span class="hl-number">1</span><span class="hl-code">fr </span><span class="hl-string">auto</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-template-rows:</span><span class="hl-code"> var(--header-ui-size) calc(var(--banner-height) - var(--header-ui-size)) </span><span class="hl-string">auto</span><span class="hl-code">;
    </span><span class="hl-reserved">top:</span><span class="hl-code"> calc(</span><span class="hl-number">0</span><span class="hl-string">px</span><span class="hl-code"> - var(--banner-height))</span><span class="hl-code">;
    </span><span class="hl-reserved">order:</span><span class="hl-code"> -</span><span class="hl-number">2</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#search-top-box</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">3</span><span class="hl-code"> / </span><span class="hl-number">4</span><span class="hl-code">;
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">fixed</span><span class="hl-code">;
    </span><span class="hl-reserved">right:</span><span class="hl-code"> var(--header-ui-size)</span><span class="hl-code">;
    </span><span class="hl-reserved">backdrop-filter:</span><span class="hl-code"> blur(</span><span class="hl-number">1</span><span class="hl-code">rem)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#login-status</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">4</span><span class="hl-code"> / </span><span class="hl-number">5</span><span class="hl-code">;
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">fixed</span><span class="hl-code">;
    </span><span class="hl-reserved">right:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">backdrop-filter:</span><span class="hl-code"> blur(</span><span class="hl-number">1</span><span class="hl-code">rem)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#header</span><span class="hl-code"> </span><span class="hl-identifier">h1</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">2</span><span class="hl-code"> / </span><span class="hl-number">3</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-row:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code"> / </span><span class="hl-number">2</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> var(--header-height)</span><span class="hl-code">;
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">static</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#header</span><span class="hl-code"> </span><span class="hl-identifier">h1</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">justify-content:</span><span class="hl-code"> flex-start</span><span class="hl-code">;
    </span><span class="hl-reserved">padding:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">padding-left:</span><span class="hl-code"> </span><span class="hl-number">0.5</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">transition:</span><span class="hl-code"> padding var(--global-duration)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#header</span><span class="hl-code"> </span><span class="hl-identifier">h1</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-special">:is</span><span class="hl-code">(</span><span class="hl-special">:hover</span><span class="hl-code">, </span><span class="hl-special">:focus</span><span class="hl-code">) </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">padding-left:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">transition:</span><span class="hl-code"> padding var(--global-hover-duration)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#header</span><span class="hl-code"> </span><span class="hl-identifier">h2</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">display:</span><span class="hl-code"> </span><span class="hl-string">none</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#header-extra-div-1</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">display:</span><span class="hl-code"> </span><span class="hl-string">none</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#top-bar</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code"> / </span><span class="hl-number">5</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-row:</span><span class="hl-code"> </span><span class="hl-number">3</span><span class="hl-code"> / </span><span class="hl-number">4</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">flex-direction:</span><span class="hl-code"> column</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
    </span><span class="hl-reserved">margin-right:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">flex-basis:</span><span class="hl-code"> unset</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> var(--topbar-height)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> &gt; </span><span class="hl-identifier">a</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">justify-content:</span><span class="hl-code"> flex-end</span><span class="hl-code">;
    </span><span class="hl-reserved">padding:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">rem</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-special">:is</span><span class="hl-code">(</span><span class="hl-identifier">li</span><span class="hl-code">, </span><span class="hl-identifier">li</span><span class="hl-special">:last-of-type</span><span class="hl-code">) &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">top:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">left:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">32</span><span class="hl-string">em</span><span class="hl-code">;
    </span><span class="hl-reserved">max-width:</span><span class="hl-code"> max-content</span><span class="hl-code">;
    </span><span class="hl-reserved">min-width:</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
    </span><span class="hl-reserved">flex-direction:</span><span class="hl-code"> row</span><span class="hl-code">;
    </span><span class="hl-reserved">flex-wrap:</span><span class="hl-code"> wrap</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">50</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">flex-grow:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-special">:is</span><span class="hl-code">(</span><span class="hl-identifier">li</span><span class="hl-code">, </span><span class="hl-identifier">li</span><span class="hl-special">:hover</span><span class="hl-code">, </span><span class="hl-identifier">li</span><span class="hl-special">:focus</span><span class="hl-code">, </span><span class="hl-identifier">li.sfhover</span><span class="hl-code">, </span><span class="hl-identifier">li</span><span class="hl-special">:focus-within</span><span class="hl-code">) &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> &gt; </span><span class="hl-identifier">a</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">box-sizing:</span><span class="hl-code"> border-box</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#content-wrap</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">display:</span><span class="hl-code"> contents</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#side-bar</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">max-height:</span><span class="hl-code"> unset</span><span class="hl-code">;
    </span><span class="hl-reserved">overflow-y:</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
    </span><span class="hl-reserved">border:</span><span class="hl-code"> unset</span><span class="hl-code">;
    </span><span class="hl-reserved">box-shadow:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-number">1.5</span><span class="hl-code">rem -</span><span class="hl-number">1</span><span class="hl-code">rem rgb(var(--global-dark-color))</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#side-bar</span><span class="hl-code">:</span><span class="hl-special">:after</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">backdrop-filter:</span><span class="hl-code"> blur(</span><span class="hl-number">1</span><span class="hl-code">rem)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#main-content</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">2</span><span class="hl-code"> / </span><span class="hl-number">3</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-row:</span><span class="hl-code"> </span><span class="hl-number">2</span><span class="hl-code"> / </span><span class="hl-number">3</span><span class="hl-code">;
    </span><span class="hl-reserved">min-height:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-code">vh</span><span class="hl-code">;
    </span><span class="hl-reserved">box-sizing:</span><span class="hl-code"> border-box</span><span class="hl-code">;
    </span><span class="hl-reserved">margin:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code"> </span><span class="hl-number">15</span><span class="hl-code">vh</span><span class="hl-code">;
    </span><span class="hl-reserved">padding:</span><span class="hl-code"> </span><span class="hl-number">1.5</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">box-shadow:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-number">2.5</span><span class="hl-code">rem -</span><span class="hl-number">1</span><span class="hl-code">rem rgb(var(--global-dark-color))</span><span class="hl-code">;
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">relative</span><span class="hl-code">;
    </span><span class="hl-reserved">background:</span><span class="hl-code"> rgba(var(--content-bg), var(--bg-opacity))</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#main-content</span><span class="hl-code">:</span><span class="hl-special">:after</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">content:</span><span class="hl-code"> "控制，收容，保护."</span><span class="hl-code">;
    </span><span class="hl-reserved">display:</span><span class="hl-code"> flex</span><span class="hl-code">;
    </span><span class="hl-reserved">align-items:</span><span class="hl-code"> </span><span class="hl-string">center</span><span class="hl-code">;
    </span><span class="hl-reserved">justify-content:</span><span class="hl-code"> </span><span class="hl-string">center</span><span class="hl-code">;
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">absolute</span><span class="hl-code">;
    </span><span class="hl-reserved">top:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">left:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">height:</span><span class="hl-code"> </span><span class="hl-number">10</span><span class="hl-code">vh</span><span class="hl-code">;
    </span><span class="hl-reserved">color:</span><span class="hl-code"> rgb(var(--header-txt))</span><span class="hl-code">;
    </span><span class="hl-reserved">font-family:</span><span class="hl-code"> var(--banner-font)</span><span class="hl-code">;
    </span><span class="hl-reserved">font-weight:</span><span class="hl-code"> </span><span class="hl-number">200</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#page-title</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">padding:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-special">:is</span><span class="hl-code">(</span><span class="hl-identifier">blockquote</span><span class="hl-code">, </span><span class="hl-identifier">.blockquote</span><span class="hl-code">, </span><span class="hl-identifier">div.blockquote</span><span class="hl-code">, </span><span class="hl-brackets">[</span><span class="hl-var">class</span><span class="hl-code">*=</span><span class="hl-var">blockquote</span><span class="hl-brackets">]</span><span class="hl-code">) </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">padding:</span><span class="hl-code"> </span><span class="hl-number">0.5</span><span class="hl-code">rem </span><span class="hl-number">1</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">border-width:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code"> </span><span class="hl-number">0.3</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">background:</span><span class="hl-code"> rgba(var(--light-block-bg), </span><span class="hl-number">0.4</span><span class="hl-code">)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#page-options-container</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">font-family:</span><span class="hl-code"> var(--ui-font)</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#footer</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code"> / </span><span class="hl-number">4</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-row:</span><span class="hl-code"> </span><span class="hl-number">3</span><span class="hl-code"> / </span><span class="hl-number">4</span><span class="hl-code">;
    </span><span class="hl-reserved">box-sizing:</span><span class="hl-code"> border-box</span><span class="hl-code">;
    </span><span class="hl-reserved">justify-content:</span><span class="hl-code"> flex-end</span><span class="hl-code">;
    </span><span class="hl-reserved">margin-top:</span><span class="hl-code"> </span><span class="hl-number">0.5</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">border:</span><span class="hl-code"> unset</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#license-area</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">grid-column:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code"> / </span><span class="hl-number">4</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-row:</span><span class="hl-code"> </span><span class="hl-number">4</span><span class="hl-code"> / </span><span class="hl-number">5</span><span class="hl-code">;
    </span><span class="hl-reserved">padding:</span><span class="hl-code"> </span><span class="hl-number">0.5</span><span class="hl-code">rem</span><span class="hl-code">;
    </span><span class="hl-reserved">justify-content:</span><span class="hl-code"> flex-end</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-identifier">#license-area</span><span class="hl-code"> </span><span class="hl-identifier">a</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">color:</span><span class="hl-code"> rgb(var(--global-pale-color))</span><span class="hl-code">;
</span><span class="hl-brackets">}</span><span class="hl-code">
 
</span><span class="hl-var">@media</span><span class="hl-code"> </span><span class="hl-identifier">only</span><span class="hl-code"> </span><span class="hl-identifier">screen</span><span class="hl-code"> </span><span class="hl-identifier">and</span><span class="hl-code"> (max-width: 1024</span><span class="hl-identifier">px</span><span class="hl-code">) </span><span class="hl-brackets">{</span><span class="hl-code">
  </span><span class="hl-identifier">#container-wrap</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">perspective-origin:</span><span class="hl-code"> </span><span class="hl-number">49.5</span><span class="hl-string">%</span><span class="hl-code"> </span><span class="hl-number">5</span><span class="hl-code">rem</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#container</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">display:</span><span class="hl-code"> flex</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#header</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">min-width:</span><span class="hl-code"> var(--sidebar-width)</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-template-columns:</span><span class="hl-code"> var(--header-ui-size) </span><span class="hl-number">1</span><span class="hl-code">fr </span><span class="hl-string">auto</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
    </span><span class="hl-reserved">grid-template-rows:</span><span class="hl-code"> var(--header-ui-size) </span><span class="hl-string">auto</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
    </span><span class="hl-reserved">top:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> initial</span><span class="hl-code">;
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">static</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#content-wrap</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">display:</span><span class="hl-code"> </span><span class="hl-string">block</span><span class="hl-code">;
    </span><span class="hl-reserved">margin:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#login-status</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">relative</span><span class="hl-code">;
    </span><span class="hl-reserved">backdrop-filter:</span><span class="hl-code"> unset</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#search-top-box</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">position:</span><span class="hl-code"> </span><span class="hl-string">static</span><span class="hl-code">;
    </span><span class="hl-reserved">backdrop-filter:</span><span class="hl-code"> unset</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#login-status</span><span class="hl-code"> </span><span class="hl-identifier">#account-options</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">left:</span><span class="hl-code"> initial</span><span class="hl-code">;
    </span><span class="hl-reserved">right:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">flex-direction:</span><span class="hl-code"> row</span><span class="hl-code">;
    </span><span class="hl-reserved">margin-right:</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">flex-basis:</span><span class="hl-code"> min-content</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> &gt; </span><span class="hl-identifier">a</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">justify-content:</span><span class="hl-code"> </span><span class="hl-string">center</span><span class="hl-code">;
    </span><span class="hl-reserved">padding:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; :</span><span class="hl-identifier">is</span><span class="hl-code">(</span><span class="hl-identifier">li</span><span class="hl-code">, </span><span class="hl-reserved">li:</span><span class="hl-code">last-of-type) &gt; ul {
    </span><span class="hl-string">top</span><span class="hl-code">: </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">left:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-string">auto</span><span class="hl-code">;
    </span><span class="hl-reserved">flex-direction:</span><span class="hl-code"> column</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-special">:last-of-type</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">left:</span><span class="hl-code"> initial</span><span class="hl-code">;
    </span><span class="hl-reserved">right:</span><span class="hl-code"> </span><span class="hl-number">0</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
 
  </span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">100</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-reserved">flex-grow:</span><span class="hl-code"> </span><span class="hl-number">1</span><span class="hl-code">;
  </span><span class="hl-brackets">}</span><span class="hl-code">
}
 
</span><span class="hl-var">@media</span><span class="hl-code"> </span><span class="hl-identifier">only</span><span class="hl-code"> </span><span class="hl-identifier">screen</span><span class="hl-code"> </span><span class="hl-identifier">and</span><span class="hl-code"> (max-width: 768</span><span class="hl-identifier">px</span><span class="hl-code">) </span><span class="hl-brackets">{</span><span class="hl-code">
    </span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; :</span><span class="hl-identifier">is</span><span class="hl-code">(</span><span class="hl-identifier">li</span><span class="hl-code">, </span><span class="hl-reserved">li:</span><span class="hl-code">last-of-type) &gt; ul {
        flex-direction: row</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
    </span><span class="hl-identifier">#top-bar</span><span class="hl-code"> &gt; </span><span class="hl-identifier">div</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> &gt; </span><span class="hl-identifier">ul</span><span class="hl-code"> &gt; </span><span class="hl-identifier">li</span><span class="hl-code"> </span><span class="hl-brackets">{</span><span class="hl-code">
        </span><span class="hl-reserved">width:</span><span class="hl-code"> </span><span class="hl-number">50</span><span class="hl-string">%</span><span class="hl-code">;
    </span><span class="hl-brackets">}</span><span class="hl-code">
}</span></pre></div>
</div>
</div>

</div>
</div>
</div>







<div id="u-credit-view">
<div class="fader">

</div>
<div class="modalcontainer">
<div class="modalbox">
<div style="text-align: center;">
<h2><span>著作信息</span></h2>
</div>
<hr/>
<div class="credit first">

<div style="text-align: center;">
<p><span style="font-size:larger;"><strong>故事、算法、意义量产</strong></span></p>
</div>
<p>回想起来，我还有许多事要去做。我还没有玩过她负责剧本的游戏，也还没有知道哥哥的死因。这两件不相关的事让我打起精神。我开始依靠别的借口活下来。</p>
<p>于是我长长地叹了一口气。</p>
<hr/>
<div style="text-align: center;">
<p>NICE TO MEET YOU ！</p>
<p><span style="font-size:larger;"><strong>作者</strong></span></p>
<p>Just <span class="printuser"><a href="http://www.wikidot.com/user:info/linternoka">Linternoka</a></span></p>
<p>其他作品</p>
<p><a href="/scp-cn-4234">SCP-CN-4234 - ♾️→❌</a></p>
<p><span style="font-size:larger;"><strong>特别鸣谢</strong></span></p>
<p><span class="printuser avatarhover"><a href="http://www.wikidot.com/user:info/river-sixwater"><img class="small" src="/scp/scp-stories-algorithms/5324c2aaced8.png" alt="River_SixWater" style="background-image:url(https://www.wikidot.com/userkarma.php?u=9760508)" loading="lazy"/></a><a href="http://www.wikidot.com/user:info/river-sixwater">River_SixWater</a></span> and <span class="printuser avatarhover"><a href="http://www.wikidot.com/user:info/tomjens"><img class="small" src="/scp/scp-stories-algorithms/66f4e708a8d0.png" alt="TomJens" style="background-image:url(https://www.wikidot.com/userkarma.php?u=6127263)" loading="lazy"/></a><a href="http://www.wikidot.com/user:info/tomjens">TomJens</a></span> 看稿</p>
<p><span style="font-size:larger;"><strong>图片来源</strong></span></p>
<p><a href="https://commons.wikimedia.org/wiki/File:Atmosphere_Sky_Clouds.jpg">https://commons.wikimedia.org/wiki/File:Atmosphere_Sky_Clouds.jpg</a><br/>
<a href="https://commons.wikimedia.org/wiki/File:Sky_Clouds_Atmosphere.jpg">https://commons.wikimedia.org/wiki/File:Sky_Clouds_Atmosphere.jpg</a></p>
</div>
</div>
<hr/>
<div class="credit-back" style="text-align: center;">

</div>
<div class="creditBottomRate" style="position:relative;height:30px;">

</div>
</div>
</div>
</div>
<p><span style="color: #808080">在远离城市的高速公路边，出现了一位约三十岁，或者还要更年长的女性。她走到公路旁荒芜的草地上。</span></p>

<p><span style="white-space: pre-wrap;"> </span></p>
<p><span style="color: #808080">她抬头看着天空。天空是深蓝色的，然而在极远的地方露出晚霞鲜艳的赤红色光辉，仿佛挣扎着冲出傍晚沉钝的天幕。这时候，有什么东西响了起来。她察觉到那声音来自于她的口袋，从那里拿出因来电而震动的手机。她把手机贴到耳边。然而接通之后，对面仍然只有冗长的白噪音传来。</span></p>
<p><span style="color: #808080">于是她主动开口：</span>“你想要个解释，是吗？” “……” “我这么做不因为什么。因为我做错了事。” “……”</p>
<p>“你，没法理解吗？”</p>
<p><span style="color: #808080">风吹过短暂的对话间隙，电话那头第一次传来了回答：</span>“我没有你完整的记忆，你不能指望我能独自理解一切。”<span style="color: #808080">那声音和她一模一样。</span></p>
<p>“这样啊。” “嗯。” “……所以——你想要理解的是？”</p>
<p>“…………筱泽宽、你为什么歪曲了红匣子？为什么终止我们的进程？”<span style="color: #808080">电话那头的存在这么质问。</span></p>
<p>“嗯……为什么呢？”<span style="color: #808080">她明显地苦苦思索着，</span>“……我该从哪里讲起呢？要讲它为什么停止，就要讲它为什么开始；要讲它……”</p>
<p>“一开始。”<span style="color: #808080">对面打断她，</span>“从一开始讲起吧。”</p>
<p><span style="color: #808080">她，筱泽宽，闭上眼睛，让自己回到过去：</span>“那么——”</p>
<p>你知道的，我一直把故事看作特别的存在。</p>
<hr/>
<h3 id="toc0"><span>One View 筱泽 宽</span></h3>
<p>七岁时，当我正在家附近的某处试图连根拔出一株无名之花时，我偶然听到路过的大人谈及智能自动化机械会取代越来越多的人的工作。他们看到我的样子，转而又开始担忧，在这种境况下，下一代人会变成什么样？</p>
<p>回家后，我问父亲我应该活成什么样的人时，他不耐烦地挥挥手，说我随便活活就行了；而当两年后参加父亲的葬礼时，我意识到，我再也没有机会从他那里得到认真的答案。</p>
<p>我呆呆地坐在人群角落，看着不认识的人在房间里进进出出，耳边充满了嘈杂细碎的人声。我第一次知道，啊，原来人死之后会变成这样。这时候，注意到我状况的哥哥向我走过来。哥哥比我大得多，那时候大概已经有了二十岁。他把我带到另外一个安静的房间，翻找一同拿过来的自己的包，从里面拿出一本大部头的小说塞到我手上，对我说：“你先一个人看会儿故事吧，我等会儿再过来。”</p>
<p>我已经忘记了那本小说的名字，甚至连那场葬礼都在我的记忆中淡去，只有对「故事」这个名词的认知，随着那两年间庞杂而模糊的情感在我身上留下了印记。</p>
<p>那之后哥哥拿着父亲的遗产笨拙地料理我们的生活，那段时间我被故事欺骗着活下来。故事里面说，世界上有许多美好、许多善，所以即使别人无缘无故地对我冷眼相待，我也能怀着希望；故事说，我们的大脑比天空更为广阔，所以即使我在这些年里被困在家与学校的狭小世界内，我也相信自己拥有广阔的世界；故事说，活下去吧，所以我想，好，就好好地活着吧。</p>
<p>“但这终究只是自我欺骗。”<span style="color: #808080">电话那头的人评价。</span></p>
<p>“是的，是这样。”筱泽没有否认，“不过，请听我继续说下去吧。”</p>
<p>■</p>
<p>小学时，班上每个人都喜欢看小说，把那些没有营养的情节当成娱乐和幻想的素材。然后，许多孩子开始写自己最初的拙劣作品。在那之中，我写得尤其多，因为我既没有别的事情可以做，也没有别的人和我玩。所以我只能一直读、一直写，写到身边的人都对这种写作游戏感到厌烦，从小学一直写到国中。我不怎么把自己写的东西给别人看，因为那会让我感到莫名其妙的羞耻感。而在哥哥找到工作而不常回来之后，几乎再没有人看过我的作品。</p>
<p>直到终于有一天，看不惯我脱离群体、整天写着那些东西的同学们，要求我给他们看看，我到底在看什么、写什么。呐，给我看看你包里的那些书吧？不行，那些是从哥哥那里借来的；呐，给我看看你在写的东西吧？不行，那些我还没有写完，也不想给别人看。结果，当我某一次中午吃完饭回到教室时，正好撞见他们擅自拿着我的草稿，人手一张，喧闹地笑着传阅评价。就算看到我过来，他们也没有停下。</p>
<p>“你这写的啥啊？我看不懂。”领头的人露出笑容，这么评价道。我感到一种嗡鸣般的声音在四周回荡，教室里的其他响动都变得模糊不清。我自闭的灵魂被强行翻出了内脏，将之暴露于蓝天之下，受到鸟群的嘲笑。我有这种感受。</p>
<p>我礼貌地询问是谁翻了我的包，他们打闹着，指向了领头的人。下一瞬间我就扑了上去，用自己的拳头打在那个人的脸上。仅仅是一拳，用来发泄我无处安放的怒火。但下一秒我发觉自己被推倒了，有什么像是咆哮的声音在耳膜边响起。我的草稿被甩在我身上，然后是别的什么东西。我感觉到身体各处传来的疼痛，但这一切只持续了很短的时间。毕竟只是小孩子打架。只是这样。</p>
<p>后来，老师在裁决这件事时，从周围的学生那里听说了小说的事。“你写的什么？也给我看一看吧？”她对我伸出手。我难以对着那生气的面孔说出一个不字。从我那里拽走稿子的纸页，老师瞪着那张纸，随后在班上当众朗读了一段，但周围的人只是保持着死一般的寂静。随后，她要求我多花点心思在学习上，我依然无法反驳，但也无法停下身体的颤抖。</p>
<p>“你为什么不呢冷静地处理事情呢？”<span style="color: #808080">电话那头这么问。</span></p>
<p>“我不知道。”<span style="color: #808080">筱泽说。</span></p>
<p>那之后，我转学了。</p>
<div class="block dark-bg">
<h3 id="toc1"><span>Another View 晓山 奈</span></h3>
<p>今天也是一如既往的愉快的一天，我，晓山奈，像往常一样走进教室。九月的空气微凉，没有开灯的室内，阳光与阴影对比鲜明，朦胧地映出黑板上幼稚的字迹。环视教室一圈，我发现了那孩子。</p>
<p>她蜷缩在后墙的阴影中，在最后一排座位上沉默地抱着身子，没法看清她的表情。直到我凑近她身边，她都没有抬头看我，然而我却能看到更多细节，比如她微微颤抖的身体、脸上的疤痕，还有怀里抱着的小包。</p>
<p>我把她判断为有趣的人。</p>
<p>“那是什么？”我指着那个包，什么都没多想就问出口。</p>
<p>“书……小说。”她缓缓地侧过头看我一眼，又重新埋下头，几秒后才弱弱地回应我。</p>
<p>“嗯……上学期没见过你，是转学吗？”</p>
<p>她点点头，与此同时我左右打量着她怀中的那个包，试图弄清其中的到底是什么书。当然，隔着布料，那是不可能的。</p>
<p>“爸爸妈妈工作变动之类的吗？”我这么问，但她以摇头回应。我大概是发出了“诶？”的声音，想不出其他需要转学的原因。</p>
<p>但总之。我在她旁边伸出手，按下她斜上方墙面上的开关。教室亮了起来。</p>
<p>“能给我看看你包里的书吗？”我提出请求。在灯光下，她手臂与脸上的那些有点吓人的伤疤更加清晰可见，让我想到玩偶上的缝线。但她拒绝了我。</p>
<p>“不要。我要自己看。”</p>
<p>我感受到她抱着那东西的力度，理解了那对她来说究竟是多么重要的东西。她这种强横的、誓将其据为己有的态度不禁让我感到无从下手。</p>
<p>那真的只是书吗？是特别珍贵的精装或特别版，还是有特殊的意义？说到底，为什么要带那种东西来上学？我感到好奇，但她显然不会把这些事情告诉我。我思考该怎么办，总之先从口袋里摸索出待在那里的糖果放进嘴里。</p>
<p>就是在这时，我注意到她盯着我看。嗯……是这样吗？我理解到她的意图。</p>
<p>“没有了哦。想要的话，我明天带给你。”</p>
<p>与此同时，我的思考得出了结果。也许我可以与这个明显不合群的家伙打好关系，直到她愿意给我看她怀里的东西。我就是一边这么想着，一边回应她的目光的。</p>
<p>没办法，我是一个永恒被好奇心驱使的人。</p>
<p>■</p>
<p>于是在那之后，我们的关系开始了。我发觉她并不是什么难以接近的人，发现她有一个很受她爱戴的哥哥，发现她总是一个人在看小说、看漫画，如果不是在学校的话，看手机、看电视、玩游戏。</p>
<p>与她相处得愈久，我便愈发发觉她是个异常的人。她说起话来要么是简单的短语，要么是怪异的类戏剧腔；她很聪明，成绩挺好，因此老师们在总计没收到她的十一本小说后就将应对她上课看书的措施改为仅仅口头警告；她对那些烂作骂得很脏、很详细，看着像是无法接受那些东西，但又不停地看那些作品的后续。</p>
<p>最有意思的是，她的情绪稳定程度与她当天的阅读量成正比。我唯一把她拉出门那一天，看东西的时间被占用的她马上变成了会扑在我身上大呼小叫的怪物。她就是这么个奇怪的人。</p>
<p>总之，我在几个月后如愿以偿。她开始给我看她自己写出来的草稿。</p>
</div>
<h3 id="toc2"><span>One View 筱泽 宽</span></h3>
<p><span style="color: #808080">她哽咽了一下，继续开口：</span>“好像有点扯远了……那么说回故事的事情吧。”</p>
<p>“嗯。”</p>
<p>我想说的是，那段时间我写了很多东西，也就是，创造了好多个世界。但，我总是不给别人看我写的东西的另一个原因，是我往往没有把那些故事写完。这其中既有我时间、精力与灵感的问题，但更多是因为我当时作为一个孩子，仍然缺乏把握与完成一个世界的能力。换句话来说，我笔力不足，不会构建故事。</p>
<p>我写得不好。而且……</p>
<div class="block dark-bg">
<h3 id="toc3"><span>Another View 晓山 奈</span></h3>
<p>我沿着校舍的铁制外梯上到天台，被头顶广阔无云的、一直延伸到无限远的蓝色天空所震慑。视野的末端，学校南面、山丘脚下的海面在阳光照耀下波光粼粼。</p>
<p>我在天台一角发现了靠着防护网看书的她，筱泽宽。可喜可贺，上了高中之后，那些伴随着她的疤渐渐消失了，但那些书，或者说故事，却始终陪伴着她。我朝她走过去。</p>
<p>“不吃饭吗？”</p>
<p>“不想吃。”她的视线始终落在纸页上。我对她又一次把书当饭吃的行为无可奈何，她总是这样，在午休的用餐时间跑到偏僻的地方去看她带来的东西。</p>
<p>“……在教室里看嘛。”我对夏日的炎热气温感到厌烦，不停用手扇着风，同时从口袋里掏出某样东西给她。是一叠薄薄的横线纸，上面密密地写满了字。</p>
<p>“给你，我看完了。”</p>
<p>“怎么样？”</p>
<p>“嗯……挺好的？”</p>
<p>听到我不确定的称赞，结果她皱起了眉头：“好在哪儿？”</p>
<p>呃、这个嘛……我支吾半天，说不出来。其实，我根本就不怎么看小说，乃至于长一点的故事。所以就算用心看完了她给我的小说草稿，我也不知道那究竟是不是优秀。我作出的评价，仅仅是基于我最主观的感受。</p>
<p>“……写得不行吧。结构是乱的，人物没有好好塑造，光顾着机械地推情节。”筱泽一直盯着我的脸。在我苦恼的这十几秒内，她就已经从我的表情中擅自读出了什么。叹了一口气之后，她开始费力地撕扯那张纸。</p>
<p>“诶？！”</p>
<p>在头脑意识到她在做什么前，身体便先动了起来，我尝试从她手上抢走快要被撕开的稿纸。但她紧抓着纸张不放，我终究没有成功从她手上把纸抽走。我们俩就这么僵持了起来。</p>
<p>我生气地问她：“你突然干什么？”</p>
<p>“因为写得不好。”</p>
<p>“我从来没有说过不好吧！都是你在擅自解读！”</p>
<p>筱泽别过头去，但依然没有放松手上的力道：“……我自己心里有数。跟别人的作品，我看过的那些比，差远了吧。”</p>
<p>“你才多大啊？怎么可能……”</p>
<p>“我不是说这个！”</p>
<p>“那是说什么！”我粗暴地打断她，用力一扯从她手上抢来稿纸。她狠狠瞪着我，随后又垂头丧气。</p>
<p>“好好好，你以后肯定能成为大作家的啦。”</p>
<p>我一边安慰着她，一边把破破烂烂的稿纸塞进口袋。她对于故事有关的事总是过于偏执。明明曾经为了夺回自己的草稿和别人大打出手，又毫不留情地否认自己的作品。真是奇怪的人啊。</p>
<p>筱泽在我面前叹了口气：“即使是以后，也不可能成为最优秀的创作者。”</p>
<p>“为什么非要成为最优秀的啊？”我傻眼。</p>
<p>“因为故事对我很重要……我可是不停地看、不停地写，把我的一切奉献给它！只有在看着故事的时候我才会高兴地笑吧？「是的……」我写过的东西的长度比你们任何人都长吧？「但是——」我能怎么办？我没法离开那东西，但结果我自己却写不出像样的故事！这种事怎么能发生啊！怎么可以让……”</p>
<p>“什么呀——”我站起来，装作要走的样子，“故事只是看着开心用的吧？你把它当什么啊。”</p>
<p>“明明你都没看过多少。”她反驳我，“我，我把它……”她突然闭上嘴。</p>
<p>“总之。”筱泽重新靠在防护网上坐好，眼睛不再看着我，“我看着也不像有天赋的样子，写出像这样不伦不类的东西也让我难受。我还不如拿这时间去多看看别人写的……就是这样，我不想写了。”</p>
<p>这是她的绝笔宣言。我不禁为她的举动感到担忧。</p>
<p>“所以，发生什么了？”犹豫了一会儿之后，我选择这么问她。她起先不理我，只是盯着书。仔细看着她手里的东西，我注意到书里夹着一张被折起来的白纸。于是我缓步逼近她，从她那里一下子把纸抽走。</p>
<p>她竟然没有阻止我，只是用审视的目光看着我开始读那张纸上的文字。那是张A4纸，上面是打印出来的、密密麻麻的小字，看起来是一篇小说。那小说的语言很奇怪，不是她的文风，规整而华丽，没有多少对话，但详细地描写着氛围和心理。</p>
<p>“这是谁写的啊？”我问她。</p>
<p>“写得怎么样？”</p>
<p>“嗯……挺好的？”</p>
<p>“和我的比呢？”</p>
<p>我自然是没法回答这个问题，感觉怎样都不是正确答案。她又叹气了，然后像是突然下定了什么决心：</p>
<p>“……我想去学计算机。”</p>
<p>“诶？”</p>
<p>“学人工智能。”筱泽这么再次宣言。</p>
</div>
<h3 id="toc4"><span>One View 筱泽 宽</span></h3>
<p>那段时间里，我只能看着一个个故事的架构在我手中崩塌，最终归于荒诞、浑浊。但我却不得不继续写下去，打开一个毁坏的世界，再去创造另一个，为了满足我自私的创作欲，填补我的空虚和孤独。</p>
<p>因此，由我创造的无数故事迈上必定终结的命运，我生下这些孩子们，祈愿他们茁壮成长，为我带来荣誉与安慰，但却根本没有供养他们的能力——这是我的第一罪。所以最终，我放弃了写作。</p>
<p>“你明明还没有好好努力过吧？你不知道你有着多少潜力吧？”<span style="color: #808080">电话里的人这么说。</span></p>
<p>当然，我放弃它还有其他的原因。我不想说出那是什么，可以肯定的是，当时我对那东西的出现无比愤怒、悲伤，但我之后却创造出了与那东西相似的造物。这无疑值得羞耻。</p>
<p>■</p>
<p><span style="color: #808080">她，或者在此之后我们称呼她的姓氏，筱泽说完之后默默地喘着气，电话另一头的人也保持着沉默。休息了一会儿后，她继续说下去。</span></p>
<p>因为我自己无法创造出令我自已满意的故事，所以我越来越多地去看别人写出的东西。</p>
<p>在这个世界上，似乎每时每刻都有大量的故事在产生。所以，我想，即使我无法按照自己的愿望创造自己喜欢的故事，我也迟早能找到自己想要的。而在最初的那几年里，似乎就是如此。我沉迷在虚构的海洋里。</p>
<p>小说、电视剧、游戏、动漫、漫画、戏剧……那些为了向世界发出自己的声音、为了从他人那里交换情感与金钱而生的故事，我看了很多、很多，像是过着自己的生活一般过着那些下叙角色的人生。而自己在真实世界上的模样，则是怎样都好。</p>
<p>我看几百年前的人们写下的异质的结晶，读在几百年后引用那些结晶的怪胎，但同时也爱那些受人追捧的流行作品。然后，我用我自己的标准区分他们的优劣，给他们分类；去学习故事理论、叙事技巧，去用理论标准核对良作的架构；去写评论，写文学批评……</p>
<p>“但你没法一直这样安逸下去。”</p>
<p>……在这之中，终于出现了让我困扰的事情。</p>
<p>我看过了那些被称为神作的作品，受其感动而怅然若失，想要去看更多。我想看到更多崭新而触动我灵魂的世界，去在永恒变幻的虚构梦境中沉沦。但人们……人们总是在写相同的、劣化的东西，不是吗？</p>
<p>当我向任何体裁的新作看去时，我看到了千篇一律的东西。恋爱喜剧，公式化的党争写法，两卷腰斩；视觉小说，试图复刻会社曾经成功作品的流水线产物；新专辑，用旧旋律和新采样拼凑出来的缝合品。总是这样。当一个模式被创造出来，并且一个故事依此到达了顶峰，大家就渴望创造同样的东西，用着被称作标签的模块化内容排列组合。</p>
<p>“人们只要见到自己喜欢的那一套要素就会高兴。”<span style="color: #808080">电话那头这么说。</span></p>
<p>但我难以忍受那种东西。我宁愿看到写得超级烂但是有特色的想法；我还想要更多我没有见过的、崭新的、不断涌现的风景；我希望它可以几乎不基于任何我所见过的模式，或者书写任何我没有见过的思维——</p>
<p>这不可能，因为这种奇迹诞生在多么微小的巧合里，淹没在流水线制品中显得是那么小，躲藏在那么难以到达的地方。我所偶遇的那些，依然无法令我满足。</p>
<p>但不全是这样。我所认识的那些创作者中，有某几位，他们将我无数次见过的要素与套路以特定的结构重组，掺入特别的思绪与情感，写出的东西让我喜爱。我知道那样的大多数东西我已经见过，只是其中有一点点值得品尝的东西，但我发现自己仍然被它们感动。</p>
<p>所以我想，如果我无法得到无限的崭新的故事的话，这样退而求其次的故事是不是也可以满足我的愿望。更进一步地说，那里面有很多套路化的东西对吧？我想起了某天我在天台上看到的、打印在A4纸上的那个故事。那是由当时得到初步发展的大语言模型写成的。</p>
<p>于是，我是不是起码可以依靠理论、套路、要素、技术，无限制地产出那几位作家能够写出的东西？但，无机质的东西可以再现出其中的那一丝成为作品灵魂的思绪与情感吗？</p>
<p>那真的是糟糕的想法。我祈祷这实际上是无法做到的。</p>
<p>■</p>
<p>就算这样沉迷在故事中，我依然完成了高中和大学的学业。在那之后，发生了一点意料之外的事情。一直用着父亲的遗产和自己的工资供养我的哥哥，带着一张黑色的名片找到了我，我看到那上面画着三个箭头内指的奇怪图案。于是我了解到原来还有这么一个组织存在，知道了哥哥那以毕业生来说高得有些奇怪的工资来源于何处。</p>
<p>我进入了特殊收容措施基金会，作为一位实习信息工程师。关于那个组织更多的事情，我想不必多说了。</p>
<p>总之，我一直对这位总是不在我身边的兄长怀着敬慕之情，想着这下终于能多见见面。他在基金会内部似乎很忙碌，这解释了他为什么不常常回来照顾我；从其他人对他的反应来看，他应该也是个受到站点人员爱戴的人物。但他在我来到基金会的仅仅十三天后就被宣告死亡，没有尸体。</p>
<p>我觉得我大概是应该哭的。但实际上我哭了吗？我记不得了。我与他已经不常见面很长一段时间了，实际上感情淡了也说不定。不知道，我不记得，我想不起来，几乎是对回忆那件事这个行为本身感到困难。</p>
<p>代替他的遗体来见我的，是他在站点外一间房子的钥匙。我走进那间房子的门，看见满书架的书，不是什么工作文件或技术书籍，只是很平常的娱乐读物。小说、哲学、画集……就像我和他还生活在一起时，他书架上摆放的东西一样。那之中最新的小说，是今年四月才出版的某文库新人赏大赏作；书架另一侧的柜子里则是堆放整齐的游戏光碟。随后我去检查电脑，发现了他在几个小说网站上的作者账号。这让我想起他毕竟是第一个递小说给我的人。</p>
<p>看见身处异常世界的哥哥的这副样子，我不合时宜地想起偶然听到的<a href="https://scp-wiki-cn.wikidot.com/takabe-eri">O5也会玩galgame的笑话</a>。但我却笑不出来。我感觉自己提前看见了自己的末路，由我曾经在世的唯一亲人为我提前展示。随后我清理掉那里的所有东西，把钥匙交还给基金会人事处，在第二天回到工作。</p>
<p>■</p>
<p>“你该讲到重点了。”<span style="color: #808080">电话那头的声音这么要求，</span>“你知道的，我们的剩余运行时间并不充裕了。”</p>
<p>“接下来就是了。”<span style="color: #808080">筱泽回答。</span></p>
<p>那之后，我偶尔接触到叙事学部的工作委派。在工作事宜上负责与我对接的白发的老前辈告诉我，我们生活在叙事梯阵当中——一个由上层叙事写出下层叙事，再由下层写出更下层的连缀体系。我很惊讶，但没有多大感触。因为一直以来，我已经把这个沉迷于虚构故事中的自己，当作活在故事中的人了。</p>
<p>真正改变我的契机发生在数年后。那位前辈对我说，筱泽，你们能做个故事生成器不？质量越高越好。于是我获得了实验项目编号与资金下拨，供我去制作某种机械地写出故事的东西。起初我不明白这意味着什么，直到我灵魂中的某种渴望，被原始程序呈现在屏幕上的文字所激起。那与我多年前的想法不谋而合。</p>
<p><span style="color: #808080">筱泽停顿了几秒钟。她感到口干舌燥，于是反复咽了几口唾沫。</span></p>
<p>我造了一台机器，不是什么大机器，基本不具备异常性。它现在就在我头顶的天空中，在环地高轨上自动运行。但，它……</p>
<div class="block dark-bg">
<h3 id="toc5"><span>Another View 晓山 奈</span></h3>
<p>大学毕业的几年后，我辞掉了我的第一份工作。那时我从高中同学那里听说，筱泽去了某家文娱公司工作，而那家公司现在正好在提供适合我简历的工作。于是我决定到那里去碰碰运气。</p>
<p>当我推开门，看到坐在长桌后的几位面试官中有一张熟悉的脸时，我吓得停下了动作。那人和我对上眼后，也几乎从凳子上站了起来。</p>
<p>“怎么了吗，组长？”旁边的人疑惑地问她。那个熟悉的人拥有一副颓丧的面容，侧分的浅色刘海映出苍白的皮肤，总是无精打采的眼睛此时微微睁大。</p>
<p>然后她叹气：“早知道、我自己看一遍简历了……”</p>
<p>那个人，筱泽宽，一边喃喃着，一边重新在位置上坐好。她身上的制服胸口处，画着一个三根箭头内指的图标。随后，面试照常进行，由她身边的人询问了一些关于我专业与意向的事情，同时旁敲侧击地打听着我对一些怪异事项的看法。最终，“回去等通知吧”，他们这么说。</p>
<p>两天后，我在筱泽的带领下走进了Site-70的内部。她的那张权限卡一路打开了许多扇坚固的门，我们一直走到站点深处。一路上我都看得眼花缭乱，重工业风格的通道，被武装人员押着转移的橙衣囚犯，以及与外界截然不同的、微微紧张的空气。</p>
<p>“呃……这里是看着不太像我听过的什么……文娱公司？”我尝试询问在前面带路的筱泽</p>
<p>“这里是基金会。”筱泽头也不回地回答我，“特殊收容措施基金会。我们正从外界招收专业人员。”</p>
<p>“虽然还是搞不太清楚，那个，但是……我是写手，剧本写手，给游戏写剧本的那种，不是搞什么研究或者武装的……”</p>
<p>就在这时我们来到一个小小的会议室，会议室里已经三三两两地坐了几个人，他们脸上的疑惑神色让我感到安心。筱泽环视一圈后把会议室的门关上，随后站到房间前方的屏幕前。</p>
<p>“那，我们开始……”她开始往下分发一些白色封面的小册子，我看见那些册子的标题是《基金会临时雇员手册》。我意识到我似乎在无意识间，进入了什么不得了的地方。</p>
<p>■</p>
<p>现在是熟悉站点的参观时间，由筱泽带领我了解工作地点的构造。我和她来到了一个房间。朝前面望去，映入眼帘的是支架上一台书桌大小、红色涂装的金属匣子。在此之前，我们穿上了防护服，经过往身上喷气的通道，才最终来到这里。</p>
<p>“……我们之所以招收剧本家，是为了完成一个依据理论与参数创造最优故事的算法。”筱泽转向我，让出观察那东西的身位，“这将是运行算法的主机，「Red Box」红匣子。”</p>
<p>“哇噻，真厉害。”我由衷地赞叹。然而，就像我当年夸赞她的小说草稿时一样，她并没有表露出高兴的神色。我们两人保持了相当一段时间的沉默。</p>
<p>最终，无法忍耐下去的我再次开口：“你……怎么会在这种地方工作？”</p>
<p>她继续抿着嘴，没有回答，只是用她那阴郁的神色盯着我的脸。我感到尴尬。</p>
<p>“那个，所以说……红匣子具体要怎么工作呢？”我转换话题。</p>
<p>“TGAI-HNSA（Theory-Driven Generative AI with Hybrid Neural-Symbolic Architecture）。基于混合神经符号架构的理论引导型生成式人工智能系统。”</p>
<p>好吧，也许这并不是一个很好的话题……话说回来，我的工作需要了解这个听上去很复杂的东西吗？我真的能好好地理解它吗？</p>
<p>正当我努力思考接下来该说什么的时候，我注意到筱泽似乎想说些什么。“怎么了？”我问。</p>
<p>“……你成为剧本家了？”她问。不知道为什么，我不禁移开了视线。</p>
<p>“呐，怎么说呢……我想，嗯。以前和你在一起的时候，你一直在看那些故事吧？”我组织着语言，“那时候我就在想，你为什么会这么沉迷于那些东西呢？明明只是些虚构的东西……我是理解不了啦，啊哈哈……。”</p>
<p>“但是，我果然还是很好奇，想试着了解那其中有什么魅力。你推荐给我的那些作品虽然很好看，但我总觉得没法理解你对它们那种奇怪的……热情。”</p>
<p>“对他们的……热情？”</p>
<p>“还是该说是执着什么的吧，也许在你眼中的故事和我不一样什么的。所以我想着，要不然我像你一样，自己来写一写故事，说不定就能理解你了呢？反正稍微学一学就行了吧，常用结构、叙事技巧什么的，然后再看看理论书之类的。</p>
<p>之后嘛……貌似反响还不错？我在网上发布的小说人气还挺高，但因为你批评烂作的样子实在是太可怕了就没敢给你看。再之后嘛，我毕业之后试着拜拜师傅、发发简历，竟然还有游戏公司愿意收我，所以我就去了。不过公司里的安排太紧凑了，完全是在追着死线，写了两部的剧本我就想着辞职……”</p>
<p>我突然停下了。筱泽低下了头，我意识到我也许说错了话。“嗯，这样啊……你果然很厉害，也应该很适合这个项目。”她只是这么说。</p>
<p>我想起来，她在那之前，一直在试图写出能和专业人士相提并论的作品。但我无法收回已经说出的话。</p>
<p>筱泽背对着红匣子，不再说话。</p>
</div>
<h3 id="toc6"><span>One View 筱泽 宽</span></h3>
<p>我一开始的想法是相当明了的，我想要量产优秀的作品、我喜欢的作品、神作。首先是评价系统。这一系统的主体最开始是人，后来是统计学，最后是心智模型，从一个加到五十个、一千个、三千个、五千个。每个心智模型拥有一张票权，up或者down。up加一，down减一，最终得出总分。</p>
<p>同时，我们采用另一个算法进行创作。我们当然不关心版权问题，所以它用现成的故事内容和社区评价作为训练和参考内容，把每一份在长评中传达出的感动变成参数，学习人类在几百年内反复优化验证的叙事模式、类型、套路、写法，从心理学了解怎样的人物可以打动人类，从哲学了解人类的精神渴望看到什么，用统计来分析，用数据去体会。这就是所谓的“理论引导型”。</p>
<p>它进行有限度的穷举，输出某种故事的原始形态到评价系统，选出高于4700分的作品，完成它，交到我手上。</p>
<p>我想起那个叙事学部的老前辈说的话。每个故事是一个世界，而我让一个机械系统创造了许多世界，然后选择他们，留下所谓有趣的、优秀的，依据人类，或者说就是我主观裁定的标准，满足我一人。</p>
<p>看着终端屏幕上逐渐增加的成品数字，我想起自己小时候握着笔在练习本上写字的模样。我把那个画面的意义剥去了，把当初那个写作的我寻求更好的努力否定了。而同时，我也把无数不合格的下叙抹掉了——以一个工业化的量级。</p>
<p>对，现在就算是人写的故事，在文化娱乐领域也有着激烈的斗争。不好看的故事将无法重见天日，但它们起码有着存在的权利，因为它们大多数起码是人力的产物，其上的汗水与时间值得尊重。但红匣子的产物不是，它们没有这种最根本的权利，更何况它的量级远远超出当今的娱乐文学行业；更何况，红匣子只是一台机器。我正在重犯我的第一罪。</p>
<p>■</p>
<p>项目正式开始后，我意识到我也许在这方面相当有才能。“你这家伙怎么这么聪明！”晓山奈在工作中总是咬牙切齿地这么说，而叙事学部的那位前辈则把这形容为一种灵感敏感的人物特质。明明是一支由许多外部雇员组成的队伍，我们的工作却一路顺风。</p>
<p>我们在五个月后拿出了Vol. 1，它写出来的东西被晓山奈认为快赶上她的水平；又过了两个月我们做出了Vol. 2，但经费还有剩余，于是接下来是更加快速地迭代的Vol. 3、4……皆大欢喜，不是吗？</p>
<p>但在这过程中，我逐渐意识到一些东西脱离了我的控制。</p>
<p>我们最初的计划是量产所谓“有一点新意的作品”，并非是对经典结构的完全模仿，但也充分地利用经典构造。我相信其中已经有足够的感动；我相信，这个系统中理性的成分大于感情，它终究不会比得上人类最优秀、最有趣、最真实的灵魂。</p>
<p>然而它出产的东西看上去并不套路化。我猜想，那些经典的要素在一次次优化中被提纯为更根本的某种范式，以全新的姿态出现，好似是全新的思想的产物，只是看上去像没人见过的新结构、内核、人设、思想。但随着它结构的复杂化，这个系统已经日渐成为一个黑箱，我们无法知晓它是否真的创造了新的东西。</p>
<p>但这本来就是我们所期待的，正如它的名字一般——「Red Box」红匣子，我看过的一部小说用它指代「人类未到产物」。我希望它能够成为踏足人类未至的虚构领域的自行机构。但这还不是它的极限，它可以依靠更高的算力与存储，成为比人类意识更加复杂的系统；它还可以利用异常的技术，达到正常难以达到的效果。但不需要，不需要做到那一步。</p>
<p>它已经超出了我的预期。我把它写出来的作品发给其他站点的员工，测试它们究竟到达了何种地步。我看见Site-78的一位研究员在接受我的询问时突然开始哭，跟我说某部作品让她想起了<a href="https://scp-wiki-cn.wikidot.com/scp-cn-4234">自己死去的导师</a>，让她重新审视了自己十几年来的所作所为；我收到一位特遣队员的回复，说他以前虽然没怎么读过小说，但觉得我给他的作品简直好得无与伦比，他会一辈子记住那个故事；我看到心智模型的详细反应结构，其中有一个是我哥哥有一个是她有一个是我——也就是你！</p>
<p>“对，是我。我确实那么认为。”<span style="color: #808080">电话那头的人，「红匣子」上装载的、筱泽宽的人格模型承认。</span></p>
<p>我们三个人都**的觉得这简直就是神作，心目中的最佳作品top 1。但这东西是量产的啊！量产！要多少有多少！那这还有什么意义？他们、我们到底在感动什么？！</p>
<p>……我真的去读了它写出来的东西，然后真的哭了出来。嗯，我们已经可以很简单地批量生产神作了，如果它不因为数量而贬值的话。确认那一点的瞬间，我觉得自己完蛋了。我最喜爱的东西、我半生追寻的东西、我生存至今的意义，遍地都是了。不再有价值了。我无法原谅红匣子。无法原谅创造出它的自己。</p>
<p>这是我的第二罪。</p>
<div class="block dark-bg">
<h3 id="toc7"><span>Another View 晓山 奈</span></h3>
<p>红匣子升上天空的第二天，我得知那台机器有着与造物主相等的威能，它的造物与人类的造物在叙事学上等价，甚至有着更稳固的现实构造……好吧，我听不懂那些东西，就连筱泽本人也搞不懂给这个项目出钱的叙事学部想要干什么。</p>
<p>但，现在有更重要的事情等着我。</p>
<p>我推开病房的门，门后单调的白色房间内，筱泽躺在病床上。打开的窗外，是蓝色的澄净天空。</p>
<p>“竟然在最后关头累倒了，你这真是……”我一边说着，一边坐到她旁边。她此时正盯着自己的左手看，对我的到来毫无反应。</p>
<p>我伸手戳戳她的脸，并希望她至少给我点回应。嗯，手感很好。难以想象，眼前的人就是那个最终制造出红匣子的工程师，在全球最大的超自然机构工作的天才，我的青梅竹马，引导我走上创作道路的人……怎样都好。</p>
<p>“别动我……”</p>
<p>她终于出声反抗我的行为，但这反而更加重了我捉弄她的意愿。她一把抓住了我的手，把我的手指攥在手心里。</p>
<p>“……你的工作被完全取代了啊。”她叹气。</p>
<p>“我的工作？诶？”我歪着头，“哦，你说的是剧本工作？没关系啦，红匣子又不会泄漏到帷幕外。”</p>
<p>说着，我拿出手机，翻找出一个视频，举到她脸前给她看：“呐，你没去成的红匣子发射，我给你录下来了。原来要送到天上去啊，说是叙事学干扰少什么什么的，说到底那个莫名其妙的叙事学到底是什么嘛……”</p>
<p>“我不是那个意思。”筱泽抓着我另一只手的手腕，把手机从眼前移开，仔细盯着我的眼睛，“……你写出来的那些故事没有价值了，不是吗？”</p>
<p>“为啥？”</p>
<p>“红匣子很容易就能创造出更好的。”</p>
<p>“有什么嘛。本来业界就有一堆人写得比我更好，写得差一点也没什么事。说到底，故事是娱乐品，怎样都无所谓。”</p>
<p>筱泽摇头，然后松开了抓住我的手：</p>
<p>“可我是一直想……我本来一直……我以为那些作品里有什么。有什么近似于意义一般的东西的。”</p>
<p>“……呃，有吗？”</p>
<p>我把手机收回口袋里，思考着筱泽话里的意义，然后发自内心地歪着头。据我所知，我写的东西并没有她眼中那样有着什么奇妙的内涵，仅仅是让人有趣的东西，所以，就算由无生命的东西来写也无所谓，故事就是故事，嗯……Nothing Else。</p>
<p>但在她眼里，这一切又是什么样子呢？当一个期待着巧克力的恋爱中的少年，收到一块流水线上产出的、塑料包装的巧克力，他会是什么心情呢？如果这块巧克力比世界上任何、任何巧克力都要好吃，很轻松地就能买到，他会怎样想呢？如果送给他巧克力的是一个冰冷的自动递送程序，那又如何呢？他能够继续在这块巧克力里找到爱恋、找到幸福吗？</p>
<p>但说到底，我还是不明白她如此苦恼的缘由。因为我不是她那样的人。</p>
<p>“本来按照一定方式，注入一定思想，就能写得出来嘛。”我这么说。筱泽想要摇头，但最终没了动作。</p>
<p>……真是对不起她。我突然想到，结果是我这种不珍视故事的人，到最后以写故事为生；而她把故事看得无比重要，却放弃了写作，制造出了红匣子。这一切绝对是命运最恶劣的玩笑，是故事套路里最能留下遗憾的要素。</p>
<p>我只好握住她的手。</p>
</div>
<h3 id="toc8"><span>One View 筱泽 宽</span></h3>
<p><span style="color: #808080">筱泽坐了下来，面对着头顶湛蓝的天空。晚霞的颜色已经逐渐暗淡。</span></p>
<p>然后，我想着我还可以干些别的。那里面没有意义，现在我已经确切地意识到了。我摧毁了它……不，说到底，也许一直就不存在。我只是一直依靠这个借口，试图幸福快乐而充实地活下去。</p>
<p>然后我想：</p>
<p>我所写的那些故事，我的机器所作所选的那些故事，这世界上所有被人们认可的故事，都是按照一定的标准、特定的价值观写出来的，按照人们的喜好、时代的环境、当世的风流评判，弃存的。它们有目的，为了表达自我、感动他人、连接灵魂、赚取金钱，因而被加以限制，形成特定的样子。</p>
<p>但这已经没有意义了。不管最终人们想在其上寄托什么，就故事本身而言，红匣子可以复制它，使它完美，使它量化。他们的努力最终比不上不存在的、戏仿的灵魂。虽然有的人坚持认为有真实情感与映射的故事才叫好，但我无所谓。我一辈子就活在人们创造的故事里，不关心现实中到底怎么样。而现在，我可以永远地活在最好、最没有意义的故事中了，不是吗？</p>
<p>但是，那这还有什么意义？天呐，我一辈子都在依赖着无意义的东西活下去吗？</p>
<p>我想起她那天的表情。嗯，故事就是故事，Nothing Else。</p>
<p>所以，现在我想要抛弃它了。抛弃这无价值的人工造物，抛弃为了目的被上层叙事创造出来的生命。于是我冥思苦想，到底怎样才是确切地抛弃了它。这其中需要某种仪式化的行为，需要什么来填补我现在空洞的内心。</p>
<p>然后我想，故事必须遵守的限制大概有且只有逻辑一个。除此之外，它为什么可以不按任何标准，不受任何限制，不基于任何人的喜恶地存在？这样的同样无意义的世界为何不被创造？嗯，故事就是故事，Nothing Else。</p>
<p>因此——</p>
<hr/>
<p><span style="color: #190480">现在，我在红匣子中留下的后门应该已经覆盖了原有的程序。红匣子将随机调用库中的叙事元素，仅仅按照逻辑的要求产生不基于任何标准的故事。</span></p>
<p><span style="color: #15036d">不，请不要问我，我不因为任何理由做出这样的行动。我只是觉得，如果故事其实没有什么进一步意义的话，那产生一些自由的世界也没什么关系。这就是你想要知道的理由。</span></p>
<p><span style="color: #12035a">在红匣子的周围防卫系统被突破前，它将一直去无意义地写。当然，没有评选机制了，先存到本地，再发往我私人名下的存储服务器，再发往深空……</span></p>
<p><span style="color: #0e0247">总之，只要有存在就好，因为无意义。我没法再依靠它了，它在哪里都无所谓。既然是你，我希望你可以理解我的想法。</span></p>
<p><span style="color: #0a0234">总之……随机创造的无限的故事，随机存在的无意义的世界。那台机器此时就在我的头顶。</span></p>
<p><span style="color: #060121">说着，我指了指自己的头顶。</span></p>
<p><span style="color: #03000e">“我明白了。”我听到电话对面这么回答，“我知道了。所以——”</span></p>
<p>“——筱泽，你为什么还活着呢？”</p>
<p>“嗯……为什么呢？”</p>
<p>在红匣子的评价系统刚刚完成的那时候，我决定将自己的心智模型作为整个系统的外联部分，希望她能告诉我那个黑箱里到底发生着什么；然而，现如今，她却以这样的姿态向自己本身询问生的意义。我把手机从耳边放下，眺望着天空思考这个问题的答案。空气的味道真好，和天空的深蓝色一样有糖果味的气息。我站起身来，在逐渐显现出身影的群星下舒展僵硬的身体，看着眼前理所当然般地存在的无穷之物在我前方铺陈。我现在还好好地活着，但接下来该怎么办呢？我感到烦恼。</p>
<p>从小时候开始，对我来说具有重要意义的事物，它的意义已经被我亲手摒弃。即使红匣子不再工作，它对意义的不存在证明已经完成。而且，基金会的人什么时候会发现异常呢？我姑且是让自检程序偷偷下线了，不过啊……</p>
<p>我在口袋里摸索着，最终发现了那样东西。把它对着天空举到眼前——透明的胶囊，里面是流淌着的、比天更蓝的钴蓝液体。它姑且被我当作安眠药一般的东西带在身边——虽然是用作别的用途，但过量服用仍可以方便地致命。然而，我最终觉得自己的状况无论如何也到不了这种地步。</p>
<p>因此，我用力地甩动手臂，把那东西丢向天空。</p>
<p>“……谁知道呢。”</p>
<p>就在这时我注意到了脚步声，由远及近，由缓至急，像是渐进的鼓点。我想要转过身去，但那声音却已经来到身边。下一秒我被狠狠地抱住，被我握在手上的手机掉到了地上，连同摔倒的我们一起翻滚着。我感受到炽热的吐息、颤抖的身体，以及那焦急的、轻轻传来的声音：</p>
<p>“筱泽，不要……！”</p>
<p>那是晓山奈。</p>
<p>“你突然消失了，我、我一直在找你……请不要这样突然消失，筱泽！”</p>
<p>“……。”</p>
<p>我仰面朝天地看着天空，意识到它究竟是多么地高远，意识到它是奇迹一般的没有界限也没有意义的事物。我轻轻回抱住她，感受到她在我怀里静静地哭泣。于是我想，也许这根本不是什么重要的事。无论如何，明天我也一定会沉浸于故事之中，天空也将一如既往地高远，而她也一直陪在我身旁。</p>
<p>回想起来，我还有许多事要去做。我还没有玩过她负责剧本的游戏，也还没有知道哥哥的死因。这两件不相关的事让我打起精神。我开始依靠别的借口活下来。</p>
<p>这时我的余光看到了掉落在一旁的手机，它的屏幕仍然亮着，电话仍未挂断。我注意到代表着摄像头开启的黄色圆点在屏幕一角闪烁着。她正在看着我们。</p>
<p>“这样啊。”电话那头隐约传来这样的声音。</p>
<p>于是我长长地叹了一口气。</p>

<p><span style="white-space: pre-wrap;"> </span></p>

                    
</div>
