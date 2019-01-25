---
layout: post
title: TypeScript'e Giriş
tags: [TypeScript, typescript,TS,Javascript, Neden Typescript, TSC]
excerpt_separator: <!--more-->
---

Merhaba,  
Bu yazıda Angular ile geliştirme sürecinde kullandığım dil olan Typescript diline ufak bir giriş yapmak istedim. Typescript nedir, neden ihtiyaç duyuyoruz
nasıl bir yapıya sahip gibi sorulara cevap vermeye çalışıyor olacağım. Bu sorular ilk kez dili araştırmaya başladığımda aklıma takılan, kendimce cevaplarını topladığım sorular. Ayrıca bu yazı sonrasında TypeScript ile "Hello World" uygulaması geliştirme kısmına da değinmiş olacağım.
<!--more-->




## Typescript Nedir?
Typescript, Javascript'in bir süpersetidir. Kısaca, Javascript'e ait özellikleri miras olarak alır ve kendince yeni özellikler ekleyerek yeni bir dil ortaya koyar. Böylelikle Javascript'te yapabildiğiniz herşeyi Typescript'te de yapabilir hatta üzerine daha fazla özelliğe de sahip olmuş olursunuz. TypeScript büyük uygulamaların daha kolay yazılması ve yönetilebilmesi hedefiyle, Microsoft tarafından geliştirilmiştir.  

Aslında çekirdekte yine Javascript'in bulunması sebebiyle, TypeScript yine günün sonunda Javascript'e derlenir. Bu süreç, TypeScript Compiler (TSC) ile gerçekleşir ve TypeScript Javascript'e transpile edilir.  

## TypeScript Neler ile Öne Çıkmaktadır?

* Static Type Checking
    - TS sayesinde değişkenlere, parametrelere ve fonksiyonlara tip atanabilmektedir. 
        Bu opsiyonel olmakla beraber,projede bugları önlemekte ve gelecekte sorunların yaşanması durumlarını 
        engellemektedir. Ayrıca kod daha okunaklı olmaktadır.
        - Kullanılabilecek tipler;
            - String
            - Number
            - Boolean 
            - Array
            - Any
            - Void
            - Null
            - Tuple
            - Enum
            - Generics

* Class based objects
    - Böylelikle Javascript'e OOP yapısı katılmış olur ve bununla classlar, propertyler, metodlar tanımlanır.
    Ayrıca prototype kullanımına artık gerek kalmaz, encapsulation yapıya dahil edilmiştir.
    Kalıtım, erişim belirteçleri kullanımda olur.
    - Abstraction çok daha açık bir şekilde tanımlanır ve takibi daha kolay olur.
    - Interface tanımlama olanağı ile beraber dizayn edilecek sistemin public alt sistem tanımlamaları belirlenir ve sistemdeki
    bağlantılar ortaya çıkar.

* Modüler Yapı  
    Diğer dosyalar ve komponentler import edilebilir

* ES6 Standartları

* Tooling
    - Typescript'in getirdiği intellisense, navigation ve refactoring,  gibi özellikler de öne çıkmasında yardımcıdır.
    Büyük projeler için dizayn edilen Typescript bu toollar ile işleri kolaylaştırır

## Neden Typescript ?

Angularda yahut diğer ekosistemlerde de Typescript'in kullanımı görünmektedir.Neden Typescript kullanıldı, neden böyle bir dile ihtiyaç oldu gibi
sorular aklınıza gelebilir. Bunun temeldeki sebebi dynamic typinge sahip Javascript dili ile geliştirilen projelerin ölçeklerinin büyümesiyle
projelerin yönetiminin zorlaşmasından kaynaklanmaktadır.  
Birden fazla developerın üstünde çalıştığı bir projede dynamic typing çeşitli sıkıntılara, gereksiz
kod tekrarlarına veya değişken tanımlamalarına sebep olabilmekte, projedeki ilişki net olarak ortaya çıkamamaktadır.  

TypeScript, iyi yazılmış ve statik olarak yazılmış bir dilin kullanışlılığının % 95'ini alır ve JavaScript ekosistemine getirir. Böylelikle hala ES6'da 
hala aynı çekirdek kütüphaneleri, 3.parti kütüphaneleri ve toolları kullanmaya devam ederken, çok daha kolay yönetilebilen, type-safe bir proje ortaya çıkar.
Bundandır ki, Angular gibi bir frontend "framework" Typescript kullanmaktadır.  


## TypeScript ile Hello World Uygulaması

> Bunu uygulamak için, nodejs ve npm'in kurulu olması gereklidir. Bütün işlemler Ubuntu üzerinde gerçekleştirilecektir.
Bunun için;  
```javascript
sudo apt install nodejs npm 
```
komutu yeterlidir.

Sonrasında, aşağıdaki komutla typescript kurulumu node package manager aracılığı ile tamamlanmış olur.
```javascript
$ sudo npm install -g typescript
```
böylelikle Typescript compilera artık erişimimiz bulunmakta.  
Yeni bir "hello" adında bir TypeScript dosyası yaratalım, ve bir fonksiyon oluşturalım;
```typescript
function logTS(message : string){
    console.log(message);
}
logTS("Hello World");
```
bundan sonra da tyscript compiler ile transpile işlemini gerçekleştirelim.
```javascript
$ tsc hello.ts
```
bu bulunduğu klasörde hello.js diye bir javascript dosyası oluşturur ve içerisinde 
```javascript
function logTS(message) {
    console.log(message);
}
logTS("Hello World");
```
bulunur.  
Sonrasında "node hello.js" komutuyla çalıştırılan javascript dosyası, konsola hello world çıktısını basar.

## Kaynaklar
[Angular 2 in TypeScript](https://vsavkin.com/writing-angular-2-in-typescript-1fa77c78d8e8)  
[TypeScript Crash Course](https://www.youtube.com/watch?v=NjN00cM18Z4)













