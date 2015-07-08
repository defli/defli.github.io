---
layout: post
title: "jQuery On Kullanımı"
date: 2015-07-08 20:48:58 +0300
comments: true
share: true
categories: 
---

JavaScript’de *addEventListener* ile ya da *jQuery* ile *$(element).click*(); vb. metodlar ile eklenen *event* - olay - sadece o anda DOM*’da olan elemanlara eklenir. Örneğin; 
{% highlight javascript%}
$(‘.kitaplar’).click(function() {
		alert(‘hello’);
});
{% endhighlight %}

diye bir metod yazarsanız o anda DOM’da hazır olan .kitaplar diye bir class - sınıf - ’i olan elemanlara dinleyici eklenecektir. Daha sonra mesela AJAX isteği sonucu oluşturulan *.kitaplar* sınıfına sahip elemanlara tıklanınca hiçbir şekilde metod çalışmazken eski yarattığınız elemanlar tıklanınca metod çalışacaktır. Çünkü *addEventListener* sadece çalıştırıldığı zaman hazır olan nesnelere dinleyici ekler. 

Bunun üzerinden iki şekilde gelebliriz. Birincisi;
{% highlight javascript%}
$(‘.kitaplar’).unbind(‘click’); // eski fonksiyonları temizleyelim
$(‘.kitaplar’).click(function() { // tekrar bind -bağlama- edelim
		alert(‘hello’);
});
{% endhighlight %}
Daha pratik olarak;
{% highlight javascript%}
$(‘body’).on(‘click’, ‘.kitaplar’, function() {
		alert(‘hello’);
});
{% endhighlight %}
İkinci örnekte *eventListener* ile *.kitaplar* nesnesini değil *body* etiketini dinlemeye başladık. dom’da her tıklama işlemi aslında body etiketinde olduğu için fonksiyonumuz her zaman çalışacaktır.

Dipnotlar:

1. DOM: (bkz. [Document Object Model](https://tr.wikipedia.org/wiki/Document_Object_Model) )
