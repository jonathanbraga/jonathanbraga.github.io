---
title: Bindable ItemSelected + Xamarin Forms
layout: posts
date: '2017-02-23 09:38:25'
categories: Descomplica
comments: true
---

Fala galera, tranquilo? O post de hoje vai ser bem rápido e simples, hoje é mais um **descomplica**, vamos fazer um exemplo falando sobre
como selecionar um **Item** de uma **ListView** via **Binding** (o famoso *Bindable Item Selected* ).



<div class="row">
<div class="col s12 center-on-small-only center">
	<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/descomplicaXamarin1/bsi.gif" alt="Gif" style="width:30%" >
		</div>
</div>
</div>

## Let's Code 

##### [**Project code**](https://github.com/jonathanbraga/Xamarin/tree/master/BindableItemSelected/BindableItemSelected/BindableItemSelected)


Como já falei o projeto é muito simples, basicamente vai ser uma lista com o nome e idade de algumas pessoas e ao clicar em um dos nomes aparecerá todas as informações da pessoa escolhida. Vamos começar criando as famosas pastas, **Models**, **Views** e **ViewModels** no nosso projeto **Portable**.



Dentro de Models crie uma **classe** com o nome de [**Person**](https://github.com/jonathanbraga/Xamarin/blob/master/BindableItemSelected/BindableItemSelected/BindableItemSelected/Models/Person.cs), nesse exemplo eu escolhi criar 
uma lista de pessoas com algumas informações, mas poderia ser qualquer outra coisa. Em **ViewModels** crie uma subpasta, nomeando de **Services**, dentro dela vamos criar uma interface e repetiremos o processo em **Views** (no lugar de uma interface será uma classe), não vou entrar em muitos
detalhes pois alguns passos já foram feitos no [**post passado**](http://jonathanbraga.com/project/2017/02/17/web-api-xamarin-forms-mvvm.html), caso tenha dúvida só olhar no [repositório do projeto](https://github.com/jonathanbraga/Xamarin/tree/master/BindableItemSelected/BindableItemSelected/BindableItemSelected). Ainda em **ViewModels**, crie uma classe com o nome de [**HomeViewModel**](https://github.com/jonathanbraga/Xamarin/blob/master/BindableItemSelected/BindableItemSelected/BindableItemSelected/ViewModels/HomeViewModel.cs), atenção para algumas coisas: 

- **ItemSelected** é o método que dispara com à ação do click em algum item da lista;
- **Persons** lista de pessoas que conterá na ListView;


Para Finalizar, em **Views** crie um **Forms Xaml Page** e coloque o nome de [**HomeView**](https://github.com/jonathanbraga/Xamarin/blob/master/BindableItemSelected/BindableItemSelected/BindableItemSelected/Views/HomeView.xaml) (mantendo o padrão MVVM - **View** {nome_do_arquivo}View.xaml e **ViewModel** {nome_do_arquivo}ViewModel.cs). **Não esquercer do BindingContext = new HomeViewModel();**

## Hasta la vista baby!
Brigado por ter acompanhado mais um post! Até a próxima :)