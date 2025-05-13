<div align="center">
  <h1 style="color:#2c3e50;">📘 Swagger Nedir ve Web API'ye Nasıl Eklenir?</h1>
</div>

<h2>🌐 Swagger Nedir?</h2>
<blockquote>
  <strong>Swagger (OpenAPI)</strong>, RESTful API'leri tanımlamak, dokümante etmek ve test etmek için kullanılan bir araçtır. Geliştiricilerin API'lerini görsel arayüzle keşfetmesine ve test etmesine imkân tanır.
</blockquote>

<h3>🛠️ Swagger'ın Temel Özellikleri</h3>
<ul>
  <li><strong>Dokümantasyon:</strong> API uç noktalarını açık şekilde gösterir.</li>
  <li><strong>Test Arayüzü:</strong> API'yi arayüz üzerinden test etmenizi sağlar.</li>
  <li><strong>Otomatik Üretim:</strong> Koddan otomatik olarak API dökümantasyonu oluşturur.</li>
</ul>

---

<h2>🚀 Web API Projesine Swagger Nasıl Eklenir?</h2>

<h3>📁 1. Boş Web API Projesi Oluşturma</h3>
<pre>
dotnet new webapi -n SwaggerOrnekProje
</pre>
<p><em>Not: Eğer `--no-https` ve `--no-openapi` gibi seçeneklerle oluşturduysanız, Swagger elle eklenmelidir.</em></p>

---

<h3>📦 2. Swagger Paketini Yükleme</h3>
<pre>
dotnet add package Swashbuckle.AspNetCore
</pre>

---

<h3>🧩 3. Program.cs Dosyasına Swagger Servislerini Ekleyin</h3>

<blockquote>
  <strong>Program.cs</strong> dosyasında Swagger'ın çalışması için hem <code>service</code> hem de <code>middleware</code> olarak iki bölümde ekleme yapılmalıdır.
</blockquote>

<h4>📌 Service (Hizmet) Tanımlamaları</h4>

<pre>
<b>// WebApplication Builder oluşturuluyor</b>
var builder = WebApplication.CreateBuilder(args);

<b>// Swagger servisleri ekleniyor</b>
builder.Services.AddEndpointsApiExplorer(); <i>// API uç noktalarını keşfeder</i>
builder.Services.AddSwaggerGen(); <i>// Swagger dökümantasyonu üretir</i>
</pre>

---

<h4>⚙️ Middleware (Ara katman) Tanımlamaları</h4>

<pre>
<b>// Uygulama inşa ediliyor</b>
var app = builder.Build();

<b>// Geliştirme ortamında Swagger arayüzünü aktif et</b>
if (app.Environment.IsDevelopment())
{
    app.UseSwagger();        <i>// Swagger JSON dökümantasyonunu oluşturur</i>
    app.UseSwaggerUI();      <i>// Swagger UI görsel arayüzünü aktif eder</i>
}

<b>// Diğer temel middleware'ler</b>
app.UseHttpsRedirection();
app.UseAuthorization();
app.MapControllers();

<b>// Uygulamayı çalıştır</b>
app.Run();
</pre>

---

<h4>🧠 Açıklamalar</h4>
<ul>
  <li><code>AddEndpointsApiExplorer()</code>: Minimal API'ler için gerekli olan uç nokta keşfini sağlar.</li>
  <li><code>AddSwaggerGen()</code>: Swagger/OpenAPI dökümantasyon dosyasını oluşturur.</li>
  <li><code>UseSwagger()</code>: JSON formatındaki dökümantasyonu yayınlar.</li>
  <li><code>UseSwaggerUI()</code>: Swagger'ın kullanıcı arayüzünü sunar.</li>
</ul>
<h3>🧭 4. <code>launchSettings.json</code> Dosyasında Yapılması Gereken Ayarlar</h3>

<blockquote>
  <strong>launchSettings.json</strong>, uygulama çalıştırıldığında hangi ayarlarla başlayacağını belirler. Swagger'ın otomatik açılması için <code>launchUrl</code> ayarı önemlidir.
</blockquote>

<h4>🛠️ Yapılması Gerekenler</h4>

📁 <code>Properties/launchSettings.json</code> dosyasını açın ve aşağıdaki gibi düzenleyin:

```json
{
  "profiles": {
    "YourApiProjectName": {
      "commandName": "Project",
      "dotnetRunMessages": true,
      "launchBrowser": true,
      "launchUrl": "swagger", // 👈 Swagger arayüzünü otomatik aç
      "applicationUrl": "https://localhost:5001;http://localhost:5000",
      "environmentVariables": {
        "ASPNETCORE_ENVIRONMENT": "Development"
      }
    }
  }
}


<!-- Footer -->
<div align="center">
  <em>Hazırlayan: <strong>Büşra Güneş</strong> • Asp.Net Core Web API Notları • 2025</em>
</div>