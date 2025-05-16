<div align="center"> <h1 style="color:#2c3e50;">🧩 Serilog ile Veritabanına Loglama</h1> </div> <h2>🔧 Neden Serilog?</h2> <blockquote> Serilog, .NET uygulamaları için yapılandırması kolay, esnek ve güçlü bir loglama kütüphanesidir. <strong>ILogger</strong> arayüzü ile uyumludur ve <strong>SQL Server</strong> dahil birçok hedefe log yazabilir. </blockquote>
<h3>📦 Gerekli NuGet Paketleri</h3>
<div align="center">
  <img src="Images/SerilogPackage.png" alt="Example" width="450" style="margin-bottom:10px;"><br>
  </div>
  <h3>🛠️ SQL Server'da Log Tablosu Oluştur</h3>
  <div align="center">
  <img src="Images/LogTable.png" alt="Example" width="450" style="margin-bottom:10px;"><br>
  </div>
  <h3>⚙️ Program.cs veya appsettings.json Konfigürasyonu</h3>
    <h4>Program.cs (Minimal API için örnek)::</h4>
    <blockquote>
    <p>using Serilog;</p>
<p>using Serilog.Sinks.MSSqlServer;</p>
<p>using System.Collections.ObjectModel;</p>

<p>var columnOptions = new ColumnOptions</p>
<p>{</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;AdditionalColumns = new Collection&lt;SqlColumn&gt;</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;{</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;new SqlColumn</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ColumnName = "Username",</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DataType = System.Data.SqlDbType.NVarChar,</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;DataLength = 100</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;}</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;}</p>
<p>};</p>

<p>Log.Logger = new LoggerConfiguration()</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;.WriteTo.Console() <span style="color:gray">// Konsola loglama</span></p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;.WriteTo.MSSqlServer( <span style="color:gray">// Veritabanına loglama</span></p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;connectionString: "Server=.;Database=MyLogsDb;Trusted_Connection=True;",</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;sinkOptions: new MSSqlServerSinkOptions</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;{</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;TableName = "Logs",</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AutoCreateSqlTable = false</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;},</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;columnOptions: columnOptions</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;)</p>
<p>&nbsp;&nbsp;&nbsp;&nbsp;.CreateLogger();</p>
</blockquote>
    

<h3>🧪 Örnek Kullanım</h3>

<div align="center">
  <img src="Images/Example2.png" alt="Example" width="450" style="margin-bottom:10px;"><br>
  </div>
  <h2>📌 Ek Bilgiler</h2>
     <blockquote> 
<li>AutoCreateSqlTable = true kullanarak tabloyu otomatik oluşturabilirsin (geliştirme için uygundur).</li>
<li>Properties kolonu sayesinde loglara ekstra bilgiler (UserId, IP, vb.) ekleyebilirsin.</li>
<li>Performans için async logging ve batch ayarları da yapılabilir.</li>
   </blockquote>
   <p></p>
<div align="center"> <em>Hazırlayan: <strong>Büşra Güneş</strong> • Asp.Net Core Loglama Notları • 2025</em> </div>