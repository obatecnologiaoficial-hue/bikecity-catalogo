<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>BikeCity Maçapá - Catálogo Online</title>
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
<style>
:root {
  --azul-escuro: #1a2336;
  --cyan: #00d4ff;
  --laranja: #ff9500;
  --amarelo: #ffd700;
  --texto: #333;
  --fundo: #f4f4f4;
  --branco: #fff;
  --sombra: 0 4px 6px rgba(0,0,0,0.1);
}
* { margin: 0; padding: 0; box-sizing: border-box; }
body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; color: var(--texto); background: var(--fundo); line-height: 1.6; }
.container { max-width: 1200px; margin: auto; padding: 0 20px; }
h2 { font-size: 2.5rem; margin-bottom: 2rem; text-align: center; color: var(--azul-escuro); }
h2 span { color: var(--cyan); }
.btn { display: inline-block; padding: 12px 30px; background: var(--laranja); color: var(--branco); border: none; border-radius: 50px; cursor: pointer; font-weight: 600; transition: all 0.3s; text-decoration: none; }
.btn:hover { background: var(--amarelo); color: var(--azul-escuro); transform: translateY(-2px); box-shadow: 0 8px 15px rgba(0,0,0,0.2); }
.section { padding: 80px 0; }
/* Header */
header { position: sticky; top: 0; z-index: 1000; background: var(--azul-escuro); box-shadow: 0 2px 10px rgba(0,0,0,0.3); transition: all 0.3s; }
.header-container { display: flex; justify-content: space-between; align-items: center; padding: 15px 20px; max-width: 1200px; margin: auto; }
.logo a { font-size: 1.8rem; font-weight: 800; color: var(--cyan); text-decoration: none; }
.logo a span { color: var(--laranja); }
nav ul { list-style: none; display: flex; gap: 25px; }
nav a { color: var(--branco); text-decoration: none; font-weight: 500; transition: color 0.3s; }
nav a:hover { color: var(--cyan); }
.search-box { display: flex; align-items: center; background: var(--branco); border-radius: 50px; overflow: hidden; }
.search-box input { border: none; padding: 10px 15px; outline: none; font-size: 1rem; width: 200px; }
.search-box button { background: var(--laranja); border: none; padding: 10px 15px; cursor: pointer; color: var(--branco); }
.menu-toggle { display: none; color: var(--branco); font-size: 1.8rem; cursor: pointer; }
@media (max-width: 768px) {
  nav ul { display: none; flex-direction: column; background: var(--azul-escuro); position: absolute; top: 70px; left: 0; width: 100%; padding: 20px; }
  nav.active ul { display: flex; }
  .search-box input { width: 150px; }
  .menu-toggle { display: block; }
}
/* Hero */
.hero { height: 100vh; min-height: 600px; display: flex; align-items: center; justify-content: center; text-align: center; position: relative; overflow: hidden; background: url('https://images.unsplash.com/photo-1576435728678-68d0fbf94e2e?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover no-repeat; background-attachment: fixed; }
.hero::before { content: ''; position: absolute; top: 0; left: 0; width: 100%; height: 100%; background: rgba(26,35,54,0.7); }
.hero-content { position: relative; z-index: 2; color: var(--branco); padding: 20px; }
.hero h1 { font-size: 4rem; font-weight: 900; margin-bottom: 1rem; text-shadow: 2px 2px 4px rgba(0,0,0,0.5); }
.hero h1 span { color: var(--cyan); }
.hero p { font-size: 1.5rem; margin-bottom: 2rem; }
.hero .btn { background: var(--cyan); color: var(--azul-escuro); font-size: 1.2rem; padding: 15px 40px; }
.hero .btn:hover { background: var(--amarelo); }
@media (max-width: 768px) {
  .hero h1 { font-size: 2.5rem; }
  .hero p { font-size: 1.2rem; }
}
/* Categories */
.categories-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap: 30px; }
.category-card { position: relative; overflow: hidden; border-radius: 15px; box-shadow: var(--sombra); transition: transform 0.3s; }
.category-card:hover { transform: translateY(-10px); }
.category-card img { width: 100%; height: 200px; object-fit: cover; }
.category-card .overlay { position: absolute; bottom: 0; left: 0; width: 100%; padding: 20px; background: linear-gradient(transparent, rgba(0,0,0,0.8)); color: var(--branco); }
.category-card h3 { font-size: 1.5rem; font-weight: 700; }
.category-card p { font-size: 1rem; }
/* Products */
.products-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 30px; }
.product-card { background: var(--branco); border-radius: 15px; overflow: hidden; box-shadow: var(--sombra); transition: all 0.3s; position: relative; }
.product-card:hover { transform: translateY(-10px); box-shadow: 0 12px 25px rgba(0,0,0,0.2); }
.product-card img { width: 100%; height: 200px; object-fit: cover; }
.product-badge { position: absolute; top: 10px; left: 10px; background: var(--laranja); color: var(--branco); padding: 5px 15px; border-radius: 50px; font-size: 0.8rem; font-weight: 600; }
.product-badge.best { background: var(--amarelo); color: var(--azul-escuro); }
.product-badge.new { background: var(--cyan); color: var(--azul-escuro); }
.product-info { padding: 20px; }
.product-info h3 { font-size: 1.3rem; margin-bottom: 10px; color: var(--azul-escuro); }
.product-info .price { font-size: 1.5rem; font-weight: 700; color: var(--laranja); margin-bottom: 15px; }
.product-info .actions { display: flex; gap: 10px; }
.product-info .btn { padding: 10px 20px; font-size: 0.9rem; }
.product-info .btn-outline { background: transparent; border: 2px solid var(--cyan); color: var(--cyan); }
.product-info .btn-outline:hover { background: var(--cyan); color: var(--branco); }
/* Benefits */
.benefits-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 30px; text-align: center; }
.benefit-card { padding: 40px 20px; background: var(--branco); border-radius: 15px; box-shadow: var(--sombra); transition: transform 0.3s; }
.benefit-card:hover { transform: scale(1.05); }
.benefit-card i { font-size: 3rem; color: var(--cyan); margin-bottom: 20px; }
.benefit-card h3 { font-size: 1.3rem; color: var(--azul-escuro); }
.benefit-card p { color: #666; }
/* Contact */
.contact-container { display: flex; flex-wrap: wrap; gap: 40px; justify-content: center; }
.contact-form { flex: 1; min-width: 300px; }
.contact-form input, .contact-form textarea { width: 100%; padding: 15px; margin-bottom: 20px; border: 1px solid #ddd; border-radius: 8px; font-size: 1rem; transition: border-color 0.3s; }
.contact-form input:focus, .contact-form textarea:focus { border-color: var(--cyan); outline: none; }
.contact-form textarea { height: 150px; }
.contact-form .btn { width: 100%; }
.contact-info { flex: 1; min-width: 300px; display: flex; flex-direction: column; justify-content: center; gap: 20px; }
.contact-info p { font-size: 1.1rem; }
.contact-info i { color: var(--cyan); margin-right: 10px; }
.contact-info .whatsapp { background: #25D366; color: var(--branco); padding: 15px 30px; border-radius: 50px; text-align: center; font-weight: 600; transition: background 0.3s; }
.contact-info .whatsapp:hover { background: #128C7E; }
/* WhatsApp Float */
.whatsapp-float { position: fixed; bottom: 20px; right: 20px; z-index: 999; background: #25D366; color: var(--branco); width: 60px; height: 60px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 2rem; box-shadow: 0 4px 10px rgba(0,0,0,0.3); transition: all 0.3s; }
.whatsapp-float:hover { transform: scale(1.1); background: #128C7E; }
/* Footer */
footer { background: var(--azul-escuro); color: var(--branco); padding: 40px 0; text-align: center; }
footer .social a { color: var(--branco); font-size: 1.5rem; margin: 0 15px; transition: color 0.3s; }
footer .social a:hover { color: var(--cyan); }
footer p { margin-top: 20px; font-size: 0.9rem; opacity: 0.8; }
/* Animations */
.fade-in { opacity: 0; transform: translateY(30px); transition: opacity 0.6s ease, transform 0.6s ease; }
.fade-in.visible { opacity: 1; transform: translateY(0); }
</style>
</head>
<body>
<header>
  <div class="header-container">
    <div class="logo"><a href="#">Bike<span>City</span></a></div>
    <nav id="nav">
      <ul>
        <li><a href="#home">Home</a></li>
        <li><a href="#categorias">Categorias</a></li>
        <li><a href="#produtos">Produtos</a></li>
        <li><a href="#beneficios">Benefícios</a></li>
        <li><a href="#contato">Contato</a></li>
      </ul>
    </nav>
    <div class="search-box">
      <input type="text" placeholder="Buscar...">
      <button><i class="fas fa-search"></i></button>
    </div>
    <div class="menu-toggle" onclick="document.getElementById('nav').classList.toggle('active')"><i class="fas fa-bars"></i></div>
  </div>
</header>
<section id="home" class="hero">
  <div class="hero-content fade-in">
    <h1>Pedale com <span>Estilo</span></h1>
    <p>A melhor bike para sua aventura urbana ou off-road</p>
    <a href="#produtos" class="btn">Ver Produtos</a>
  </div>
</section>
<section id="categorias" class="section">
  <div class="container">
    <h2>Nossas <span>Categorias</span></h2>
    <div class="categories-grid">
      <div class="category-card fade-in">
        <img src="https://images.unsplash.com/photo-1576435728678-68d0fbf94e2e?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Mountain Bike">
        <div class="overlay">
          <h3>Mountain Bike</h3>
          <p>Aventure-se nas trilhas</p>
        </div>
      </div>
      <div class="category-card fade-in">
        <img src="https://images.unsplash.com/photo-1485965120184-e220f721d03e?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Speed">
        <div class="overlay">
          <h3>Speed / Road</h3>
          <p>Velocidade no asfalto</p>
        </div>
      </div>
      <div class="category-card fade-in">
        <img src="https://images.unsplash.com/photo-1517649763962-0c623066013b?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Urbana">
        <div class="overlay">
          <h3>Urbana</h3>
          <p>Mobilidade na cidade</p>
        </div>
      </div>
      <div class="category-card fade-in">
        <img src="https://images.unsplash.com/photo-1571330735066-0bc4ac9d1cee?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Acessórios">
        <div class="overlay">
          <h3>Acessórios</h3>
          <p>Equipamentos essenciais</p>
        </div>
      </div>
    </div>
  </div>
</section>
<section id="produtos" class="section">
  <div class="container">
    <h2>Nossos <span>Produtos</span></h2>
    <div class="products-grid">
      <!-- Mountain Bike 1 -->
      <div class="product-card fade-in">
        <div class="product-badge">Promoção</div>
        <img src="https://images.unsplash.com/photo-1576435728678-68d0fbf94e2e?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Mountain Bike XTR">
        <div class="product-info">
          <h3>Mountain Bike XTR</h3>
          <p class="price">R$ 4.999,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Mountain Bike 2 -->
      <div class="product-card fade-in">
        <div class="product-badge best">Mais Vendido</div>
        <img src="https://images.unsplash.com/photo-1576435728678-68d0fbf94e2e?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Mountain Bike Enduro">
        <div class="product-info">
          <h3>Mountain Bike Enduro</h3>
          <p class="price">R$ 5.499,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Mountain Bike 3 -->
      <div class="product-card fade-in">
        <div class="product-badge new">Novo</div>
        <img src="https://images.unsplash.com/photo-1576435728678-68d0fbf94e2e?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Mountain Bike Trail">
        <div class="product-info">
          <h3>Mountain Bike Trail</h3>
          <p class="price">R$ 4.299,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Mountain Bike 4 -->
      <div class="product-card fade-in">
        <img src="https://images.unsplash.com/photo-1576435728678-68d0fbf94e2e?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Mountain Bike Downhill">
        <div class="product-info">
          <h3>Mountain Bike Downhill</h3>
          <p class="price">R$ 6.999,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Speed 1 -->
      <div class="product-card fade-in">
        <div class="product-badge">Promoção</div>
        <img src="https://images.unsplash.com/photo-1485965120184-e220f721d03e?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Speed Race">
        <div class="product-info">
          <h3>Speed Race</h3>
          <p class="price">R$ 7.999,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Speed 2 -->
      <div class="product-card fade-in">
        <div class="product-badge best">Mais Vendido</div>
        <img src="https://images.unsplash.com/photo-1485965120184-e220f721d03e?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Speed Pro">
        <div class="product-info">
          <h3>Speed Pro</h3>
          <p class="price">R$ 9.499,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Speed 3 -->
      <div class="product-card fade-in">
        <div class="product-badge new">Novo</div>
        <img src="https://images.unsplash.com/photo-1485965120184-e220f721d03e?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Speed Elite">
        <div class="product-info">
          <h3>Speed Elite</h3>
          <p class="price">R$ 8.299,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Speed 4 -->
      <div class="product-card fade-in">
        <img src="https://images.unsplash.com/photo-1485965120184-e220f721d03e?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Speed Aero">
        <div class="product-info">
          <h3>Speed Aero</h3>
          <p class="price">R$ 10.999,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Urbana 1 -->
      <div class="product-card fade-in">
        <div class="product-badge best">Mais Vendido</div>
        <img src="https://images.unsplash.com/photo-1517649763962-0c623066013b?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Bike Urbana Clássica">
        <div class="product-info">
          <h3>Bike Urbana Clássica</h3>
          <p class="price">R$ 2.499,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Urbana 2 -->
      <div class="product-card fade-in">
        <div class="product-badge new">Novo</div>
        <img src="https://images.unsplash.com/photo-1517649763962-0c623066013b?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Bike Urbana Elétrica">
        <div class="product-info">
          <h3>Bike Urbana Elétrica</h3>
          <p class="price">R$ 4.999,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Acessórios 1 -->
      <div class="product-card fade-in">
        <div class="product-badge">Promoção</div>
        <img src="https://images.unsplash.com/photo-1571330735066-0bc4ac9d1cee?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Capacete Pro">
        <div class="product-info">
          <h3>Capacete Pro</h3>
          <p class="price">R$ 299,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
      <!-- Acessórios 2 -->
      <div class="product-card fade-in">
        <img src="https://images.unsplash.com/photo-1571330735066-0bc4ac9d1cee?ixlib=rb-4.0.3&auto=format&fit=crop&w=400&q=80" alt="Kit Luzes LED">
        <div class="product-info">
          <h3>Kit Luzes LED</h3>
          <p class="price">R$ 89,00</p>
          <div class="actions">
            <a href="#" class="btn">Comprar</a>
            <a href="#" class="btn btn-outline">Mais Info</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
<section id="beneficios" class="section">
  <div class="container">
    <h2>Por que <span>escolher a BikeCity?</span></h2>
    <div class="benefits-grid">
      <div class="benefit-card fade-in">
        <i class="fas fa-truck"></i>
        <h3>Frete Grátis</h3>
        <p>Para compras acima de R$ 500</p>
      </div>
      <div class="benefit-card fade-in">
        <i class="fas fa-shield-alt"></i>
        <h3>Garantia Estendida</h3>
        <p>2 anos em todos os produtos</p>
      </div>
      <div class="benefit-card fade-in">
        <i class="fas fa-headset"></i>
        <h3>Suporte 24h</h3>
        <p>Equipe especializada</p>
      </div>
      <div class="benefit-card fade-in">
        <i class="fas fa-undo-alt"></i>
        <h3>Devolução Fácil</h3>
        <p>30 dias para trocar</p>
      </div>
    </div>
  </div>
</section>
<section id="contato" class="section">
  <div class="container">
    <h2>Entre em <span>Contato</span></h2>
    <div class="contact-container">
      <div class="contact-form fade-in">
        <form id="contactForm">
          <input type="text" name="nome" placeholder="Seu Nome" required>
          <input type="email" name="email" placeholder="Seu Email" required>
          <textarea name="mensagem" placeholder="Sua Mensagem" required></textarea>
          <button type="submit" class="btn">Enviar Mensagem</button>
        </form>
      </div>
      <div class="contact-info fade-in">
        <p><i class="fas fa-map-marker-alt"></i> Rua das Bicicletas, 123, Centro, Maçapá</p>
        <p><i class="fas fa-phone"></i> (96) 9132-2552</p>
        <a href="https://wa.me/559691322552" target="_blank" class="whatsapp"><i class="fab fa-whatsapp"></i> Fale Conosco pelo WhatsApp</a>
      </div>
    </div>
  </div>
</section>
<a href="https://wa.me/559691322552" target="_blank" class="whatsapp-float" title="Fale conosco"><i class="fab fa-whatsapp"></i></a>
<footer>
  <div class="social">
    <a href="#"><i class="fab fa-facebook"></i></a>
    <a href="#"><i class="fab fa-instagram"></i></a>
    <a href="#"><i class="fab fa-youtube"></i></a>
  </div>
  <p>&copy; 2025 BikeCity Maçapá. Todos os direitos reservados.</p>
</footer>
<script>
// Intersection Observer for animations
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.1 });

document.querySelectorAll('.fade-in').forEach(el => observer.observe(el));

// Form submission
document.getElementById('contactForm').addEventListener('submit', function(e) {
  e.preventDefault();
  alert('Mensagem enviada com sucesso! Em breve entraremos em contato.');
});
</script>
</body>
</html>
