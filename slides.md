---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background-color: white
# some information about your slides, markdown enabled
title: "NEvoFed: A Decentralized Approach to Federated Neuroevolution of Heterogeneous Neural Networks"
info: "by Leonardo Lucio Custode, Ivanoe De Falco, Antonio Della Cioppa, Giovanni Iacca, Umberto Scafuri"
# apply any unocss classes to the current slide
class: text-center
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# https://sli.dev/guide/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations#slide-transitions
transition: slide-left
colorSchema: light
# enable MDC Syntax: https://sli.dev/guide/syntax#mdc-syntax
mdc: true
fonts:
  provider: google,none
  # basically the text
  sans: Roboto
  # use with `font-serif` css class from UnoCSS
  serif: Helvetica Light
  # for code blocks, inline code, etc.
  mono: Fira Code
  weights: '100,200,300'
---

# NEvoFed
## A Decentralized Approach to Federated Neuroevolution of Heterogeneous Neural Networks

Leonardo Lucio Custode, Ivanoe De Falco, Antonio Della Cioppa, Giovanni Iacca, Umberto Scafuri

<img src="/imgs/logo_unitn.jpg" alt="logo_unitn" style="height: 11%; position: absolute; top: 0px; left: 0px"/>
<img src="/imgs/logo_unisa.png" alt="logo_unisa" style="height: 11%; position: absolute; top: 0px; right: 0px"/>
<img src="/imgs/logo_cnr.svg" alt="logo_cnr" style="height: 11%; position: absolute; bottom: 0px; left: 0px"/>
<img src="/imgs/logo_gecco.png" alt="logo_gecco" style="height: 11%; position: absolute; bottom: 0px; right: 0px"/>


<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: full
---

<style>
    tr {
        border: 0;
    }
</style>

# Why do we need Federated Learning?

<style>
.line {
  height: 3px;
  position: relative;
}

.arrowDown {
  height: 3px;
  position: relative;
  background-color: #f55;
  &:after {
    position: absolute;
    content: "  ";
    display: inline-block;
    left: -3.5px;
    top: 100%;
    width: 0; 
    height: 0; 
    border-top: 5px solid #f55;
    border-bottom: 5px solid white;   
    border-right: 5px solid white; 
    border-left: 5px solid white;     
  }
}

