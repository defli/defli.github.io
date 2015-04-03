---
layout: post
title: "Bulut'un geleceği melez uygulamalarda mı?"
date: 2015-03-21 23:03:58 +0200
comments: true
share: true
categories: 
---
Son yıllarda bulut -cloud- bilişim çok popüler oldu. Bulut bilişim kısaca kullandığımız servislerin kendi bilgisayarlarımızda değil de uzaktaki bir sunucuda çalışması mantığına dayanıyor^(1). Web uygulamaları - ki bunlar gelişmiş internet siteleri - bulutta önemli bir yer kaplıyor.

Her ne kadar HTML5 ile gelen yeni özellikler, Javascript çatılarının -framework- hızlı gelişmesi biz web programcılarına muazzam olanaklar ve hız sağlasa da hala yerli -native-, yani bilgisayarda tek başına çalışan uygulamaların performasından epeyce uzağız. İnternet tarayıcıları -browser- her ne kadar gelişmiş olsa da işletim sistemi düzeyinde API**’lara erişimimiz çok kısıtlı. 

Mesela ben ağ -network- üzerinde başka bilgisayarlarla iletişim kuracak bir uygulama yapmak istiyorsam bu noktada o bilgisayar için bilgisayarda çalışan bir uygulamaya ihtiyacım var. 

Ya da şunu düşünelim, kritik bir uygulamamız var ve bu uygulama internet bağlantısı kopsa dahi çalışması gerekiyor. 

İşte bu noktada melez -hybrid- uygulamalar ortaya çıkıyor. Yani hem web uygulaması ve hem de bilgisayar üzerinde web sunucusu ile iletişime geçen bir masaüstü uygulaması. Bu sayede iki platformun da avantajlarını en üst düzeyde kullanabiliyoruz.

Artık uygulamalarımızı sadece web tabanlı, sadece işletim sistemine bağımlı ya da sadece mobil için geliştirmiyoruz. Çünkü insanlar sadece bir platformda değil. Bu yüzden API tabanlı uygulamalar*** geliştirmeliyiz.

Bu yazıyı [Mac Reeder App](http://reederapp.com/mac/) isimli RSS**** uygulamasını satın aldıktan sonra yazmaya karar verdim. Gerçekten muazzam bir uygulama ve bir melez uygulama örneği. Çünkü aslında [Feedly](http://www.feedly.com) ya da başka bir RSS servisi ile senkron çalışıyor. Üstelik RSS yayınlayan sitelerin ille de siteme girmelisin zorlamasına da harika bir çözümü var. Sadece ilgili yazıyı uygulama içerisinde gösteriyor.

Dipnotlar:

1. İşin ilginç tarafı ilk bilgisayarlar da sadece istemci gibi davranıyordu. İnsanlar terminallerinden ana sunucuya bağlanıp işlerini yapıyorlardı. Sonra bildiğimiz manada kendi üzerinde çalışan bilgisayarlar çıktı. Acaba başlayan her şey sonradan ilk haline mi dönüyor?

2. API’nin açılımı Application Programming Interface, başka programların veya kod parçalarının belirli özelliklerini kullanabilmemizi sağlayan metodlar.

3. API driven development. Merkezde tekil bir API olur ve diğer her uygulama, web sitesi, masaüstü uygulaması buna bağlıdır.

4. RSS gerçekten en sevdiğim web teknolojilerinden birisi. Kısaca takip ettiğiniz sitelere yeni yazılar geldiği zaman haberdar oluyorsunuz ve yazıyı hemen okuyabiliyorsunuz. Detaylı açıklaması için [wikipedia](http://tr.wikipedia.org/wiki/RSS).