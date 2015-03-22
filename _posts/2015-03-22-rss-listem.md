---
layout: post
title: "RSS Listem"
date: 2015-03-22 21:13:53 +0200
comments: true
share: true
categories: 
---
Bir önceki yazıda RSS’i ne kadar sevdiğimi belirtmiştim. Şimdi de  RSS listemi paylaşmak istiyorum. Genel olarak frontend teknolojileri ağırlıklı bir liste. Sanırım [Paul Irish](http://www.paulirish.com/) paylaşmıştı temelde onun listesine dayanıyor.

RSS okuyucu olarak [Feedly’yi](http://feedly.com/) kullanıyordum fakat istatistik seçeneği olmamasından dolayı [Inoreader’a](https://www.inoreader.com/) geçtim. İstediğinizi seçebilirsiniz. Masaüstü uygulaması olarak da [Reeder for Mac](http://reederapp.com/mac/) kullanıyorum. Bu uygulama ile ilgili web servislerinden içeriği çekiyorum ve uygulamada okuduklarım web servisinde de okunmuş olarak işaretleniyor. Kullanışlı bir program. Mobil istemcisi de var fakat daha deneyemedim.

<span>
<a href=/downloads/subs.xml download>Can Küçükyılmaz’ın RSS Listesi</a>
</span>

Yeri gelmişken de “download” özniteliğinden -attribute- bahsetmek istiyorum. Eğer pdf, xml gibi tarayıcının kendi içerisinde gösterebileceği şeylere link veriyorsanız etiketin içine download yazarsanız tarayıcı ilgili içeriği kendisi göstermek yerine indirmeye çalışacaktır.

{% highlight bash%}
<a href=“/downloads/subs.xml” download>
	Can Küçükyılmaz’ın RSS Listesi
</a>
{% endhighlight%}
