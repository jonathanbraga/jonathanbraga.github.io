---
title: Web API + Xamarin Forms + MVVM
layout: posts
comments: true
date: '2017-02-17 11:12:56'
categories: project
---

Fala galera tranquilo? Sei que passei um tempo sem postar, mas esse post vai compensar! Vamos criar um mini projeto, onde iremos fazer chamada de uma WEB API (News API), utilizaremos alguns componentes e faremos tudo isso usando a estrutura MVVM. Será um projeto bem simples e rápido onde tentarei dar uma noção bem básica de um projeto MVVM e de chamadas de APIs.

## News API 
O [News API](https://newsapi.org/) é uma API simples e fácil de usar, retorna metadados JSON para as manchetes atuais publicadas. Possui uma variedade de fontes de notícias e blogs. Com uma exelente documentação, bem fácil de se entender. Para utilizar basta criar uma conta no site.

## MVVM 
O padrão de arquitetura Model-View-ViewModel (MVVM) foi inventado para o XAML. O padrão impõe uma separação da interface do usuário XAML (View) dos dados subjacentes (Model) através de uma classe que serve como um intermediário entre a View e o Model (ViewModel). O View e o ViewModel são frequentemente ligados através do Binding.
<div class="row">
<div class="col s12 center-on-small-only center">
	<div class="image-container">
			<img src="https://dl.dropboxusercontent.com/u/35899264/blog/img/Projects/apinews/mvvm.png" alt="Xamarin site image" style="width:70%" >
		</div>
</div>
</div>

## Let's Code
Antes de tudo preciso dizer que dessa vez não vou colocar todos os códigos, pois iria ficar muito grande o post, vou disponibilizar o código no meu github, [para acessar o código basta clicar aqui](https://github.com/jonathanbraga/Xamarin/tree/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM). Nesse nosso projeto vamos organizar a nossa Solution Explore de uma maneira um pouco diferente, se comparado com as outras. Iremos criar cinco pastas na nossa PCL, **Models**, **Views**, **ViewModels**, **Controls** e **Service**.
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
Para que possamos usar a API da melhor forma, temos que entender como ela é construida e como iremos utilizar esses dados.
<script src="https://gist.github.com/jonathanbraga/878609f9afac4292625c094b57053638.js"></script>
<br/>
Observe que na chamada da API, temos alguns campos, iremos utilizar os dados referente a articles, pois são os de mais relevância para o nosso projeto.

### Models

Agora que já se sabe quais são os campos que a API nos fornece e quais são os campos que irão ser utilizados, crie uma classe dentro da pasta **Models** e coloque o nome dessa classe de [**Article**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Models/Article.cs).

### Helpers 
Dentro de **Helpers**  crie uma **Classe** com o nome de [**ApiCaller**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Helpers/ApiCaller.cs). Será aqui onde iremos fazer a chamada da API. O endpoint que iremos utilizar será : <br/>
**https://newsapi.org/v1/articles?source=the-next-web&sortBy=latest&apiKey={my_api_key}**

### Controls 

Agora em **Controls**,  crie uma **classe** com o nome de [BindablePicker](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Controls/BindablePicker.cs) . Vamos criar essa classe com o intuito de ter o componente **Picker** com alguns dos atributos de uma **listview**, facilitando a implementação do nosso código.

### Service

Dentro de **ViewModels**  cire  uma pasta, chamada de **Service**, dentro dessa pasta crie uma **interface** com o nome de [**INavigationService**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/ViewModels/Service/INavigationService.cs). Com essa interface poderemos navegar entre as Views.
Dentro de **View**  crie  uma pasta, chamada de **Service**, dentro dessa pasta crie uma classe com o Nome de [**NavigationService**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Views/Service/NavigationService.cs). 
Por fim, teremos que fazer algumas mudanças no nosso **App.xaml.cs**  <br/>
<script src="https://gist.github.com/jonathanbraga/b2ec208bd9765ffc031830ef9e89e6f4.js"></script>


### ViewModels 
Com toda a nossa parte de **Service** , **Controls** , **Helpers** e **Models** já prontas, vamos partir para a contrução das nossas **VewModels**.
Em **ViewModels** crie uma classe chama de [**BaseViewModel**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/ViewModels/BaseViewModel.cs), essa classe Herda de **INotifyPropertyChanged**, responsável por toda a mágica do MVVM.
Antes de criar as nossas ViewModels, vamos definir o que terá em cada View. Teremos basicamente três Views, **SelectJournalView** -onde vamos poder escolher de qual jornal ler as  manchetes-, **HomeView** -lista de todas as manchetes do jornal selecionado-, **SiteView** -página da manchete selecionada-. 
[**SelectJournalViewModel**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/ViewModels/SelectJournalViewModel.cs), [**HomeViewModel**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/ViewModels/HomeViewModel.cs), [**SiteViewViewModel**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/ViewModels/SiteViewModel.cs).

### Views 

Finalmente vamos para a parte final do projeto, como já definimos a organização das páginas, vamos direto para o desenvolvimento. Na pasta **Views** crie três **FormPage.xaml**, [**SelectJournalView**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Views/SelectJournalView.xaml), [**HomeView**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Views/HomeView.xaml),  [**SiteView**](https://github.com/jonathanbraga/Xamarin/blob/master/NewsApi/NewsApi%2BListView%2BMVVM/NewsApi_ListView_MVVM/Views/SiteView.xaml.cs).

Não esquecer de colocar o **BindinContext** no code behind, aponete para a **ViewModel** correspondente.

## Hasta la vista baby! 

Espero que tenham gostado desse post! O site mudou um pouco pra muito, algumas coisas não vão funcionar 100% ainda, mas aos poucos estarei melhorando. Agora vou poder acompanhar o feedback de vocês vias comentário no post, vamos nos ajudar para que juntos possamos melhorar :) 
