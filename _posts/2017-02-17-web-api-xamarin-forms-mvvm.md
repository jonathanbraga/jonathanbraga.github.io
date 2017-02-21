---
title: Web API + Xamarin Forms + MVVM
layout: posts
comments: true
date: '2017-02-17 11:12:56'
categories: project
---

Fala galera tranquilo? Sei que passei um tempo sem postar, mas esse post vai compensar! Vamos criar um mini projeto, onde iremos fazer chamada de uma WEB API (News API), utilizaremos alguns componentes e faremos tudo isso usando a estrutura MVVM. Será um projeto bem simples e rapido onde tentarei dar uma noção bem básica de um projeto MVVM e de chamadas de APIs.

## News API 
O [News API](https://newsapi.org/) é uma API simples e fácil de usar que retorna metadados JSON para as manchetes atuais publicadas em uma variedade de fontes de notícias e blogs. Possui uma exelente documentação, bem fácil de se entender. Para utilizar basta criar uma conta no site.

## MVVM 
O padrão de arquitetura Model-View-ViewModel (MVVM) foi inventado para o XAML. O padrão impõe uma separação da interface do usuário XAML (View) dos dados subjacentes (Model) através de uma classe que serve como um intermediário entre a View e o Model (ViewModel). O View e o ViewModel são frequentemente ligados através do BindingContext.
<div class="row">
<div class="col s12 center-on-small-only center">
	<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/Projects/apinews/mvvm.png" alt="Xamarin site image" style="width:70%" >
		</div>
</div>
</div>

## Let's Code
Antes de tudo preciso dizer que dessa vez não vou colocar todos os códigos, pois iria ficar muito grande o post, vou disponibilizar o código no meu github, [para acessar o código basta clicar aqui](https://github.com/jonathanbraga/Xamarin/tree/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM). Nesse nosso projeto vamos organizar a nossa Solution Explore de uma maneira um pouco diferente, se comparado com as outras. Iremos criar três pastas na nossa PCL, **Models**, **Views** e **ViewModels**, assim teremos a nossa estrutura **MVVM**.
<ul>
		<li>Project_API_NEWS</li>
		<ul>
				<li>Portable</li>
				<ul> 
						<li>Models</li>
						<li>Views</li>
						<li>ViewModels</li>
				</ul>
				<li>Doird</li>
				<li>IOS</li>
		</ul>
</ul>

### Vamos nessa! 

Antes de tudo vamos instalar alguns pacotes ao nosso projeto **Portable**, usando o manage nuget packages, instale o **Microsoft HTTP Client Libraries** e  **Newtonsoft.Json**.

### Entendendo a News API
Para que possamos usar a API da melhor forma, iremos precisar entender como ela é construida e como iremos utilizar esses dados.
<script src="https://gist.github.com/jonathanbraga/878609f9afac4292625c094b57053638.js"></script>
<br/>
Observe que na chamada da API, temos alguns campos, iremos utilizar os dados referente a articles, pois são os de mais relevância para o nosso projeto.

### Models

Agora que já se sabe quais são os campos que a API nos fornece e quais são os campos que irão ser utilizados, crie uma classe dentro da pasta **Models** e coloque o nome dessa classe de [**Article**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Models/Article.cs).

### Helpers 
Além das pastas que já criamos referentes ao **MVVM**, vamos criar mais uma, chamada de **Helpers**. Dentro de Helpers iremos criar uma Classe com o nome de [**ApiCaller**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Helpers/ApiCaller.cs). Será aqui onde iremos fazer a chamada da API. O endpoint que iremos utilizar será : <br/>
**https://newsapi.org/v1/articles?source=the-next-web&sortBy=latest&apiKey={my_api_key}**

### Controls 

Do mesmo jeito que foi feito com a pasta **Helpers**, vamos criar uma nova pasta com o nome de **Controls** e dentro de controls crie uma classe com o nome de [BindablePicker](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Controls/BindablePicker.cs) . Vamos criar essa classe com o intuito de ter o componente **Picker** com alguns dos atributos de uma **listview**.

### Service

Dentro de **ViewModels**  cire  uma pasta, chamada de **Service**, dentro dessa pasta crie uma interface com o Nome de [**INavigationService**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/ViewModels/Service/INavigationService.cs). Com essa interface poderemos navegar entre as Views.
Dentro de **View**  crie  uma pasta, chamada de **Service**, dentro dessa pasta crie uma classe com o Nome de [**NavigationService**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Views/Service/NavigationService.cs). 
Por fim, teremos que fazer algumas mudanças no nosso **App.xaml.cs**  <br/>
<script src="https://gist.github.com/jonathanbraga/b2ec208bd9765ffc031830ef9e89e6f4.js"></script>


### ViewModels 
Com toda a nossa parte de **Service** , **Controls** , **Helpers** e **Models** já configuradas, vamos partir para a constrção das nossas **VewModels**.
Em **ViewModels** crie uma classe chama de [**BaseViewModel**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/ViewModels/BaseViewModel.cs), essa classe Herda de **INotifyPropertyChanged**.
Após a implementação da classe **BaseViewModel**, podemos partir para o desenvolvimento das nossas **ViewModels** . 
#### HomeViewModel
[**HomeViewModel**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/ViewModels/HomeViewModel.cs)
