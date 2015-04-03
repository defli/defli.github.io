---
layout: post
title: "Javascript'te scope ve closure mantığı"
date: 2015-04-04 00:35:13 +0300
comments: true
share: true
categories: 
---

Javascript’te eğer dikkatli olmazsak değişkenlerin birbirine girmesi çok kolay. Yani;
{% highlight javascript%}
var hello = “world”;
{% endhighlight%}

diye bir değişken tanımlarsak aslında biz bu değişkeni window nesnesine entegre etmiş oluyoruz. Gelin şu kodu deneyelim.

{% highlight javascript%}
console.log(hello);
console.log(window.hello);
// Çıktı: world
// Çıktı: world
{% endhighlight%}

Gördüğünüz gibi iki durumda bize aynı değeri dönüyor. Eğer çok basit bir javascript kodu yazıyorsak ve bu, sayfada çalışan tek kod ise bir sorun olmayacak ama artık kompleks uygulamalar geliştirdiğimiz için bu durum büyük bir problem. Aslında Javascript’te her fonksiyonun kendine has bir scope - etki alanı- var. Yani eğer bir fonksiyonunun içinde değişken tanımlarsanız bu değişkene dışarıdan ulaşamazsanız. Örneğin;

<iframe width=100% height=300 src=//jsfiddle.net/defli/1yu0qnva/1/embedded/js,result/ allowfullscreen=allowfullscreen frameborder=0></iframe>

Ama fonksiyonun içinde tanımlanan “**var hello**”’yu sadece “**hello**” ile değiştirirsek dışardan erişebiliriz;

<iframe width=100% height=300 src=//jsfiddle.net/defli/1yu0qnva/2/embedded/js,result/ allowfullscreen=allowfullscreen frameborder=0></iframe>

Çünkü ikinci örnekte yaptığımız değişiklik ile değişkeni global scope’a yani window nesnesine bağladık. Ve bu hiç de iyi bir yöntem değil. Çünkü yazdığımız kodlar başka kodları bozabilir, aynı değişkeni kullanan farklı fonksiyonlar olabilir ve biz kodları birleştirdiğimiz zaman bütün yapı karışır.

Eğer global scope’a bir değer atamak istiyorsak bile bu değişkeni fonksiyonun dışında tanımlamalıyız.

<iframe width=100% height=300 src=//jsfiddle.net/defli/1yu0qnva/3/embedded/js,result/ allowfullscreen=allowfullscreen frameborder=0></iframe>

Şimdi basit olarak scope’un nasıl işlediğini anladık. Bir kısayol uygulayalım ve şu çirkin foo(); fonksiyon çağırmasından kurtulalım.

<iframe width=100% height=300 src=//jsfiddle.net/defli/1yu0qnva/5/embedded/js,result/ allowfullscreen=allowfullscreen frameborder=0></iframe>

Peki iki tane farklı fonksiyon varsa ve bu fonksiyonlar birbirine bağımlıysa yani birbirine scope’una erişmek istiyorsak ne yapacağız? Bu değişkenleri global scope’a mı yazacağız? Tabi ki hayır. Bir fonksiyondan diğerini çağıracağız. Örneğin;

<iframe width=100% height=300 src=//jsfiddle.net/defli/1yu0qnva/6/embedded/js,result/ allowfullscreen=allowfullscreen frameborder=0></iframe>

Şimdi burada işler ilginçleşiyor. Mesela benim sadece bir kere yapılacak işlemlerim var. Ondan sonra buna bağımlı başka bir işlem var ve ben makbul* bir programcıyım. O zaman ne yaparım? Her seferinde aynı işlemi tekrar tekrar yapmam bir kere yaptırır sonra o sonuca göre işlemlerimi yaparım. Ama nasıl? Şöyle ki;

<iframe width=100% height=300 src=//jsfiddle.net/defli/1yu0qnva/7/embedded/js,result/ allowfullscreen=allowfullscreen frameborder=0></iframe>

Peki biz ne yaptık? Önce ilk fonksiyonu çağırıp, değişkene atayarak - **var ikiCarpi = artiBir(1);** birinci fonksiyonu çalıştırdık. Ve ikinci fonksiyonu **return** ederek ikinci fonksiyonu değişkene eşitledik. Buna closure(1) diyoruz. Daha sonra closure’ı **ikiCarpi(2);** çağırdık. 

ikiCarpi aslında bir değişken ve bu değişken artiBir() fonksiyonundan dönen fonksiyonla eşitlenmiş. Bu yüzden fonksiyon gibi davranıyor.

İyi de üst scope’a erişilemiyorsa fonksiyon nasıl **sayi** değişkenini aldı ve çalıştı? Fonksiyon çalıştı çünkü fonksiyonlar bir üst ya da “n” üst sayıdaki fonksiyonların scope’una erişebilir ama üst fonksiyonlar alt fonksiyonların scope’una - içindeki değişkenlere - erişemez.

Scope ve closure genel olarak böyle. Aslında closure’lar işimizi çok kolaylaştıran bir pattern(2)  ayrıca frontend mülakatlarında sorulan defakto soru. Temelini anlarsak çok zevkli kullanım alanları var.

Dipnotlar:

1. Burada makbul’den kasıt *tembelliktir. Tembel programcı her zaman daha kısa bir yol bulur ve işin kompleksliğini azaltır :)

2. Design Pattern: Türkçesi tasarım desenleri, daha önce başka programcılar tarafından bulunmuş ve sürekli uygulanarak geçerliliği kanıtlanmış programlama yöntemleri örn. Observer, Singleton, MVC vs.

3. Kodları çalıştırmak için kendi bilgisayarına yazmanız gerekmiyor üstte javascript yazan sekmeyi result’a getirirseniz kodlar çalışacaktır. Tabi konsolunuzu açmayı unutmayın :)



