---
title: 'Simplified Xamarin Forms #1'
layout: posts
date: '2017-01-23 07:56:39'
categories: Descomplica
comments: true
---

## O grande começo!
Olá, tudo bem ?

O blog sobre [Xamarin](https://www.xamarin.com/) é um projeto bem antigo meu, mas só agora pude "tirar do papel". Ao logo dessa nossa jornada vou tentar passar um pouco do conhecimento que eu adiquiri no mundo cross-mobile.

## Quem sou eu?

Sou Jonathan Braga, programador e aspirante a engenheiro mecatrônico. Como engenheiro mecatrônico, não consegui construir o [Reator Arc](https://en.wikipedia.org/wiki/Arc_reactor). Como programador, não gosto de café. 

## Vamos começar! 


O post de hoje vai ser uma breve introdução ao Xamarin Forms e no final vamos criar o nosso primeiro app. O mundo mudou quando a [Microsoft](https://www.microsoft.com/pt-br/) trouxe a Xamarin para a realidade open source, trouxe a facilidade na construção de apps. Agora não se é mais necessário três times de programadores ou um super programador que saiba as três linguagens para desenvolver apps para IOS, Android e WinPhone. Hoje, temos o [Xamarin Forms](https://developer.xamarin.com/guides/xamarin-forms/) que proporciona o compartilhamento de código e assim a construção de apps nativos! 


<div class="row">
	<div class="col s4 center-on-small-only center">
		<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/descomplicaXamarin1/android.png" alt="android"  style="width:50%" >
		</div>
	</div>
		<div class="col s4 center-on-small-only center">
		<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/descomplicaXamarin1/windows.png" alt="winphone"  style="width:50%" >
		</div>
	</div>
		<div class="col s4 center-on-small-only center">
		<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/descomplicaXamarin1/apple.png" alt="apple"  style="width:50%" >
		</div>
	</div>
</div>

Xamarin Forms, proporciona todo o conforto da linguagem C# e ainda nos permite usar API nativas de cada plataforma.

## Let's Code!


Nesse exemplo vamos construir um app bem simples usando o Visual Studio. Vamos construir esse app para as três principais plataformas. Caso não possua o Xamarin Forms instalado [Clique aqui](https://msdn.microsoft.com/pt-br/library/mt613162.aspx?f=255&MSPPError=-2147217396).

Criando um Projeto Cross-Platform 
- File 
-  New 
-  Project 
-  Cross-Platform 
-  Blank Xaml App (Xamarin.Forms.Portable)

<div class="row">
	<div class="col s12 center-on-small-only center">
		<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/descomplicaXamarin1/tela1.png" alt="tela 1" style="width:70%" >
		</div>
	</div>
</div>

Após o projeto ser criado vamos analisar a estrutura dele.

<div class="row">
	<div class="col s12 center-on-small-only center">
		<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/descomplicaXamarin1/tela4.png" alt="tela 2" style="width:40%" >
		</div>
	</div>
</div>

Vemos que a nossa solução possui seis projetos dentro dela, mas queria destacar o App (Portable).
É onde fica localizado o nosso "código geral", nosso código compartilhado, onde vamos criar Models, Views, Chamadas de Web API etc.

Dentro do App (Portable) iremos encontrar o App.xaml.cs.

<script src="https://gist.github.com/jonathanbraga/3343dee96588108b9b2295e3766635e8.js"></script>

No App.xaml.cs é onde podemos fazer algumas configurações de iniciliação do app.

Ainda no App (Portable) iremos encontrar o MainPage.xaml, que é responsável por construir o layout do nosso app, ao expandir o MainPage.xaml iremos encontrar o seu Code Behind, MainPage.xaml.cs

- MainPage.xaml
- <script src="https://gist.github.com/jonathanbraga/94d89bd25bf04782ebe7584c78881d1c.js"></script>

- MainPage.xaml.cs
<script src="https://gist.github.com/jonathanbraga/11fe264fd4dbe810be08a861eb14cd39.js"></script>

Antes de rodar a nossa solução precisamos definir qual será o nosso StartUp project (Seleciona o projeto -> Click com o botão direito do mouse ->Set as StartUp project). Podemos escolher qualquer um dos seis projetos apresentados. Rodando a nossa solução nas três plataformas, teremos:

<div class="row">
	<div class="col s12 center-on-small-only center">
		<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/descomplicaXamarin1/tela3.png" alt="tela 3" style="width:30%">
		</div>
	</div>
</div>

Ao final da execução temos um app, totalmente nativo, obedecendo todas as regras de design e responsividade de cada plataforma.

## Hasta la vista baby! 
Espero que tenham gostado desse primero/teste post, espero que possamos aprender juntos nessa jornada!

**Forte abraço!**
