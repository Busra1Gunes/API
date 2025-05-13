<div align="center">
  <h1 style="color:#2c3e50;">🧩 HYPERMEDİA-HATEOAS</h1>
</div>
<blockquote>
RESTful API'de "hypermedia"(ya da daha yaygın olarak HATEOAS) terimi , API'nin yanıtlarının dinamik ve etkileşimli olmasını ifade eder. Bu işlemciye (client) API'nin nasıl kullanılacağı hakkında bilgi sağlayarak, API'nin sunduğu kaynaklarla nasıl etkileşimde bulunabileceğini belirtir
</blockquote>
<p></p>
<h2>🌐 Hypermedia ve HATEOAS Nedir?</h2>
<blockquote>
<strong>Hypermedia: </strong>Web üzerinde içerikler arasında köprüler sağlayan ve bu köprüler aracılığı ile gezinmeyi mümküm kılan medya öğeleridir. RESTful API'lerde hypermedia, API'nin yanıtlarına ilgili kaynaklara erişim sağlamak için bağlantılar eklemeyi ifade eder</p>
</blockquote>
<blockquote>
<p><strong>HATEOAS: </strong>Bu prensip RESTful API'lerin bir kaynağın durumunu değiştirmek veya yeni kaynaklara erişmek için hiper bağlantılar içermesidir. HATEOAS, işlemcilerin API'nin mevcut durumuna göre yönlendirilmesini sağlar </p>
</blockquote>

<p><h4>HATEOAS'ın Temel Özellikleri</h4>
<blockquote>
<li>Bağlantılar : API yanıtları, mevcut kaynaklara ve işlemlere ulaşmak için gerekli olan bağlantıları içerir. Örneğin bir kullanıcı profil yanıtında "profile update" ve "delete profile" gibi bağlantıları bulabilir</li>
<li>Dinamik ve Yönlendirme : İstemci, API'yi kullanırken hangi adımların atılabileceğini ve hangi işlemlerin yapılabileceğini , yanıt içinde yer alan bağlantılar aracılığı ile öğrenir</li>
<li>Durum Bilgisi : Her kaynak,bu kaynağın nasıl güncellenebileceği veya başka kaynaklara nasıl erişebileceği hakkında bilgi sunar. Bu api'nin sunduğu kaynakların ve işlemlerin dinamik olarak değişmesini sağlar</li>
</p>
</blockquote>


<hr>

<p><h4>HATEOAS Kullanımına Örnek</h4>
<p>Bir e-ticaret API'ai düşünelim. Bir ürün kaydını aldığınızda, yanıt içinde o ürünü güncellemek için bir bağlantı (örneğin /products/{id}/update) ve ürünü silmek için başka bir bağlantı içerebilir. Ayrıca, kullanıcıların bu ürünle ilgili yorumlar bırakabileceği bir bağlantıda bulunabilir</p>
<blockquote>
<li>Bağlantılar : API yanıtları, mevcut kaynaklara ve işlemlere ulaşmak için gerekli olan bağlantıları içerir. Örneğin bir kullanıcı profil yanıtında "profile update" ve "delete profile" gibi bağlantıları bulabilir</li>
<li>Dinamik ve Yönlendirme : İstemci, API'yi kullanırken hangi adımların atılabileceğini ve hangi işlemlerin yapılabileceğini , yanıt içinde yer alan bağlantılar aracılığı ile öğrenir</li>
<li>Durum Bilgisi : Her kaynak,bu kaynağın nasıl güncellenebileceği veya başka kaynaklara nasıl erişebileceği hakkında bilgi sunar. Bu api'nin sunduğu kaynakların ve işlemlerin dinamik olarak değişmesini sağlar</li>
</p>
</blockquote>
<p>Örnek JSON yanıtı:</p>
<blockquote>
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
</blockquote>
<h2>📨 Olgunluk Seviyesi Piramidi</h2>
<div align="center">
  <img src="images/Diagram.png" alt="Request 1" width="450" style="margin-bottom:10px;"><br>
</div>
<!-- Footer -->
<div align="center">
  <em>Hazırlayan: <strong>Büşra Güneş</strong> • Asp.Net Core Web API Notları • 2025</em>
</div>


