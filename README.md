# Ecommerce

## Description

This project is about a simple Ecommerce website created using Angular 10 as a front end application.There are two roles given, one for Admin who can  add, modfily and delete the products and the other is User who after login can add a comment or buy products and can also add the produts to the cart.



This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 10.1.1.

> ## Angular CLI version (10.1.1)
* `ng new` : 
The Angular CLI makes it easy to create an application that already works, right out of the box. It already follows our best practices!
* `ng generate` : 
Generate components, routes, services and pipes with a simple command. The CLI will also create simple test shells for all of these.
* `ng serve` : 
Easily test your app locally while developing.





```bash
$  npm install -g @angular/cli

$  ng new ecommerce

$  cd ecommerce

$  ng serve
```

## Project Structure

![Screenshot (327)](https://user-images.githubusercontent.com/74126223/118676922-7154ad00-b819-11eb-837b-351fba92f493.png)


> ## Install Bootstrap CSS framework

Bootstrap a framework to encourage consistency across internal tools. Before Bootstrap, various libraries were used for interface development, which led to inconsistencies and a high maintenance burden. 

Use the following command to install bootstrap in the project.

```bash
$  npm install bootstrap --save
```


> ## Install Angular Material

In addition to the install schematic, Angular Material comes with several schematics (like nav, table, address-form, etc.) that can be used to easily generate pre-built components in your application.

```bash
$  ng add @angular/material
```

## Angular Services

Angular services are singleton objects that get instantiated only once during the lifetime of an application. They contain methods that maintain data throughout the life of an application, i.e. data does not get refreshed and is available all the time. The main objective of a service is to organize and share business logic, models, or data and functions with different components of an Angular application.


An example of when to use services would be to transfer data from one controller to another custom service.


Why Should We Use Services in Angular? The separation of concerns is the main reason why Angular services came into existence. An Angular service is a stateless object and provides some very useful functions. These functions can be invoked from any component of Angular, like Controllers, Directives, etc. This helps in dividing the web application into small, different logical units which can be reused.


> ### Create Data services

This service will use Angular HTTPClient to send HTTP requests. You can see that its functions includes CRUD operations and finder method.

* ### Create these services in the service package

1. CartService
2. CategoryService
3. CommentService
4. OrderService
5. ProductService
6. TagService
7. UserService

```bash
$  ng generate service service/cart

$  ng generate service service/category

$  ng generate service service/comment

$  ng generate service service/order

$  ng generate service service/product

$  ng generate service service/tag

$  ng generate service service/user
```

> ## Font Awesome

Font Awesome is a font and icon toolkit based on CSS and Less. It was made by Dave Gandy for use with Bootstrap, and later was incorporated into the BootstrapCDN. Font Awesome has a 38% market share among those websites that use third-party font scripts on their platform, ranking it second place after Google Fonts.

```bash
<link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.2.0/css/all.css" integrity="sha384-hWVjflwFxL6sNzntih27bfxkr27PmbbK/iSvJ+a4+0owXq79v+lsFkW54bOGbiDQ" crossorigin="anonymous">

<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

```


## App Routing Module

In Angular, the best practice is to load and configure the router in a separate, top-level module that is dedicated to routing and imported by the root AppModule.
By convention, the module class name is AppRoutingModule and it belongs in the app-routing.module.ts in the src/app folder.

```javascript
import  { ProfileComponent }  from  './profile/profile.component';
 import  { DashboardComponent}  from  './dashboard/dashboard.component';
 import  { NgModule }  from  '@angular/core';
 import  { CommonModule }  from  '@angular/common';
 import  { Routes, RouterModule  }  from  '@angular/router';
 import  { CategoriesComponent }  from  './admin/categories/categories.component';
 import  { SangleProductComponent }  from  './ecommerce/sangle-product/sangle-product.component';
 import  { DisplayCategoryComponent }  from  './display-category/display-category.component';
 import  { DisplayTagComponent }  from  './display-tag/display-tag.component';

const routes: Routes = [
  { path: '', redirectTo: '/dashboard', pathMatch: 'full' },
  {
    path: 'dashboard',
    component: DashboardComponent,
  },
  {
    path: 'sangle/product/:idProduct',
    component: SangleProductComponent
  },
  {
    path: 'puy/product/:name',
    component: SangleProductComponent
  },
  {
    path: 'dsiplay-category/:idCategory',
    component: DisplayCategoryComponent
  },
  {
    path: 'display-tag/:idTag',
    component: DisplayTagComponent
  },
  {
    path: 'profile/:id',
    component: ProfileComponent,
    children: [
      {
        path: 'categories/:idCategory',
        component: CategoriesComponent
      }
    ]
  }
];

@NgModule({
  declarations: [],
  imports: [CommonModule, RouterModule.forRoot(routes)],
  exports: [RouterModule]
})
export class AppRoutingModule { }
```

## NgModules and JavaScript modules

The NgModule system is different from and unrelated to the JavaScript (ES2015) module system for managing collections of JavaScript objects. These are complementary module systems that you can use together to write your apps.


In JavaScript each file is a module and all objects defined in the file belong to that module. The module declares some objects to be public by marking them with the export key word. Other JavaScript modules use import statements to access public objects from other modules.


```javascript
import  { BrowserModule }  from  '@angular/platform-browser';
 import  { NgModule, CUSTOM_ELEMENTS_SCHEMA, NO_ERRORS_SCHEMA }  from  '@angular/core';
 import  { HttpClientModule }  from  '@angular/common/http';
 import  { AppComponent }  from  './app.component';
 import  { LoginComponent }  from  './login/login.component';
 import  { FormsModule }  from  '@angular/forms';
 import  { NoopAnimationsModule }  from  '@angular/platform-browser/animations';
 import  { MaterialModule }  from  './material-module';
 import  { ProfileComponent }  from  './profile/profile.component';
 import  { AppRoutingModule }  from  './app-routing.module';
 import  { DashboardComponent }  from  './dashboard/dashboard.component';
 import  { CategoriesComponent }  from  './admin/categories/categories.component';
 import  { AddCategoryComponent }  from  './admin/add-category/add-category.component';
 import  { AddProductComponent }  from  './admin/add-product/add-product.component';
 import  { AddTagComponent }  from  './admin/add-tag/add-tag.component';
 import  { AddTagToProductComponent }  from  './admin/add-tag-to-product/add-tag-to-product.component';
 import  { EcommerceComponent }  from  './ecommerce/ecommerce.component';
 import  { OrdersComponent }  from  './ecommerce/orders/orders.component';
 import  { ProductsComponent }  from  './ecommerce/products/products.component';
 import  { ShoppingCartComponent }  from  './ecommerce/shopping-cart/shopping-cart.component';
 import  { DatePipe }  from  '@angular/common';
 import  { SangleProductComponent }  from  './ecommerce/sangle-product/sangle-product.component';
 import  { UpdateProfileComponent }  from  './update-profile/update-profile.component';
 import  { DisplayCategoryComponent }  from  './display-category/display-category.component';
 import  { DisplayTagComponent }  from  './display-tag/display-tag.component';

@NgModule({
  declarations: [
    AppComponent,
    LoginComponent,
    ProfileComponent,
    DashboardComponent,
    CategoriesComponent,
    AddCategoryComponent,
    AddProductComponent,
    AddTagComponent,
    AddTagToProductComponent,
    EcommerceComponent,
    OrdersComponent,
    ProductsComponent,
    ShoppingCartComponent,
    SangleProductComponent,
    UpdateProfileComponent,
    DisplayCategoryComponent,
    DisplayTagComponent
  ],
  imports: [
    BrowserModule,
    HttpClientModule,
    FormsModule,
    NoopAnimationsModule,
    MaterialModule,
    AppRoutingModule
  ],
  providers: [DatePipe],
  bootstrap: [AppComponent],
  schemas: [ CUSTOM_ELEMENTS_SCHEMA, NO_ERRORS_SCHEMA ]
})
export class AppModule { }
```

## Conclusion

This is just a basic Application which uses Angular as a front end development tool. There are many changes to be made in future.


## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
