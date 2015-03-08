---
layout: post
title: "Neden Jekyll kullanıyorum?"
date: 2015-03-08 15:26:34 +0200
comments: true
share: true
categories: 
---

Bir blog tutmaya karar verdiğiniz zaman önünüze bir çok alternatif çıkar. Blogger, Wordpress hatta benim yaptığım [Sincapp](https://wwww.sincapp.com).

Eğer hosted* çözümler kullanacaksınız Blogger ve Wordpress işinizi fazlasıyla görebilir. Fakat bu durumda sizin özelleştirme seçenekleriniz kısalır. Esnekliğiniz tamamen platform sağlayıcıların insafına kalmıştır. Örneğin Wordpress.com’dan blog açtıysanız belirli eklentileri kurabilirsiniz, her eklentiyi kuramazsınız.

Eğer kendi sunucumda kullanacağım sistemi derseniz en güçlü alternatif Wordpress gibi duruyor. Wordpress php, mysql kullanan dinamik bir cms**’dir. 

Jekyll özeline dönersek, Jekyll tamamen statik bir site oluşturucudur. Şöyle ki siz yazılarınızı _posts dizinine aşağıdaki formatta yazarsınız.

{% highlight bash%}
—
layout: post
title: “Yazınızın başlığı”
date: 2015-03-08 15:26:34 +0200
comments: true
share: true
categories: 
—
İçerik buraya gelecek
{% endhighlight %}

Dosya adı: 2015-03-08-neden-jekyll-kullaniyorum.md

Konsolda **jekyll build** dediğiniz zaman otomatik olarak statik sayfalarınız oluşturulur. Statik sayfalarınız **_site** dizinin altındadır. 

**jekyll serve** derseniz statik dosyalar yine otomatik oluşturulur ve **localhost:4000** adresinde servis edilmeye başlar. Jekyll ilgili kurulum ve konfigürasyon ayarlarını bir sonraki gönderimde paylaşmayı düşünüyorum. Şimdi Jekyll’nin artılarına gelirsek;

### 1. Jekyll hızlıdır
Jekyll klasik blog sistemlerinin aksine php ya da başka bir dil kullanmaz, mysql vs. gibi bir veritabanı kullanmaz. Sitenizin içeriği tamamen html formatında statik bir şekilde durur.

### 2. Jekyll güvenlidir
Arada mysql ve php olmadığı için Jekyll’de güvenlik açığı minimum düzeydedir. Eğer github ya da host ettiğiniz başka bir yerin şifresini çaldırmazsanız sitenizin hackleme ihtimali*** çok düşüktür.

### 3. Hosting ücretsizdir
Jekyll github pages ile kullanabilirsiniz. Siteniz Github sunucularında durur ve bunun için hosting ücreti ödemezseniz.

### 4. Özelleştirme
Jekyll’nin çok basit bir template şablonu vardır. Çok kolay bir şekilde istediğiniz gibi özelleştirebilirsiniz. Üstelik post’larınızın içine değişik içerik tipleri koymanız da çok kolaydır.

### 5. Geek’ler için biçilmiş kaftandır
Eğer github’a açık kaynak kodlu şeyler koyuyorsanız bunlar için sayfalar yapmak Jekyll ile çok kolaydır.

### 6. Markdown’ların gücü
Jekyll ile klasik wysiwyg kullanmazsanız her şey markdown formatındadır. Böylelikle her şeyi klavyenizden halledebilirsiniz.


*Dipnotlar*:

1. Hosted kelimesini tam karşılayan Türkçe bir kelime bulamadım. Bundan kasıt sitenizi sizin yerinize bulutta host eden çözümlerdir.

2. CMS: Content management service, türkçesi İçerik yönetim sistemi.

3. Hacklenmeniz için Github’ın ya da sitenizi host ettiğiniz sunucunun hacklenmesi gerekir. 