# Dhagozzz-
My personal website 
from pathlib import Path
import zipfile

site = Path("/mnt/data/dhagozzz")
site.mkdir(exist_ok=True)

html = """<!DOCTYPE html>
<html lang="so">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Dhagozzz</title>
<style>
*{box-sizing:border-box} body{margin:0;font-family:Arial,sans-serif;background:#0b1020;color:white}
header{padding:22px 7%;display:flex;justify-content:space-between;align-items:center;background:#111936}
.logo{font-size:28px;font-weight:800;color:#5eead4}.btn{background:#5eead4;color:#07111c;padding:12px 18px;border-radius:10px;text-decoration:none;font-weight:bold}
.hero{padding:90px 7%;text-align:center}.hero h1{font-size:54px;margin:0 0 15px}.hero p{font-size:20px;color:#cbd5e1;max-width:650px;margin:0 auto 30px}
.cards{display:flex;gap:20px;flex-wrap:wrap;justify-content:center;padding:20px 7% 80px}.card{background:#151d3d;padding:28px;border-radius:18px;width:280px}.card h2{color:#5eead4}
footer{text-align:center;padding:25px;background:#111936;color:#94a3b8}
</style>
</head>
<body>
<header><div class="logo">DHAGOZZZ</div><a class="btn" href="#contact">Nala Xiriir</a></header>
<section class="hero">
<h1>Ku soo dhawoow Dhagozzz</h1>
<p>Website-kaaga gaarka ah oo casri ah, fudud oo mobile-ka si fiican uga shaqeeya.</p>
<a class="btn" href="#about">Wax badan ogow</a>
</section>
<section class="cards" id="about">
<div class="card"><h2>Dhagozzz</h2><p>Magacaaga iyo astaantaada ku muuji meel qurux badan.</p></div>
<div class="card"><h2>Mobile</h2><p>Waxaa loogu talagalay in uu si fiican uga shaqeeyo telefoonada.</p></div>
<div class="card" id="contact"><h2>Xiriir</h2><p>Ku dar lambarkaaga ama WhatsApp-kaaga marka aad diyaar tahay.</p></div>
</section>
<footer>© 2026 Dhagozzz — All rights reserved.</footer>
</body>
</html>"""

(site/"index.html").write_text(html, encoding="utf-8")
zip_path = Path("/mnt/data/Dhagozzz-Website.zip")
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    z.write(site/"index.html", "index.html")

print(f"[Download the Dhagozzz website](sandbox:{zip_path})")