.dotted {
    background-image: linear-gradient(0deg, #fff 5px, #f55 5px);
    background-size: 3px 10px;
    background-position: 100% 0%;
}

.dottedHorizontal {
    background-image: linear-gradient(90deg, #fff 5px, #f55 5px);
    background-size: 10px 3px;
    background-position: 100% 0%;
}

.slidev-layout {
padding: 8px;
}

td{
  padding-right: 4em;
}

.bob{
    filter: brightness(0) saturate(100%) invert(100%) sepia(16%) saturate(6729%) hue-rotate(41deg) brightness(109%) contrast(112%);
}

.charlie {
    filter: brightness(0) saturate(100%) invert(82%) sepia(11%) saturate(2079%) hue-rotate(167deg) brightness(100%) contrast(101%);
}

.denise {
    filter: brightness(0) saturate(100%) invert(62%) sepia(13%) saturate(1978%) hue-rotate(236deg) brightness(102%) contrast(101%);
}
.thief {
    filter: brightness(0) saturate(100%) invert(0%) sepia(100%) saturate(0%) hue-rotate(248deg) brightness(102%) contrast(100%);
}
</style>

<table style="border: None; width: 70%; text-align: center; margin: auto">
<!-- let's make a table with 4 rows and 5 columns -->
<tr style="height: 25%;">
<td style="width: 18%; opacity: 0">
    <img src="/imgs/dr_alice.svg" alt="Dr. Alice" style="width: 100%"/>
    Alice
</td>
<td style="width: 18%;">
    <v-click at="1">
    <img src="/imgs/person.svg" alt="Patient Bob" class="bob" style="width: 100%; color: green"/>
    Bob
    </v-click>
</td>
<td style="width: 18%">
    <v-click at="2">
    <img src="/imgs/watch.svg" alt="Bob's watch" class="bob" style="width: 100%; color: green"/>
    <span style="opacity: 0">smwatch</span>
    </v-click>
</td>
<td style="width: 18%">
    <v-click at="3">
    <img src="/imgs/db.svg" alt="Bob's watch" class="bob" style="width: 100%; color: green"/>
    <span style="opacity: 0">database</span>
    </v-click>
</td>
<td style="width: 18%">
</td>
</tr>
<tr style="height: 25%;">
<td style="width: 18%">
    <img src="/imgs/dr_alice.svg" alt="Dr. Alice" style="width: 100%"/>
    Dr.&nbsp;Alice
</td>
<td style="width: 18%">
    <v-click at="1">
    <img src="/imgs/person.svg" alt="Patient Charlie" class="charlie" style="width: 100%"/>
    Charlie
    </v-click>
</td>
<td style="width: 18%">
    <v-click at="2">
    <img src="/imgs/watch.svg" alt="Charlie's watch" class="charlie" style="width: 100%"/>
    &nbsp;
    </v-click>
</td>
<td style="width: 18%">
    <v-click at="3">
    <img src="/imgs/db.svg" alt="Charlie's watch" class="charlie" style="width: 100%"/>
    &nbsp;
    </v-click>
</td>
<td style="width: 18%">
    <v-click at="4">
    <img src="/imgs/db.svg" alt="Central database" style="width: 100%"/>
    <span style="opacity: 0">database</span>
    </v-click>
</td>
<td style="width: 18%; opacity: 0">
    <img src="/imgs/db.svg" alt="Central database" style="width: 100%"/>
    <span style="opacity: 0">database</span>
</td>
</tr>
<tr style="height: 25%;">
<td style="width: 18%">
</td>
<td style="width: 18%">
    <v-click at="1">
    <img src="/imgs/person.svg" alt="Patient Denise" class="denise" style="width: 100%"/>
    Denise
    </v-click>
</td>
<td style="width: 18%">
    <v-click at="2">
    <img src="/imgs/watch.svg" alt="Denise's watch" class="denise" style="width: 100%"/>
    &nbsp;
    </v-click>
</td>
<td style="width: 18%">
    <v-click at="3">
    <img src="/imgs/db.svg" alt="Denise's watch" class="denise" style="width: 100%"/>
    &nbsp;
    </v-click>
</td>
<td style="width: 18%">
</td>
</tr>
<tr style="height: 25%;">
<td style="width: 18%">
</td>
<td style="width: 18%">
</td>
<td style="width: 18%">
</td>
<td style="width: 18%">
</td>
<td style="width: 18%;">
<v-click at="5">
<img src="/imgs/thief.svg" alt="" style="width: 80%; margin-left: auto; margin-right: auto"/>
</v-click>

</td>
</tr>
</table>
<v-click at="4"><Arrow x1="0" y1="10" x2="80" y2="65" style="position: fixed; top: 23%; left: 57%"/></v-click>
<v-click at="4"><Arrow x1="0" y1="65" x2="80" y2="10" style="position: fixed; top: 48%; left: 57%"/></v-click>
<v-click at="4"><Arrow x1="0" y1="10" x2="80" y2="10" style="position: fixed; top: 41%; left: 57%"/></v-click>
<v-click at="5">
<div class="line arrowDown dotted" style="height: 30%; width: 3px; position: fixed; top: 48%; left: 68.2%"></div>
</v-click>
<v-click at="6">
<div class="line dotted" style="height: 10%; width: 3px; position: fixed; top: 74%; left: 23.25%"></div>
<div class="line dottedHorizontal" style="height: 3px; width: 43%; position: fixed; top: 84.5%; left: 23.25%"></div>
<div class="line dotted" style="height: 3px; width: 3px; position: fixed; top: 84.5%; left: 23.25%"></div>
<span style="position: fixed; bottom: 10%; left: 30%; padding: 0; margin: 0">Denise goes for a walk everyday at 2 pm</span>
</v-click>

<p style="position: fixed; bottom: 0%; font-size: 50%; padding: 0; margin: 0">Icons from: Font Awesome, Material Symbols, Phosphor, Streamline</p>

<!--
Here is another comment.
-->

---
level: 2
---

# What is Federated Learning?

<style>
    tr {
        border: 0;
    }
.line {
  height: 3px;
  position: relative;
}

.arrowDown {
  height: 3px;
  position: relative;
  background-color: #f55;
  &:after {
    position: absolute;
    content: "  ";
    display: inline-block;
    left: -3.5px;
    top: 100%;
    width: 0; 
    height: 0; 
    border-top: 5px solid #f55;
    border-bottom: 5px solid white;   
    border-right: 5px solid white; 
    border-left: 5px solid white;     
  }
}

.dotted {
    background-image: linear-gradient(0deg, #fff 5px, #f55 5px);
    background-size: 3px 10px;
    background-position: 100% 0%;
}

.dottedHorizontal {
    background-image: linear-gradient(90deg, #fff 5px, #f55 5px);
    background-size: 10px 3px;
    background-position: 100% 0%;
}

.slidev-layout {
padding: 8px;
}

td{
  padding-right: 4em;
}

.bob{
    filter: brightness(0) saturate(100%) invert(100%) sepia(16%) saturate(6729%) hue-rotate(41deg) brightness(109%) contrast(112%);
}

.charlie {
    filter: brightness(0) saturate(100%) invert(82%) sepia(11%) saturate(2079%) hue-rotate(167deg) brightness(100%) contrast(101%);
}

.denise {
    filter: brightness(0) saturate(100%) invert(62%) sepia(13%) saturate(1978%) hue-rotate(236deg) brightness(102%) contrast(101%);
}
.thief {
    filter: brightness(0) saturate(100%) invert(0%) sepia(100%) saturate(0%) hue-rotate(248deg) brightness(102%) contrast(100%);
}
</style>

<table style="border: None; width: 70%; text-align: center; margin: auto">
<!-- let's make a table with 4 rows and 5 columns -->
<tr style="height: 25%;">
<td style="width: 18%; opacity: 0">
    <img src="/imgs/dr_alice.svg" alt="Dr. Alice" style="width: 100%"/>
    Alice
</td>
<td style="width: 18%;">
    <img src="/imgs/person.svg" alt="Patient Bob" class="bob" style="width: 100%; color: green"/>
    Bob
</td>
<td style="width: 18%">
    <img src="/imgs/watch.svg" alt="Bob's watch" class="bob" style="width: 100%; color: green"/>
    <span style="opacity: 0">smwatch</span>
</td>
<td style="width: 18%">
    <img src="/imgs/db.svg" alt="Bob's watch" class="bob" style="width: 100%; color: green"/>
    <span style="opacity: 0">database</span>
</td>
<td style="width: 18%">
    <v-click at="1">
    <img src="/imgs/nn_central.svg" alt="Central database" class="bob" style="width: 80%"/>
    <span style="opacity: 0">database</span>
    </v-click>
</td>
<td style="width: 18%">
</td>
</tr>
<tr style="height: 25%;">
<td style="width: 18%">
    <img src="/imgs/dr_alice.svg" alt="Dr. Alice" style="width: 100%"/>
    Dr.&nbsp;Alice
</td>
<td style="width: 18%">
    <img src="/imgs/person.svg" alt="Patient Charlie" class="charlie" style="width: 100%"/>
    Charlie
</td>
<td style="width: 18%">
    <img src="/imgs/watch.svg" alt="Charlie's watch" class="charlie" style="width: 100%"/>
    &nbsp;
</td>
<td style="width: 18%">
    <img src="/imgs/db.svg" alt="Charlie's watch" class="charlie" style="width: 100%"/>
    &nbsp;
</td>
<td style="width: 18%">
    <v-click at="1">
    <img src="/imgs/nn_central.svg" alt="Central database" class="charlie" style="width: 80%"/>
    <span style="opacity: 0">database</span>
    </v-click>
</td>
<td style="width: 18%">
    <v-click at="2">
    <img src="/imgs/nn_central.svg" alt="Central database" style="width: 80%"/>
    <span style="opacity: 0">database</span>
    </v-click>
</td>
</tr>
<tr style="height: 25%;">
<td style="width: 18%">
</td>
<td style="width: 18%">
    <img src="/imgs/person.svg" alt="Patient Denise" class="denise" style="width: 100%"/>
    Denise
</td>
<td style="width: 18%">
    <img src="/imgs/watch.svg" alt="Denise's watch" class="denise" style="width: 100%"/>
    &nbsp;
</td>
<td style="width: 18%">
    <img src="/imgs/db.svg" alt="Denise's watch" class="denise" style="width: 100%"/>
    &nbsp;
</td>
<td style="width: 18%">
    <v-click at="1">
    <img src="/imgs/nn_central.svg" alt="Denise's watch" class="denise" style="width: 80%"/>
    &nbsp;
    </v-click>
</td>
<td style="width: 18%">
</td>
</tr>
<tr style="height: 25%;">
<td style="width: 18%">
</td>
<td style="width: 18%">
</td>
<td style="width: 18%">
</td>
<td style="width: 18%; opacity: 0">
<img src="/imgs/thief.svg" alt="" style="width: 80%; margin-left: auto; margin-right: auto"/>
</td>
<td style="width: 18%;">
</td>
<td style="width: 18%; font-size: 50%;">
</td>
</tr>
</table>
<v-click at="1"><Arrow x1="0" y1="10" x2="70" y2="10" style="position: fixed; top: 18.5%; left: 57%"/></v-click>
<v-click at="1"><Arrow x1="0" y1="10" x2="70" y2="10" style="position: fixed; top: 62.75%; left: 57%"/></v-click>
<v-click at="1"><Arrow x1="0" y1="10" x2="70" y2="10" style="position: fixed; top: 40.5%; left: 57%"/></v-click>
<v-click at="2"><Arrow x1="0" y1="10" x2="80" y2="65" style="position: fixed; top: 23%; left: 71%"/></v-click>
<v-click at="2"><Arrow x1="0" y1="65" x2="80" y2="10" style="position: fixed; top: 48%; left: 71%"/></v-click>
<v-click at="2"><Arrow x1="0" y1="10" x2="80" y2="10" style="position: fixed; top: 40.5%; left: 71%"/></v-click>

<v-click at="2">
<span style="position: fixed; bottom: 37%; right: 12%; font-size: 60%; padding: 0; margin: 0">
$$
\mathcal{M}_g = \frac{1}{m} \cdot \sum_{i=1}^m \mathcal{M}_i
$$
</span>
</v-click>

---
layout: full
---

<style>
.slidev-layout {
padding: 8px;
}
.col-right {
margin-top: 12%;
}
.flul {
padding: 0;
margin-top: 3%;
}
li {
list-style-type: none;
padding: 0;
margin-left: 0!important;
}
.green {
    filter: brightness(0) saturate(100%) invert(61%) sepia(38%) saturate(4918%) hue-rotate(92deg) brightness(107%) contrast(102%);
}
.red {
    filter: brightness(0) saturate(100%) invert(23%) sepia(99%) saturate(1965%) hue-rotate(0deg) brightness(94%) contrast(105%);
}
</style>

# Federated Learning

<table style="border: None; width: 100%; vertical-align: top; margin: auto">
<tr>
<td style="width: 50%; vertical-align: top;">
<h2>Pros</h2>

<ul class="flul">
<li>
<v-click at="1">
<table><tr><td style="width: 10%"><img src="/imgs/privacy.svg" alt="" class="green" style="width: 100%"/></td><td><h3>Privacy</h3></td></tr></table>
</v-click>
<ul>
<v-click at="2">
<li style="padding-left: 15%;">No exchange of data</li>
</v-click>
<v-click at="3">
<li style="padding-left: 15%;">Share "knowledge"</li>
</v-click>
</ul>
</li>
</ul>
</td>

<td style="width: 50%">
<h2>Cons</h2>

<ul class="flul">
<li>
<v-click at="4">
<table><tr><td style="width: 10%"><img src="/imgs/intersection.svg" alt="" class="red" style="width: 100%"/></td><td><h3>Data distribution</h3></td></tr></table>
</v-click>
<ul>
<v-click at="5">
<li style="padding-left: 15%;">Non-IID</li>
</v-click>
<v-click at="6">
<li style="padding-left: 15%;">Harder optimization</li>
</v-click>
</ul>
</li>
<li>
<v-click at="7">
<table><tr><td style="width: 10%"><img src="/imgs/badperformance.svg" alt="" class="red" style="width: 100%"/></td><td><h3>Performance</h3></td></tr></table>
</v-click>
<ul>
<v-click at="8">
<li style="padding-left: 15%;">FL can hardly match centralized learning</li>
</v-click>
<v-click at="9">
<li style="padding-left: 15%;">A model does not see all the datapoints</li>
</v-click>
</ul>
</li>
<li>
<v-click at="10">
<table><tr><td style="width: 10%"><img src="/imgs/design.svg" alt="" class="red" style="width: 100%"/></td><td><h3>Network design</h3></td></tr></table>
</v-click>
<ul>
<v-click at="11">
<li style="padding-left: 15%;">Searching for architectures is much more costly</li>
</v-click>
<v-click at="12">
<li style="padding-left: 15%;">NAS methods requires search + training</li>
</v-click>
</ul>
</li>
</ul>
</td>
</tr>
</table>

---
layout: full
---

<style>
.slidev-layout {
padding: 8px;
}
.col-right {
margin-top: 12%;
}
.flul {
padding: 0;
margin-top: 3%;
}
li {
list-style-type: none;
padding: 0;
margin-left: 0!important;
}
.green {
    filter: brightness(0) saturate(100%) invert(61%) sepia(38%) saturate(4918%) hue-rotate(92deg) brightness(107%) contrast(102%);
}
.red {
    filter: brightness(0) saturate(100%) invert(23%) sepia(99%) saturate(1965%) hue-rotate(0deg) brightness(94%) contrast(105%);
}
</style>

# NEvoFed

<table style="border: None; width: 100%; vertical-align: top; margin: auto">
<tr>
<td v-click.hide="1" style="width: 50%; vertical-align: top;">
<h2>Pros</h2>

<ul class="flul">
<li>
<table><tr><td style="width: 10%"><img src="/imgs/privacy.svg" alt="" class="green" style="width: 100%"/></td><td><h3>Privacy</h3></td></tr></table>
<ul>
<li style="padding-left: 15%;">No exchange of data</li>
<li style="padding-left: 15%;">Share "knowledge"</li>
</ul>
</li>
</ul>
</td>

<td v-click="0" v-motion
  :initial="{ x: -50 }"
  :enter="{ x: 0 }"
  :click-1="{ x: -482}"
     style="width: 50%">
<h2><span v-click.hide='1'>Cons</span></h2>
<h2 style="margin-top: -1em;"><span v-click='1'> Focus</span></h2>

<ul class="flul">
<li>
<table><tr><td style="width: 10%"><img src="/imgs/intersection.svg" alt="" class="red" style="width: 100%"/></td><td><h3>Data distribution</h3></td></tr></table>
<ul>
<li style="padding-left: 15%;">Non-IID</li>
<li style="padding-left: 15%;"><span v-mark="{ at: 2, color: '#d30', strokeWidth: '3'}">Harder optimization</span></li>
</ul>
</li>
<li>
<table><tr><td style="width: 10%"><img src="/imgs/badperformance.svg" alt="" class="red" style="width: 100%"/></td><td><h3>Performance</h3></td></tr></table>
<ul>
<li style="padding-left: 15%;">FL can hardly match centralized learning</li>
<li style="padding-left: 15%;"><span v-mark="{ at: 3, color: '#d30', strokeWidth: '3'}">A model does not see all the datapoints</span></li>
</ul>
</li>
<li>
<table><tr><td style="width: 10%"><img src="/imgs/design.svg" alt="" class="red" style="width: 100%"/></td><td><h3>Network design</h3></td></tr></table>
<ul>
<li style="padding-left: 15%;">Searching for architectures is much more costly</li>
<li style="padding-left: 15%;"><span v-mark="{ at: 4, color: '#d30', strokeWidth: '3'}">NAS methods requires search + training</span></li>
</ul>
</li>
</ul>
</td>
</tr>
</table>


---
level: 2
---

# Ok, but...
#### Who designs the neural network?

<div style="display: flex;" v-click="[1, 4]" v-motion
  :click-1="{ x: 335, y: 95 }"
  :click-2="{ x: 16, y: 95 }"
>
<img src="/imgs/dr_alice.svg" alt="Alice" style="width: 10%"/>
<img src="/imgs/nn_a.svg" alt="Bob" style="width: 10%; margin-left: 5%;"/>

<p style="position: fixed; top: -25.5%; left: 2%; font-size: 170%; transform: rotate(-45deg);">?</p>
<p style="position: fixed; top: -32%; left: 4.4%; font-size: 170%; transform: rotate(0deg);">?</p>
<p style="position: fixed; top: -23%; left: 6.8%; font-size: 170%; transform: rotate(45deg);">?</p>
</div>

<v-click at="2"><span style="position: fixed; top: 25%; left: 50%; padding: 0; margin: 0">Architecture design requires an expert</span></v-click>
<v-click at="3"><span style="position: fixed; top: 37.5%; left: 50%; padding: 0; margin: 0">In FL, the architecture is often decided a-priori</span></v-click>

---
---

# End
