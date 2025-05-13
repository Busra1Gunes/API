<div align="center">
  <h1 style="color:#2c3e50;">🧩 Program.cs Dosyası</h1>
</div>
<h2>🌐 Program.cs Nedir?</h2>
<blockquote>
  <strong>Program.cs</strong>, .NET Core API uygulamalarının başlangıç noktasıdır. Uygulamanın başlatılması, yapılandırılması ve HTTP isteklerinin nasıl yönlendirileceği bu dosyada belirlenir.
</blockquote>

<h3>🛠️ Program.cs Dosyasının Temel Özellikleri</h3>
<ul>
  <li><strong>Uygulama Başlatma:</strong> Uygulamanın tüm servislere ve yapılandırmalara göre başlatılmasını sağlar.</li>
  <li><strong>Servis Ekleme:</strong> Veritabanı bağlantıları, kimlik doğrulama ve diğer bağımlılıklar burada eklenir.</li>
  <li><strong>HTTP Middleware:</strong> HTTP istekleri için middleware'ler burada yapılandırılır.</li>
</ul>

<!-- Program.cs Metodları -->
<h3>✏️ Program.cs Metodları</h3>
<table>
  <thead>
    <tr>
      <th>Metod</th>
      <th>Açıklama</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><code>CreateHostBuilder</code></td><td>Uygulamanın host yapılandırmasını başlatır ve servisleri hazırlar.</td></tr>
    <tr><td><code>Configure</code></td><td>HTTP isteklerini yönlendiren middleware'leri yapılandırır.</td></tr>
    <tr><td><code>ConfigureServices</code></td><td>Uygulamanın ihtiyaç duyduğu servisleri (örneğin, veritabanı, kimlik doğrulama) ekler.</td></tr>
    <tr><td><code>ConfigurePipeline</code></td><td>Uygulamanın HTTP pipeline'ını (middleware'leri) yapılandırır.</td></tr>
  </tbody>
</table>

<hr>

<!-- CreateHostBuilder Metodu -->
<h2>📨 CreateHostBuilder Metodu</h2>
<p><strong>CreateHostBuilder</strong>, uygulamanın başlatılmasında kullanılan ilk metodtur. Bu metod, uygulamanın yapılandırmasını ve servislerini hazırlar.</p>
<div align="center">
  <img src="images/HostBuilder.png" alt="HostBuilder" width="450"><br>
</div>

<hr>

<!-- Configure Metodu -->
<h2>📬 Configure Metodu</h2>
<p><strong>Configure</strong>, HTTP isteklerinin nasıl yönlendirileceğini belirler. Middleware'lerin sıralandığı bu metodda, hangi yolların hangi işlemlerle yanıtlanacağı ayarlanır.</p>
<div align="center">
  <img src="images/Configure.png" alt="Configure" width="450"><br>
</div>

<hr>

<!-- ConfigureServices Metodu -->
<h2>🛠️ ConfigureServices Metodu</h2>
<p><strong>ConfigureServices</strong>, uygulamanın servislerini tanımlar. Örneğin, veritabanı servisleri, kimlik doğrulama ve bağımlılıklar burada eklenir.</p>
<div align="center">
  <img src="images/ConfigureServices.png" alt="ConfigureServices" width="450"><br>
</div>

<hr>

<!-- Footer -->
<div align="center">
  <em>Hazırlayan: <strong>Büşra Güneş</strong> • Asp.Net Core Web API Notları • 2025</em>
</div>
