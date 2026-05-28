<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>BikeCity Maçapá - Catálogo</title>
  <style>
    * { margin: 0; padding: 0; box-sizing: border-box; font-family: Arial, sans-serif; }
    body { background: #f5f5f5; color: #333; }
    a { text-decoration: none; color: inherit; }
    .container { max-width: 1200px; margin: 0 auto; padding: 0 15px; }
    h2 { font-size: 2rem; margin-bottom: 20px; color: #1E90FF; }
    /* Header */
    header { background: #1E90FF; color: #fff; padding: 15px 0; position: sticky; top: 0; z-index: 100; }
    header .container { display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 15px; }
    .logo { font-size: 1.8rem; font-weight: bold; color: #fff; }
    .logo span { color: #FF8C00; }
    nav ul { list-style: none; display: flex; gap: 20px; }
    nav a { color: #fff; font-weight: 500; transition: color 0.3s; }
    nav a:hover { color: #32CD32; }
    .search-box { display: flex; align-items: center; }
    .search-box input { padding: 8px 12px; border: none; border-radius: 4px 0 0 4px; outline: none; }
    .search-box button { padding: 8px 12px; background: #32CD32; color: #fff; border: none; border-radius: 0 4px 4px 0; cursor: pointer; transition: background 0.3s; }
    .search-box button:hover { background: #28a428; }
    /* Banner */
    .banner { background: linear-gradient(135deg, #1E90FF, #32CD32); color: #fff; text-align: center; padding: 60px 20px; }
    .banner h1 { font-size: 2.5rem; margin-bottom: 10px; }
    .banner p { font-size: 1.2rem; margin-bottom: 20px; }
    .banner .cta { background: #FF8C00; color: #fff; padding: 12px 30px; border-radius: 25px; font-size: 1rem; display: inline-block; transition: transform 0.3s, box-shadow 0.3s; }
    .banner .cta:hover { transform: scale(1.05); box-shadow: 0 5px 15px rgba(0,0,0,0.3); }
    /* Filters */
    .filters { padding: 30px 0; }
    .filters .container { display: flex; flex-wrap: wrap; gap: 15px; justify-content: center; }
    .filters select, .filters input { padding: 10px; border: 2px solid #1E90FF; border-radius: 5px; outline: none; font-size: 1rem; }
    .filters button { padding: 10px 20px; background: #1E90FF; color: #fff; border: none; border-radius: 5px; cursor: pointer; transition: background 0.3s; }
    .filters button:hover { background: #1a7acc; }
    /* Products */
    .products { padding: 40px 0; }
    .product-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 20px; }
    .product-card { background: #fff; border-radius: 10px; overflow: hidden; box-shadow: 0 4px 6px rgba(0,0,0,0.1); transition: transform 0.3s, box-shadow 0.3s; }
    .product-card:hover { transform: translateY(-5px); box-shadow: 0 8px 12px rgba(0,0,0,0.15); }
    .product-card img { width: 100%; height: 200px; object-fit: cover; }
    .product-info { padding: 15px; }
    .product-info h3 { font-size: 1.2rem; margin-bottom: 10px; color: #1E90FF; }
    .product-info .price { font-size: 1.4rem; font-weight: bold; color: #32CD32; }
    .product-info .old-price { text-decoration: line-through; color: #999; font-size: 0.9rem; }
    .product-info .installment { color: #555; font-size: 0.9rem; }
    /* Benefits */
    .benefits { background: #fff; padding: 40px 0; }
    .benefits-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 30px; text-align: center; }
    .benefit-item i { font-size: 3rem; color: #1E90FF; margin-bottom: 15px; }
    .benefit-item h3 { margin-bottom: 10px; color: #32CD32; }
    .benefit-item p { color: #666; }
    /* Contact */
    .contact { padding: 40px 0; background: #f0f8ff; }
    .contact-form { max-width: 600px; margin: 0 auto; background: #fff; padding: 30px; border-radius: 10px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
    .contact-form .form-group { margin-bottom: 20px; }
    .contact-form label { display: block; margin-bottom: 5px; font-weight: 500; color: #1E90FF; }
    .contact-form input, .contact-form select, .contact-form textarea { width: 100%; padding: 10px; border: 2px solid #ddd; border-radius: 5px; outline: none; transition: border-color 0.3s; font-size: 1rem; }
    .contact-form input:focus, .contact-form select:focus, .contact-form textarea:focus { border-color: #1E90FF; }
    .contact-form .error { color: #e74c3c; font-size: 0.85rem; margin-top: 5px; display: none; }
    .contact-form button { background: #25D366; color: #fff; border: none; padding: 12px 20px; border-radius: 5px; font-size: 1rem; cursor: pointer; transition: background 0.3s; width: 100%; }
    .contact-form button:hover { background: #1da851; }
    /* Floating WhatsApp */
    .whatsapp-float { position: fixed; bottom: 20px; right: 20px; width: 60px; height: 60px; background: #25D366; border-radius: 50%; display: flex; align-items: center; justify-content: center; color: #fff; font-size: 2rem; box-shadow: 0 4px 8px rgba(0,0,0,0.2); cursor: pointer; transition: transform 0.3s, box-shadow 0.3s; z-index: 999; }
    .whatsapp-float:hover { transform: scale(1.1); box-shadow: 0 6px 12px rgba(0,0,0,0.3); }
    /* Footer */
    footer { background: #1E90FF; color: #fff; padding: 30px 0; text-align: center; }
    footer .container { display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center; gap: 20px; }
    footer .social a { color: #fff; margin: 0 10px; font-size: 1.5rem; transition: color 0.3s; }
    footer .social a:hover { color: #32CD32; }
    footer .info p { margin-bottom: 5px; }
    /* Responsive */
    @media (max-width: 768px) {
      header .container { flex-direction: column; align-items: stretch; }
      nav ul { flex-wrap: wrap; justify-content: center; }
      .search-box { width: 100%; }
      .search-box input { flex: 1; }
      .banner h1 { font-size: 1.8rem; }
      .contact-form { padding: 20px; }
    }
  </style>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
  <!-- Header -->
  <header>
    <div class="container">
      <div class="logo">Bike<span>City</span> Maçapá</div>
      <nav>
        <ul>
          <li><a href="#home">Início</a></li>
          <li><a href="#catalogo">Catálogo</a></li>
          <li><a href="#beneficios">Benefícios</a></li>
          <li><a href="#contato">Contato</a></li>
        </ul>
      </nav>
      <div class="search-box">
        <input type="text" id="searchInput" placeholder="Buscar produtos...">
        <button onclick="searchProducts()"><i class="fas fa-search"></i></button>
      </div>
    </div>
  </header>

  <!-- Banner -->
  <section class="banner" id="home">
    <div class="container">
      <h1>Encontre sua bike ideal</h1>
      <p>As melhores marcas com os melhores preços em Maçapá</p>
      <a href="#catalogo" class="cta">Ver Catálogo</a>
    </div>
  </section>

  <!-- Filters -->
  <section class="filters" id="catalogo">
    <div class="container">
      <select id="categoryFilter">
        <option value="">Todas as categorias</option>
        <option value="mountain">Mountain Bike</option>
        <option value="speed">Speed</option>
        <option value="urbana">Urbana</option>
        <option value="infantil">Infantil</option>
      </select>
      <input type="number" id="minPrice" placeholder="Preço mínimo" min="0">
      <input type="number" id="maxPrice" placeholder="Preço máximo" min="0">
      <button onclick="applyFilters()">Filtrar</button>
    </div>
  </section>

  <!-- Products -->
  <section class="products">
    <div class="container">
      <h2>Nossos Produtos</h2>
      <div class="product-grid" id="productGrid">
        <!-- Products will be injected by JS -->
      </div>
    </div>
  </section>

  <!-- Benefits -->
  <section class="benefits" id="beneficios">
    <div class="container">
      <h2>Por que escolher a BikeCity?</h2>
      <div class="benefits-grid">
        <div class="benefit-item">
          <i class="fas fa-truck"></i>
          <h3>Frete Grátis</h3>
          <p>Para compras acima de R$ 200</p>
        </div>
        <div class="benefit-item">
          <i class="fas fa-shield-alt"></i>
          <h3>Garantia</h3>
          <p>1 ano de garantia em todos os produtos</p>
        </div>
        <div class="benefit-item">
          <i class="fas fa-credit-card"></i>
          <h3>Parcele em até 12x</h3>
          <p>Sem juros no cartão</p>
        </div>
        <div class="benefit-item">
          <i class="fas fa-headset"></i>
          <h3>Suporte 24h</h3>
          <p>Atendimento personalizado</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Contact Form -->
  <section class="contact" id="contato">
    <div class="container">
      <h2>Entre em Contato</h2>
      <div class="contact-form">
        <form id="contactForm" onsubmit="return handleSubmit(event)">
          <div class="form-group">
            <label for="nome">Nome</label>
            <input type="text" id="nome" required>
            <div class="error" id="nomeError">Por favor, insira seu nome.</div>
          </div>
          <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" required>
            <div class="error" id="emailError">Por favor, insira um email válido.</div>
          </div>
          <div class="form-group">
            <label for="telefone">Telefone</label>
            <input type="tel" id="telefone" pattern="[0-9]{2}[0-9]{4,5}[0-9]{4}" placeholder="(96) 91234-5678" required>
            <div class="error" id="telefoneError">Por favor, insira um telefone válido (apenas números).</div>
          </div>
          <div class="form-group">
            <label for="assunto">Assunto</label>
            <select id="assunto" required>
              <option value="">Selecione...</option>
              <option value="Informações sobre produtos">Informações sobre produtos</option>
              <option value="Orçamento">Orçamento</option>
              <option value="Reclamação">Reclamação</option>
              <option value="Outro">Outro</option>
            </select>
            <div class="error" id="assuntoError">Por favor, selecione um assunto.</div>
          </div>
          <div class="form-group">
            <label for="mensagem">Mensagem</label>
            <textarea id="mensagem" rows="5" required></textarea>
            <div class="error" id="mensagemError">Por favor, escreva sua mensagem.</div>
          </div>
          <button type="submit"><i class="fab fa-whatsapp"></i> Enviar via WhatsApp</button>
        </form>
      </div>
    </div>
  </section>

  <!-- Floating WhatsApp Button -->
  <a class="whatsapp-float" href="https://wa.me/559691322552?text=Ol%C3%A1%20BikeCity!%20Gostaria%20de%20mais%20informa%C3%A7%C3%B5es%20sobre%20seus%20produtos." target="_blank" rel="noopener noreferrer">
    <i class="fab fa-whatsapp"></i>
  </a>

  <!-- Footer -->
  <footer>
    <div class="container">
      <div class="info">
        <p>&copy; 2024 BikeCity Maçapá - Todos os direitos reservados</p>
        <p>Endereço: Rua das Bicicletas, 123 - Centro</p>
        <p>Telefone: (96) 9132-2552</p>
      </div>
      <div class="social">
        <a href="#" target="_blank"><i class="fab fa-facebook"></i></a>
        <a href="#" target="_blank"><i class="fab fa-instagram"></i></a>
        <a href="#" target="_blank"><i class="fab fa-whatsapp"></i></a>
      </div>
    </div>
  </footer>

  <script>
    // Sample products
    const products = [
      { name: "Bike Mountain Aro 29", category: "mountain", price: 2499.90, oldPrice: 2999.90, installment: "12x de R$ 208,33", image: "https://via.placeholder.com/300x200/1E90FF/ffffff?text=Mountain+29" },
      { name: "Bike Speed Aro 700", category: "speed", price: 3499.90, oldPrice: 3999.90, installment: "12x de R$ 291,66", image: "https://via.placeholder.com/300x200/32CD32/ffffff?text=Speed+700" },
      { name: "Bike Urbana Aro 26", category: "urbana", price: 1299.90, oldPrice: 1599.90, installment: "12x de R$ 108,33", image: "https://via.placeholder.com/300x200/FF8C00/ffffff?text=Urbana+26" },
      { name: "Bike Infantil Aro 20", category: "infantil", price: 899.90, oldPrice: 1099.90, installment: "12x de R$ 75,00", image: "https://via.placeholder.com/300x200/1E90FF/ffffff?text=Infantil+20" },
      { name: "Capacete Profissional", category: "acessorios", price: 149.90, oldPrice: 199.90, installment: "3x de R$ 49,97", image: "https://via.placeholder.com/300x200/32CD32/ffffff?text=Capacete" },
      { name: "Kit Manutenção", category: "acessorios", price: 79.90, oldPrice: 99.90, installment: "3x de R$ 26,63", image: "https://via.placeholder.com/300x200/FF8C00/ffffff?text=Kit+Manuten%C3%A7%C3%A3o" }
    ];

    function renderProducts(filteredProducts) {
      const grid = document.getElementById('productGrid');
      if (!filteredProducts) filteredProducts = products;
      grid.innerHTML = '';
      filteredProducts.forEach(p => {
        const card = document.createElement('div');
        card.className = 'product-card';
        card.innerHTML = `
          <img src="${p.image}" alt="${p.name}">
          <div class="product-info">
            <h3>${p.name}</h3>
            <p class="old-price">De R$ ${p.oldPrice.toFixed(2)}</p>
            <p class="price">Por R$ ${p.price.toFixed(2)}</p>
            <p class="installment">${p.installment}</p>
          </div>
        `;
        grid.appendChild(card);
      });
    }

    function applyFilters() {
      const category = document.getElementById('categoryFilter').value;
      const minPrice = parseFloat(document.getElementById('minPrice').value) || 0;
      const maxPrice = parseFloat(document.getElementById('maxPrice').value) || Infinity;
      let filtered = products.filter(p => {
        if (category && p.category !== category) return false;
        if (p.price < minPrice || p.price > maxPrice) return false;
        return true;
      });
      renderProducts(filtered);
    }

    function searchProducts() {
      const query = document.getElementById('searchInput').value.toLowerCase();
      if (!query) { renderProducts(); return; }
      const filtered = products.filter(p => p.name.toLowerCase().includes(query));
      renderProducts(filtered);
    }

    // Contact form validation and WhatsApp
    function handleSubmit(event) {
      event.preventDefault();
      let valid = true;
      const fields = ['nome', 'email', 'telefone', 'assunto', 'mensagem'];
      fields.forEach(f => {
        const el = document.getElementById(f);
        const errorEl = document.getElementById(f + 'Error');
        if (!el.value.trim()) {
          errorEl.style.display = 'block';
          valid = false;
        } else {
          errorEl.style.display = 'none';
        }
      });
      // Additional validation for email
      const email = document.getElementById('email');
      if (email.value && !/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email.value)) {
        document.getElementById('emailError').style.display = 'block';
        valid = false;
      }
      // Phone validation (accepts digits only)
      const telefone = document.getElementById('telefone');
      if (telefone.value && !/^[0-9]{10,11}$/.test(telefone.value.replace(/\D/g,''))) {
        document.getElementById('telefoneError').style.display = 'block';
        valid = false;
      }
      if (!valid) return false;
      // Build WhatsApp message
      const nome = document.getElementById('nome').value.trim();
      const emailVal = document.getElementById('email').value.trim();
      const tel = document.getElementById('telefone').value.trim();
      const assunto = document.getElementById('assunto').value;
      const mensagem = document.getElementById('mensagem').value.trim();
      const texto = `Olá BikeCity! Me chamo ${nome}.\n\nEmail: ${emailVal}\nTelefone: ${tel}\nAssunto: ${assunto}\nMensagem: ${mensagem}`;
      const url = `https://wa.me/559691322552?text=${encodeURIComponent(texto)}`;
      window.open(url, '_blank');
      return false;
    }

    // Initial render
    renderProducts();
  </script>
</body>
</html>
