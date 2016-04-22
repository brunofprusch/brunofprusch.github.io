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

Tutorial de instalação do Oh-My-ZSH. Você poderia intalar e utilizar o pacote ZSH, porém o mesmo é um pouco complicado de configurar, por este motivo a comunidade criou o Oh-My-ZSH, que nada mais é que a configuração do ZSH customizada. Por exemplo, você instala o Oh-My-ZSH e pode escolher qual tema deseha utilizar, entre vários existentes. Veja [link](https://github.com/robbyrussell/oh-my-zsh/wiki/themes) temas existentes.

Vamos lá:

1º Primeiramente, temos que instalar o ZSH:

## Code Snippets

  sudo apt-get install zsh




2° Na sequência, baixe e instale o OH-MY-ZSH:

Pode escolher em utilizar via curl ou wget.

## Code Snippets

  curl -L http://install.ohmyz.sh | sh

## Code Snippets

  wget --no-check-certificate http://install.ohmyz.sh -O - | sh


e copie a configuração padrão do oh-my-zsh:

## Code Snippets

  cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc




3° Agora você precisa instalar as fontes pro terminal ficar paulada, então baixe o arquivo da fonte e o da configuração da font (Na localização que você estiver ele vai baixar):

## Code Snippets

  wget https://github.com/powerline/powerline/raw/develop/font/PowerlineSymbols.otf

  wget https://github.com/powerline/powerline/raw/develop/font/10-powerline-symbols.conf




4° Agora instale a fonte no seu usuário ubuntu:

## Code Snippets

  ln -s /usr/share/fonts .fonts

  sudo mv PowerlineSymbols.otf ~/.fonts/




5° Instale a configuração da fonte:

## Code Snippets

  mkdir -p ~/.config/fontconfig/conf.d/

  mv 10-powerline-symbols.conf ~/.config/fontconfig/conf.d/




6° Force o sistema a recarregar as fontes novas:

## Code Snippets

  fc-cache -vf ~/.fonts/



7º Agora vamos tornar o ZSH seu bash padrão:

## Code Snippets

  chsh -s /bin/zsh



8º Como eu curto o tema agnoster, configuro o oh-my-zsh para usar ele. Edite o arquivo de configuração:

## Code Snippets

  gedit ~/.zshrc

Mude a linha da propriedade "ZSH_THEME" para usar o tema, substitua o tema pelo agnoster. A linha deve ficar assim:

## Code Snippets

  ZSH_THEME="agnoster"



9° Salve e reinicie seu pc......Agora é só alegria!
