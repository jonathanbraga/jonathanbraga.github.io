---
title: Layouts and Components Xamarin.Forms
layout: posts
comments: true
date: '2017-01-24 10:40:56'
categories: components
---

## Layout 
O Xamarin Forms possui alguns layouts para a organização da tela do dispositivo. Cada layout é responsável por uma determinada organização de componentes na tela do dispositivo. Abaixo segue os layouts que o Xamarin.Forms nos fornece:

- StackLayout <br/>
Na minha humilde opinião esse é o layout mais usado e o mais fácil de se utilizar. Por padrão posiciona verticalmente os componentes.

- AbsoluteLayout <br/>
Usado para poder criar uma View que possua elementos de posição específica.

- RelativeLayout <br/>
Geralmente é usado quando se precisar ajustar um componente a qualquer tamanho de tela

- Grid <br/>
Bastante poderoso quando o assunto é definir tamanhos proporcionais de tela para cada componente. Nos permite dividir a tela em linhas e colunas e assim reorganizar na maneira desejada

- ScrollViewÉ usado para mostrar componentes que não cabem na tela do dispositivo. <br/>
Na minha humilde opinião esse é o layout mais usado e o mais fácil de se utilizar. Por padrão posiciona verticalmente os componentes.

<center>
<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/Components/Layouts%2BComponentes/Layouts.png" alt="tela 1" >
</center>
<br/>

## Componentes 

Xamarin Forms nos oferece os principais componentes presentes em cada plataforma, como:

- Button 
- Slider 
- SearchBar 
- DatePicker 
- Map 
- ListView 
- Entry 
- Switch 
- Label

A grande vantagem de usar esses componentes via Xamarin Forms é que cada componente é desenhado nativamente, ou seja, um Button terá uma "única escrita de código" (via xaml), mas terá ao menos três formas diferentes de design (IOS, Android e WinPhone).

## Let's Code! 

Vamos criar um app de uma forma bem simples e prática, demonstrando em que situações usar alguns dos layouts e componentes. Ao criando um projeto Xamarin.Forms.Portable abra o arquivo MainPage.xaml 
<br/> 
Solution Explore
<ul>
	<li>AppXamrin (Portable)</li>
		<ul>
			<li>App.xaml</li>
			<ul>
					<li>App.xaml.cs</li>
			</ul>
				<ul>
					<li><b>MainPage.xaml</b></li>
					<ul>
						<li>MainPage.xaml.cs</li>
					</ul>
			</ul>
	</ul>
</ul>

### Vamos nessa!

- StackLayout + Label + Button

* MainPage.xaml
<script src="https://gist.github.com/jonathanbraga/ee38eeb7acf509321e84d5cfa5d16b83.js"></script>

<center>
<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/Components/Layouts%2BComponentes/tela3.png" alt="tela 3" style="width:35%">
</center>
<br/>

- StackLayout + Label + Button + Entry + Grid
- MainPage.xaml
<script src="https://gist.github.com/jonathanbraga/be14d991e275b778bba55aa9e42a57c3.js"></script>

<center>
<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/Components/Layouts%2BComponentes/tela1.png" alt="tela 3" style="width:35%">
</center>
<br/>

Para cada componente temos algumas propriedades, no segundo exemplo podemos ver isso de uma forma mais clara, como por exemplo:

- Padding <br/>
É a definição de margem do layout, podemos inserir um valor único que irá servir para left, top, right, and bottom ou então difinir o valor de cada um (na respectiva ordem).
- ColumnDefinition <br/>
Será a maneira com que iremos configurar a divisão de nossa tela (nesse caso em colunas). Podemos usar tanto o "*" (o que resta da tela) como o "Auto" (o que o componente precisa).
- HorizontalTextAlignment <br/>
É a organização horizontal do texto.

## Hasta la vista baby!
Espero que tenham gostado desse post, espero que possamos aprender juntos nessa jornada!

**Forte Abraço!**