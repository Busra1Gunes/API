<div align="center"> <h1 style="color:#2c3e50;">🧩 Controller Nedir ve Nasıl Oluşturulur?</h1> 
</div> 
<h2>📦 Controller Nedir?</h2> <blockquote>
 <strong>
 Controller
 </strong>,
  ASP.NET Core Web API uygulamalarında istemciden gelen HTTP isteklerini karşılayan sınıflardır. Her 
<code>controller</code> 
içinde, genellikle HTTP GET, POST, PUT ve DELETE gibi işlemleri gerçekleştiren metotlar yer alır. 
</blockquote>
 <ul> 
 <li><strong>Route (Yönlendirme):</strong> Controller, belirli bir URL yoluna yanıt verir.</li>
  <li>
  <strong>İşlem Yöntemleri:</strong>
   HTTP metotlarına göre davranış sergiler (örn: <code>[HttpGet]</code>, <code>[HttpPost]</code>).</li> 
   <li>
   <strong>RESTful yapı:
   </strong> 
   API'nin CRUD işlemlerini yönetmesini sağlar.</li>
   </ul>
<h2>🛠️ 1. Controller Klasörü Oluşturun</h2>
 <blockquote>
  Projenizin kök dizinine <code>Controllers</code> adında bir klasör ekleyin. Controller sınıfları genellikle burada yer alır. 
  </blockquote>
<h2>✏️ 2. Örnek Bir Controller Oluşturun</h2>
 <pre>
 <code>// Controllers/HelloController.cs using Microsoft.AspNetCore.Mvc; namespace WebApi.Controllers { [ApiController] [Route("[controller]")] public class HelloController : ControllerBase { [HttpGet] public IActionResult Get() { return Ok("Merhaba dünya! Bu ilk API cevabın."); } } } 
 </code>
 </pre>
<h2>⚙️ 3. Program.cs Dosyasına Controller Desteği Ekleyin</h2> 
<pre>
<code>var builder = WebApplication.CreateBuilder(args); // Controller desteğini ekle builder.Services.AddControllers(); var app = builder.Build(); // Controller'ları kullanmak için yönlendirme middleware'ini ekle app.UseHttpsRedirection(); app.UseAuthorization(); app.MapControllers(); app.Run(); </code>
</pre>
<h2>🚀 4. Tarayıcıda Test Et</h2> 
<blockquote> Projeyi çalıştırdıktan sonra şu URL'yi açarak test edebilirsin: <br>
<br>
 <code>https://localhost:xxxx/hello</code> 
 </blockquote>
<h4>🧠 Ek Bilgi</h4> <ul> <li><code>[ApiController]
</code>: Sınıfın bir API controller olduğunu belirtir.</li>
 <li>
 <code>[Route("[controller]")]</code>: Controller adını URL yolu olarak ayarlar. Örn: <code>HelloController</code> → <code>/hello</code>.</li> <li><code>Ok("mesaj")</code>: 200 OK HTTP cevabıyla birlikte içerik döner.</li> </ul>
<div align="center"> <em>Hazırlayan: <strong>Büşra Güneş</strong> • Asp.Net Core Web API Notları • 2025</em> </div>