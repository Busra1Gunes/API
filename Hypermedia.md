<p><h1 style=color:red> HYPERMEDİA-HATEOAS</h1> </p>
<p>RESTful API'de "hypermedia"(ya da daha yaygın olarak HATEOAS) terimi , API'nin yanıtlarının dinamik ve etkileşimli olmasını ifade eder. Bu işlemciye (client) API'nin nasıl kullanılacağı hakkında bilgi sağlayarak, API'nin sunduğu kaynaklarla nasıl etkileşimde bulunabileceğini belirtir </p>
<p><h3>Hypermedia ve HATEOAS Nedir?<h4></p>
<p><strong>Hypermedia: </strong>Web üzerinde içerikler arasında köprüler sağlayan ve bu köprüler aracılığı ile gezinmeyi mümküm kılan medya öğeleridir. RESTful API'lerde hypermedia, API'nin yanıtlarına ilgili kaynaklara erişim sağlamak için bağlantılar eklemeyi ifade eder</p>
<p><strong>HATEOAS: </strong>Bu prensip RESTful API'lerin bir kaynağın durumunu değiştirmek veya yeni kaynaklara erişmek için hiper bağlantılar içermesidir. HATEOAS, işlemcilerin API'nin mevcut durumuna göre yönlendirilmesini sağlar </p>
<br>
<p><h3>HATEOAS'ın Temel Özellikleri</h3></p>
<p> <strong>1.Bağlantılar </strong>: API yanıtları, mevcut kaynaklara ve işlemlere ulaşmak için gerekli olan bağlantıları içerir. Örneğin bir kullanıcı profil yanıtında "profile update" ve "delete profile" gibi bağlantıları bulabilir </p>
<p> <strong>2.Dinamik ve Yönlendirme </strong>: İstemci, API'yi kullanırken hangi adımların atılabileceğini ve hangi işlemlerin yapılabileceğini , yanıt içinde yer alan bağlantılar aracılığı ile öğrenir </p>
<p> <strong>3.Durum Bilgisi </strong>: Her kaynak,bu kaynağın nasıl güncellenebileceği veya başka kaynaklara nasıl erişebileceği hakkında bilgi sunar. Bu api'nin sunduğu kaynakların ve işlemlerin dinamik olarak değişmesini sağlar </p>
<p><h4>HATEOAS Kullanımına Örnek</h4></p>
<p>Bir e-ticaret API'ai düşünelim. Bir ürün kaydını aldığınızda, yanıt içinde o ürünü güncellemek için bir bağlantı (örneğin /products/{id}/update) ve ürünü silmek için başka bir bağlantı içerebilir. Ayrıca, kullanıcıların bu ürünle ilgili yorumlar bırakabileceği bir bağlantıda bulunabilir  </p>

<p> Örnek JSON yanıtı:</p>
<p>{</p>
<p> "id":1,</p>
<p> "name":Örnek Ürün,</p>
<p> "price":100.0,</p>
<p> "links":  {</p>
<p> "self":"/products/1/update",</p>
<p> "update":"/products/1/delete",</p>
<p> "update":"/products/1/reviews",</p>
<p>   }</p>
<p>}</p>

