<div align="center"> <h1 style="color:#34495e;">🛠️ <code>launchSettings.json</code> ve Ortamlar</h1> </div> <h2>📁 launchSettings.json Nedir?</h2> <blockquote> <strong>launchSettings.json</strong> dosyası, .NET Core uygulaması çalıştırıldığında hangi ayarlarla başlayacağını belirleyen konfigürasyon dosyasıdır. </blockquote>
<h2>🌍 Ortam Belirtme: <code>ASPNETCORE_ENVIRONMENT</code></h2>
Bu değişken ile uygulamanın hangi ortamda çalışacağı belirlenir. Örneğin:

<pre><code> "environmentVariables": { "ASPNETCORE_ENVIRONMENT": "Development" } </code></pre>
<h2>🏷️ Ortam Türleri ve Açıklamaları</h2> <table border="1" cellpadding="6"> <tr> <th>Ortam</th> <th>Açıklama</th> <th>Kullanım Amacı</th> </tr> <tr> <td><strong>Development</strong></td> <td>Geliştirme ortamı</td> <td>Hata detaylarını görmek, Swagger gibi araçları kullanmak</td> </tr> <tr> <td><strong>Staging</strong></td> <td>Test ortamı</td> <td>Gerçek yayına çıkmadan önce son testlerin yapıldığı yer</td> </tr> <tr> <td><strong>Production</strong></td> <td>Canlı ortam</td> <td>Kullanıcılara hizmet veren nihai ortam</td> </tr> </table>
<h2>🧾 Örnek <code>launchSettings.json</code></h2> <pre><code> { 
"profiles": 
{ 
    "WebApi-Development": { 
    "commandName": "Project", 
 "dotnetRunMessages": true,
  "launchBrowser": true, 
  "applicationUrl": "https://localhost:5001",
   "environmentVariables": {
     "ASPNETCORE_ENVIRONMENT": "Development" } }, 
     "WebApi-Production": {
         "commandName": "Project",
          "dotnetRunMessages": true, 
          "launchBrowser": true, 
          "applicationUrl": "https://localhost:7001", "environmentVariables": 
          { 
            "ASPNETCORE_ENVIRONMENT": "Production"
          } 
      }
    }
} </code></pre>
<p>🔄 Visual Studio’da farklı profiller arasında geçiş yaparak uygulamayı farklı ortamlarda test edebilirsin.</p>
<div align="center"> <em>Hazırlayan: <strong>Büşra Güneş</strong> • Asp.Net Core Web API Notları • 2025</em> </div
