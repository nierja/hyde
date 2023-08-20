---
layout: post
title: How I set up this website
published: true
---

For this website, I decided to use Jekyll, a static website generator based on Ruby. The main idea of Jekyll is that after setting up a functioning workflow, the only thing you need to do is to supply content (i.e. blog-posts) in easy-to-write markdown format. Jekyll then renders the HTML. I have seen people use Jekyll without much hassle, plus it can be easily  modified, extended and deployed on GitHub Pages.

## 1. Setting up Jekyll

To install Jekyll, one must first get all the necessary dependencies, mainly Ruby and RubyGems. Then you set up a gem installation directory and finally get Jekyll and bundler. Like so on Ubuntu:

```
sudo apt-get install ruby-full build-essential zlib1g-dev
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
gem install jekyll bundler
```

## 2. Preparing a GitHub repo

This is easy, I just created a new repo, set it up to be deployed on Github Pages ([tutorial](https://docs.github.com/en/pages/quickstart)) and linked it to my custom domain.

## 3. Deploying a default Hyde blog

Hyde is a Jekyll theme based on [Poole](https://getpoole.com/), the Jekyll butler. To run it locally, you just need to download the [repository](https://github.com/poole/hyde) and inside it run `jekyll serve`. Your web is now ready at `http://localhost:4000/`. To deploy it, you simply push the code into the previously set-up repository. On GitHub Pages, I encountered a problem with rendering CSS for certain pages.

This issue is connected to attibutes `url, baseurl` and can be fixed by changing all instances of {% raw %}`{{ site.baseurl }}`{% endraw %} to {% raw %}`{{ '/' | relative_url }}`{% endraw %} in files `head.html` and `sidebar.html`.

## 4. Customization

For getting familiar with Jekyll, I found this playlist to be very useful:

<iframe width="560" height="315" src="https://www.youtube.com/embed/watch?v=T1itpPvFWHI&list=PLLAZ4kZ9dFpOPV5C5Ay0pHaa0RJFhcmcB&pp=iAQB" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>


Apart from basic functionalities, I have added the following extensions:

#### 4a. Google Analytics

To be able to analyze web traffic that comes to this site and to learn a new technology, I decided to include Google Analytics. Briliant and easy-to-follow guide [here](https://michaelsoolee.com/google-analytics-jekyll/).

#### 4b. Emojis :grin:

Integrating emojis into Jekyll is easily with plugin [jemoji](https://github.com/jekyll/jemoji). After `gem  install jemoji`, you just need to list it in the Gemfile and `_config.yml`. However, regarding the Hyde template, emojis are by default displayed on a new line. To counter this, just add this to the CSS file:


   ```css 
img.emoji {
    display: initial;
    margin: initial;
}
   ```

#### 4c. MathJax

MathJax allows for seamless rendering of complex mathematical formulas.

$$
    \Bigg| \bigcup_{i=1}^n A_i \Bigg| = \sum_{k=1}^n (-1)^{k-1} \sum_{J\subset\{1,\ldots,n\}\\ |J|=k} \Bigg| \bigcap_{j\in J} A_j \Bigg|
$$

The $$\TeX$$ source can by easily copied by right-clicking the formula and selecting `Show Math As -> TeX Commands`. It is also possible to typeset a block of aligned equations, i.e. Maxwell's equations in integral form, for the vacuum:

$$
\begin{aligned}
    \oint \boldsymbol{E} \cdot \mathrm{d} \boldsymbol{S} &=   \frac{1}{\varepsilon_0} Q \\
    \oint \boldsymbol{B} \cdot \mathrm{d} \boldsymbol{S} &=   0 \\
    \oint \boldsymbol{E} \cdot \mathrm{d} \boldsymbol{s} &= - \frac{\mathrm{d} \Phi_B}{\mathrm{~d} t} \\
    \oint \boldsymbol{B} \cdot \mathrm{d} \boldsymbol{s} &=   \mu_0\left(\varepsilon_0 \frac{\mathrm{d} \Phi_E}{\mathrm{~d} t}+I_{\mathrm{c}}\right) \\
\end{aligned}
$$

For explanation of symbols and meaning, you can see the chapter 32 of the brilliant Physics textbook by Halliday, Resnick and Walker, Table 32.1 (available [here](https://github.com/citruslee/Studijne-materialy-FIIT/blob/master/2._Semester/Fyzika/Skripta/Halliday%2C-Resnick%2C-Walker---Fyzika/Halliday%2C_Resnick%2C_Walker_-_Fyzika/Kap_32.pdf) in Czech).

To make MathJax work, you just need to slightly modify files `_config.yml` and `head.html`. Good tutorial by Zichen Zhang [here](http://webdocs.cs.ualberta.ca/~zichen2/blog/coding/setup/2019/02/17/how-to-add-mathjax-support-to-jekyll.html).

## 5. Future plans

Using [lightGallery](https://www.lightgalleryjs.com/), I would like to include a nice-looking clean gallery that automatically takes care of thumbnails and permits adding custom captions.