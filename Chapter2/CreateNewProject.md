<div align="center">
  <h1 style="color:#2c3e50;">🚀 ASP.NET Core Web API Projesi Oluşturma</h1>
</div>

<hr>

<div align="center">
  <h2 style="color:#2c3e50;">🛠 Visual Studio ile Web API Projesi Oluşturma</h2>
</div>

<!-- Adım 1 -->
<h3>📌 1. Visual Studio'yu Başlat</h3>
<ul>
  <li><strong>Visual Studio</strong> 2019, 2022 veya daha güncel bir sürümünü başlat.</li>
  <li><strong>“Create a new project”</strong> seçeneğine tıkla.</li>
</ul>

<div align="center">
  <img src="images/vs_start.png" alt="Visual Studio Başlangıç" width="500">
</div>

<hr>

<!-- Adım 2 -->
<h3>📌 2. Yeni Proje Oluştur</h3>
<ul>
  <li>Açılan pencerede arama kutusuna <strong>ASP.NET Core Web API</strong> yaz.</li>
  <li>Listeden <em>“ASP.NET Core Web API”</em> şablonunu seç.</li>
  <li><strong>Next</strong> butonuna tıkla.</li>
</ul>

<div align="center">
  <img src="images/create_project.png" alt="Yeni Proje Oluştur" width="500">
</div>

<hr>

<!-- Adım 3 -->
<h3>📌 3. Proje Ayarlarını Belirle</h3>
<ul>
  <li><strong>Project name:</strong> Örn: <code>MyFirstApi</code></li>
  <li><strong>Location:</strong> Bilgisayarındaki uygun bir klasörü seç.</li>
  <li><strong>Solution name:</strong> Otomatik gelir veya isteğe göre değiştir.</li>
  <li><strong>Next</strong> butonuna tıkla.</li>
</ul>

<div align="center">
  <img src="images/project_config.png" alt="Proje Ayarları" width="500">
</div>

<hr>

<!-- Adım 4 -->
<h3>📌 4. Framework Seç ve Diğer Ayarlar</h3>
<ul>
  <li><strong>Framework:</strong> .NET 6, 7 veya 8 (güncel olanı seç)</li>
  <li><strong>Authentication Type:</strong> “None” olarak bırak.</li>
  <li><strong>Enable OpenAPI Support (Swagger):</strong> Kutucuğu işaretli kalsın.</li>
  <li><strong>Create</strong> butonuna tıkla.</li>
</ul>

<div align="center">
  <img src="images/framework_select.png" alt="Framework Seçimi" width="500">
</div>

<hr>

<!-- Proje Yapısı -->
<h3>📁 Oluşturulan Proje Yapısı</h3>
<table>
  <thead>
    <tr>
      <th>Klasör/Dosya</th>
      <th>Açıklama</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><code>Program.cs</code></td><td>Uygulamanın başlangıç noktası</td></tr>
    <tr><td><code>Controllers/</code></td><td>API controller sınıflarının yer aldığı klasör</td></tr>
    <tr><td><code>appsettings.json</code></td><td>Konfigürasyon dosyası</td></tr>
    <tr><td><code>WeatherForecastController.cs</code></td><td>Örnek controller</td></tr>
  </tbody>
</table>

<hr>

<!-- İlk Controller -->
<h3>📌 İlk Controller’ını Yaz</h3>

<blockquote>
Aşağıdaki gibi basit bir "Hello" controller'ı ekleyebilirsin:
</blockquote>

```csharp
[ApiController]
[Route("api/[controller]")]
public class HelloController : ControllerBase
{
    [HttpGet]
    public IActionResult GetHello()
    {
        return Ok("Merhaba ASP.NET Core API!");
    }
}
<!-- Footer -->
<div align="center">
  <em>Hazırlayan: <strong>Büşra Güneş</strong> • Asp.Net Core Web API Notları • 2025</em>
</div>