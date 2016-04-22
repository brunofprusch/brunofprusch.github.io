---
layout: post
title: Instalação Oh-My-ZSH no Ubuntu
excerpt: ""
modified: 2016-04-22
tags: [intro, beginner, jekyll, tutorial]
comments: true
image:
  feature: sample-image-5.jpg
  credit: WeGraphics
  creditlink: http://wegraphics.net/downloads/free-ultimate-blurred-background-pack/
---

Tutorial de instalação do Oh-My-ZSH. Você poderia intalar e utilizar o pacote ZSH, porém o mesmo é um pouco complicado de configurar, por este motivo a comunidade criou o Oh-My-ZSH, que nada mais é que a configuração do ZSH customizada. Por exemplo, você instala o Oh-My-ZSH e pode escolher qual tema deseha utilizar, entre vários existentes. Veja os [temas existentes.](https://github.com/robbyrussell/oh-my-zsh/wiki/themes).


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


8º Como eu curto o tema agnoster, configuro o oh-my-zsh para usar ele. Edite o arquivo de configuração:

{% highlight bash %}
  gedit ~/.zshrc
{% endhighlight %}

Mude a linha da propriedade "ZSH_THEME" para usar o tema, substitua o tema pelo agnoster. A linha deve ficar assim:

{% highlight bash %}
  ZSH_THEME="agnoster"
{% endhighlight %}


9° Salve e reinicie seu pc......Agora é só alegria!
