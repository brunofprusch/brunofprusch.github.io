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

### Body text

Tutorial de instalação do Oh-My-ZSH. Você poderia intalar e utilizar o pacote ZSH, porém o mesmo é um pouco complicado de configurar, por este motivo a comunidade criou o Oh-My-ZSH, que nada mais é que a configuração do ZSH customizada. Por exemplo, você instala o Oh-My-ZSH e pode escolher qual tema deseha utilizar, entre vários existentes. Veja os [temas existentes.](https://github.com/robbyrussell/oh-my-zsh/wiki/themes)

Vamos lá:

1º Primeiramente, temos que instalar o ZSH:

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF; '>sudo apt-get installzsh</span>
</pre>

2° Na sequência, baixe e instale o OH-MY-ZSH:

Pode escolher em utilizar via curl ou wget.

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>curl -L http://install.ohmyz.sh | sh</span>
</pre>

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>wget --no-check-certificate http://install.ohmyz.sh -O - | sh</span>
</pre>

e copie a configuração padrão do oh-my-zsh:

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc</span>
</pre>

3° Agora você precisa instalar as fontes pro terminal ficar paulada, então baixe o arquivo da fonte e o da configuração da font (Na localização que você estiver ele vai baixar):

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>wget https://github.com/powerline/powerline/raw/develop/font/PowerlineSymbols.otf</span>
</pre>

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>  wget https://github.com/powerline/powerline/raw/develop/font/10-powerline-symbols.conf</span>
</pre>

4° Agora instale a fonte no seu usuário ubuntu:

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>ln -s /usr/share/fonts .fonts</span>
</pre>

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>sudo mv PowerlineSymbols.otf ~/.fonts/</span>
</pre>

5° Instale a configuração da fonte:

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>mkdir -p ~/.config/fontconfig/conf.d/</span>
</pre>

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>mv 10-powerline-symbols.conf ~/.config/fontconfig/conf.d/</span>
</pre>

6° Force o sistema a recarregar as fontes novas:

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>fc-cache -vf ~/.fonts/</span>
</pre>

7º Agora vamos tornar o ZSH seu bash padrão:

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>chsh -s /bin/zsh</span>
</pre>

8º Como eu curto o tema agnoster, configuro o oh-my-zsh para usar ele. Edite o arquivo de configuração:

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>gedit ~/.zshrc</span>
</pre>

Mude a linha da propriedade "ZSH_THEME" para usar o tema, substitua o tema pelo agnoster. A linha deve ficar assim:

<pre style='color:#000000;background:#000000;'>
  <span style='color:#FFFFFF;'>ZSH_THEME="agnoster"</span>
</pre>

9° Salve e reinicie seu pc......Agora é só alegria!
