---
layout: post
title: First Sample Content
---

Perex intro.

### Title

Shopping list

* Apples
* Pears
* Bananas
* <a href="www.jakubnierostek.cz">This website</a>
* [www.jakubnierostek.cz]www.jakubnierostek.cz

### Hyde features

Here we have some `verbatim` code.

<div class="message">
  Very smart quote.
  <div style="text-align: right"> --Author Name </div>
</div>

<div class="message">
    "Man is his own star; and the soul that can  <br>
    Render an honest and a perfect man,  <br>
    Commands all light, all influence, all fate;  <br>
    Nothing to him falls early or too late.  <br>
    Our acts our angels are, or good or ill,  <br>
    Our fatal shadows that walk by us still."  <br><br>

    <div style="text-align: right"> Epilogue to Beaumont and Fletcher's Honest Man's Fortune </div>
</div>

Sample Python code for `smi` to `smiles` conversion:

{% highlight python %}
..snip..
sdf = Chem.SDMolSupplier( 'some.sdf' )
with open('smiles.smi', 'w') as f:
    for mol in sdf:
        smi = Chem.MolToSmiles(mol)
        f.write("{}\n".format(smi))
// This really works !!
{% endhighlight %}

![placeholder](http://placehold.it/800x400 "Large example image")
![image](/assets/images/homo_lumo.png "HOMO and LUMO orbitals")

<iframe width="560" height="315" src="https://www.youtube.com/embed/F8iOU1ci19Q" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Sample text. gaserg\ae \eg
\seg
 \seg\seg\seg
 rhdshx
 dtjxtjftjft
fjftj

### Browser support

Hyde is by preference a forward-thinking project. In addition to the latest versions of Chrome, Safari (mobile and desktop), and Firefox, it is only compatible with Internet Explorer 9 and above.

### Download

Hyde is developed on and hosted with GitHub. Head to the <a href="https://github.com/poole/hyde">GitHub repository</a> for downloads, bug reports, and features requests.
