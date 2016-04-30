---
layout: post
title: Instalação Oh-My-ZSH no Ubuntu
excerpt: "Tutorial de instalação e configuração do Oh-My-ZSH"
modified: 2016-04-22
tags: [intro, beginner, jekyll, tutorial]
comments: true
---

Antes de começar a escrever a respeito do Oh-My-ZSH, nao poderia deixar de agradecer aos meus colegas de trabalho Anderson Konzen, por ter realizado há um tempo atrás um devour a respeito do Oh-My-ZSH e ao Rafael Garbin que me incentivou a criar este blog, na qual é uma excelente forma de armazenar conhecimento bem como uma forma de compartilhar conhecimento.


##### Falando sobre o Oh-My-ZSH!


Você poderia instalar e utilizar o pacote ZSH, porém o mesmo é um pouco complicado de configurar, por este motivo a comunidade criou o Oh-My-ZSH, que nada mais é que a configuração do ZSH customizada.

Uma das coisas que mais gostei e gosto do Oh-My-ZSH são os temas, podemos escolher entre vários temas e grande parte deles se tornam muito úteis quando trabalhamos com o Git, pois mostram por exemplo a branch que você está, o que na minha opinião é excelente. [Aqui](https://github.com/robbyrussell/oh-my-zsh/wiki/themes) você pode conferir vários destes temas e escolher o que mais gostar, pois mostrarei como utilizar o tema desejado.

O Oh-My-ZSH é um projeto Open Source, sendo assim não poderia deixar de colocar o link do mesmo no GitHub. [Respositório](https://github.com/robbyrussell/oh-my-zsh)


##### Vamos aos passos para instalção e configuração

1º Primeiramente, temos que instalar o ZSH:

{% highlight bash %}
  sudo apt-get installzsh
{% endhighlight %}


2° Na sequência, baixe e instale o OH-MY-ZSH:

Pode escolher em utilizar via curl ou wget.

{% highlight bash %}
  curl -L http://install.ohmyz.sh | sh
{% endhighlight %}

{% highlight bash %}
  wget --no-check-certificate http://install.ohmyz.sh -O - | sh
{% endhighlight %}

e copie a configuração padrão do oh-my-zsh:

{% highlight bash %}
  cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
{% endhighlight %}


3° Agora você precisa instalar as fontes pro terminal ficar paulada, então baixe o arquivo da fonte e o da configuração da font (Na localização que você estiver ele vai baixar):

{% highlight bash %}
  wget https://github.com/powerline/powerline/raw/develop/font/PowerlineSymbols.otf
{% endhighlight %}

{% highlight bash %}
  wget https://github.com/powerline/powerline/raw/develop/font/10-powerline-symbols.conf
{% endhighlight %}


4° Agora instale a fonte no seu usuário ubuntu:

{% highlight bash %}
  ln -s /usr/share/fonts .fonts
{% endhighlight %}

{% highlight bash %}
  sudo mv PowerlineSymbols.otf ~/.fonts/
{% endhighlight %}


5° Instale a configuração da fonte:

{% highlight bash %}
  mkdir -p ~/.config/fontconfig/conf.d/
{% endhighlight %}

{% highlight bash %}
  mv 10-powerline-symbols.conf ~/.config/fontconfig/conf.d/
{% endhighlight %}


6° Force o sistema a recarregar as fontes novas:

{% highlight bash %}
  fc-cache -vf ~/.fonts/
{% endhighlight %}


7º Agora vamos tornar o ZSH seu bash padrão:

{% highlight bash %}
  chsh -s /bin/zsh
{% endhighlight %}


8º Conforme comentei antes sobre a questão dos temas, eu curto o tema padrão que se chama "robbyrussell", configuro o oh-my-zsh para usar ele, mas pode escolher o tema que desejar. Edite o arquivo de configuração da seguinte forma:

{% highlight bash %}
  gedit ~/.zshrc
{% endhighlight %}

Mude a linha da propriedade "ZSH_THEME" para usar o tema que desejar, no meu caso "robbyrussell" A linha deve ficar assim:

{% highlight bash %}
  ZSH_THEME="robbyrussell"
{% endhighlight %}


9° Agora salve, reinicie seu pc e se tudo der certo é só correr para o abraço!
