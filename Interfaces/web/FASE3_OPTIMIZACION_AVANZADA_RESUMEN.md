/* MASTER TECHNOLOGY BAR - OPTIMIZED STYLESHEET */

/* === IMPORTACIÓN DIRECTA DE COMPONENTES BEM === */
@import './components/top-navigation.css';
@import './components/product.css';
@import './components/category.css';

/* === VARIABLES GLOBALES CONSOLIDADAS === */
:root {
  /* Core Colors - Simplified */
  --primary: #f3f6f6;
  --accent: #00f7ff;
  --bg: #000;
  --text: #ECE9D8;
  --card-bg: rgba(0,0,0,0.7);
  --border: #00f7ff40;
  
  /* Unified Shadows */
  --shadow-base: 0 0 10px rgba(0, 247, 255, 0.3);
  --shadow-hover: 0 0 20px rgba(0, 247, 255, 0.6);
  
  /* Layout Constants */
  --transition: 0.3s ease;
  --border-radius: 10px;
  --container-width: 95%;
  --container-max: 1400px;
  --spacing: 20px;
  --nav-height: 60px;
  
  /* === ESTANDARIZACIÓN DE COLUMNAS === */
  --container-width-3: 100%;     /* Interfaces de 3 columnas (Refrescos, Cervezas) */
  --container-width-4: 97%;      /* Interfaces de 4 columnas (reducido 3%) */
  --container-width-5: 97%;      /* Interfaces de 5 columnas (mismo ancho visual que 4) */
  
  /* Thumbnails estandarizados */
  --thumb-size-3: clamp(90px, 14vw, 140px);
  --thumb-size-4: clamp(80px, 12vw, 130px);  /* Referencia de Coctelería */
  --thumb-size-5: clamp(75px, 11vw, 120px);
  
  /* Fuentes base */
  --font-size-base: clamp(14px, 2vw, 18px);
  --font-size-price: clamp(12px, 1.8vw, 16px);
  --font-size-name: clamp(13px, 1.9vw, 17px);
  
  /* Espaciado */
  --gap-3: clamp(20px, 3vw, 30px);
  --gap-4: clamp(18px, 2.8vw, 28px);
  --gap-5: clamp(15px, 2.5vw, 25px);
  
  /* Padding */
  --padding-3: clamp(20px, 3vw, 30px);
  --padding-4: clamp(18px, 2.8vw, 28px);
  --padding-5: clamp(15px, 2.5vw, 25px);
  
  /* Botones licores */
  --liquor-button-scale: 0.85;
  
  /* Legacy support */
  --primary-color: var(--primary);
  --accent-color: var(--accent);
  --background-color: var(--bg);
  --text-color: var(--text);
  --price-color: var(--accent);
  --border-color: var(--border);
  --transition-time: var(--transition);
  --table-width: var(--container-width);
  --table-max-width: var(--container-max);
  --table-margin: var(--spacing);
  
  /* === VARIABLES MÓVILES ESPECÍFICAS === */
  --mobile-sidebar-width: 140px;
  --mobile-padding: 8px;
  --mobile-gap: 8px;
  --mobile-font-base: 0.8rem;
  --mobile-font-small: 0.7rem;
  --mobile-font-tiny: 0.6rem;
  
  /* Top Navigation Variables */
  --top-nav-height: 60px;
  --top-nav-bg: rgba(0, 0, 0, 0.95);
  --top-nav-border: #00f7ff;
  
  /* Fixed top navigation height for all screen sizes */
  --top-nav-height-mobile: 60px;
  --top-nav-height-tablet: 60px;
  --top-nav-height-desktop: 60px;
}

/* ================================================================= 
   RESET Y ELEMENTOS BASE - MOBILE FIRST
   ================================================================= */
* { 
  margin: 0; 
  padding: 0; 
  box-sizing: border-box; 
}

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Montserrat', sans-serif;
  min-height: 100vh;
  overflow-x: hidden;
}

/* === LAYOUT PRINCIPAL === */

#app { 
  width: 100%;
  max-width: 100vw;
  min-height: 100vh; 
  position: relative; 
  margin: 0;
  padding: 0 clamp(8px, 3vw, 2rem);
  box-sizing: border-box;
}

/* Contenedor principal flexbox */
.content-container-flex {
  display: flex;
  flex-direction: column;
  flex-wrap: nowrap;
  justify-content: center;
  gap: clamp(8px, 2vw, 1rem);
  width: 100%;
  min-width: 320px;
  max-width: 1400px;
  margin: 0 auto;
  transition: all 0.3s ease;
}

/* Contenido principal */
#content-container {
  flex: 1 1 auto;
  min-width: 0; /* para evitar overflow */
  max-width: 1120px;
  width: 100%;
  padding: 0 clamp(8px, 3vw, 12px);
}

/* Centrado cuando no hay orden */
body:not(.order-mode-active) .content-container-flex {
  justify-content: center;
}

body:not(.order-mode-active) #content-container {
  flex: 0 1 auto;
  width: 72%;
  max-width: 1120px;
}

.screen { 
  position: absolute; 
  top: 0; 
  left: 0; 
  width: 100%; 
  height: 100vh; 
  display: flex; 
  flex-direction: column; 
  justify-content: center; 
  align-items: center; 
  z-index: 1; 
}

/* Video de fondo */
#background-video {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  z-index: -1;
  opacity: 0.4;
}

/* === TIPOGRAFÍA Y BRANDING === */

/* Sistema tipográfico */
.welcome-text, .title-text, .category-title {
  font-family: 'Playfair Display', serif;
  color: var(--text);
  text-align: center;
  animation: fadeIn 1s ease-in-out;
  text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.8);
}

.welcome-text { font-size: clamp(2rem, 4vw, 3rem); }
.title-text { font-size: clamp(2.5rem, 5vw, 4rem); color: var(--accent); }
.category-title { font-size: clamp(1.5rem, 3vw, 2.5rem); }

/* Sistema de logos */
.logo-container {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--spacing);
}

.logo, .main-logo {
  max-width: clamp(200px, 25vw, 300px);
  height: auto;
  animation: fadeIn 1s ease-in-out;
  filter: drop-shadow(var(--shadow-base));
  transition: var(--transition);
}

.logo:hover, .main-logo:hover {
  transform: scale(1.05);
  filter: drop-shadow(var(--shadow-hover));
}

.main-logo {
  content: url('https://udtlqjmrtbcpdqknwuro.supabase.co/storage/v1/object/public/productos/recursos/logos/Logo5.webp');
  display: block;
  margin: 0 auto;
}

/* Pantalla principal */
.main-content-screen {
  padding: 20px;
  justify-content: flex-start;
  background-color: transparent;
}

/* === NAVEGACIÓN Y BOTONES === */

/* Menú principal */
.navigation-menu {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 10px;
  margin-bottom: 20px;
}

.nav-row {
  display: flex;
  justify-content: center;
  gap: 10px;
  flex-wrap: wrap;
}

/* Elementos transparentes */
.nav-button, .view-toggle-btn, .page-title, .product-table td, .liquor-table td {
  background: transparent;
}

/* Botones de navegación */
.nav-button, .view-toggle-btn {
  border: 2px solid var(--primary);
  color: var(--text);
  padding: 8px 15px;
  font: 600 1rem 'Montserrat', sans-serif;
  cursor: pointer;
  transition: var(--transition);
  border-radius: 8px;
  text-decoration: none;
  display: inline-flex;
  align-items: center;
  justify-content: center;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.view-toggle-btn {
  font-size: 1.2rem;
  width: 50px;
  height: 50px;
  backdrop-filter: blur(10px);
  font-weight: bold;
}

/* Estados hover */
.nav-button:hover, .nav-button.active, 
.view-toggle-btn:hover, .view-toggle-btn.active {
  background-color: var(--primary);
  color: var(--bg);
  transform: scale(1.05);
  box-shadow: var(--shadow-base);
}

/* === COMPONENTES DE LAYOUT === */

/* Layout de página */
.page-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: var(--container-width);
  max-width: var(--container-max);
  margin: 0 auto;
  position: relative;
}

.page-title {
  font-family: 'Playfair Display', serif;
  color: var(--text);
  font-size: clamp(1.5rem, 3vw, 2rem);
  text-align: center;
  width: 100%;
  margin: 0 0 15px 0;
  padding: 15px var(--spacing);
  border-bottom: 2px solid var(--border);
}

/* Botones de acción principales */
#create-order-btn, #orders-btn {
  position: relative;
  z-index: 1;
  min-width: 120px; 
}

#create-order-btn {
  margin-left: auto;
}

/* Pantalla de órdenes */
.orders-screen {
  width: 100%;
  max-width: 1200px;
  margin: 0 auto;
  padding: 20px;
}

.orders-screen-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 30px;
  width: 100%;
  position: relative;
}

.orders-screen-title {
  font-family: 'Playfair Display', serif;
  color: var(--text-color);
  font-size: 2rem;
  text-align: center;
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  width: auto;
  margin: 0;
  white-space: nowrap;
}

/* Botones de navegación de órdenes */
.orders-back-btn, .history-btn {
  position: relative;
  z-index: 1;
}

.history-btn {
  margin-left: auto;
}

/* Contenedores de contenido principal */
.content-wrapper {
  display: flex;
  width: 100%;
  gap: 0px;
  position: relative;
  margin-top: 0;
  padding-right: 0px;
  justify-content: center; /* Centrar contenido normalmente */
}

#content-container {
  flex: 1;
  padding: 0;
  margin-right: 0;
  display: flex;
  justify-content: center;
  width: 100%;
}

.content-container-flex {
  display: flex;
  align-items: flex-start;
  justify-content: flex-start;
  width: 100%;
  gap: 20px;
}

/* Botón hamburguesa en contenedor flex */
.content-container-flex .hamburger-btn {
  position: relative;
  top: unset;
  left: unset;
  margin-right: 20px;
  margin-top: 20px;
  position: sticky;
  top: 20px;
  z-index: 1000;
}

/* ================================================================= 
   ELEMENTOS MULTIMEDIA
   ================================================================= */

/* Iconos de video e imagen */
.video-icon, .image-icon {
  cursor: pointer;
  text-align: center;
  opacity: 0.8;
  transition: all 0.3s ease;
  /* backdrop-filter: blur(5px); */
}

/* Video thumbnails */
.video-thumb {
  width: 80px;
  height: 56px;
  object-fit: cover;
  border-radius: 8px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

.video-thumb:hover {
  transform: scale(1.05);
}

/* Estilos por categoría */
[data-category="carnes"] .video-thumb {
  width: 100px;
  height: 70px;
  border-radius: 6px;
}

[data-category="cafe"] .video-thumb {
  width: 90px;
  height: 60px;
}

[data-category="postres"] .video-thumb:hover {
  transform: rotate(-2deg) scale(1.05);
}

[data-category="sopas"] .video-thumb {
  border: 1px solid rgba(255, 165, 0, 0.3);
}

/* Miniaturas adaptables */

/* === TABLES & GRID CONTAINERS === */
.container, .category-grid, .product-grid, .product-table, .liquor-table {
  width: var(--container-width);
  max-width: var(--container-max);
  margin: var(--spacing) auto;
  background: var(--card-bg);
  border-radius: var(--border-radius);
  box-shadow: var(--shadow-hover);
  position: relative;
  border: 1px solid var(--border);
}

/* Mejoras de tabla */
.product-table, .liquor-table {
  border-collapse: separate;
  border-spacing: 0 10px;
  padding: var(--spacing);
}

/* Celdas de tabla */
.product-table th, .liquor-table th {
  font: 600 1rem 'Montserrat', sans-serif;
  color: var(--primary);
  text-align: center;
  padding: 15px 10px;
  border-bottom: 2px solid var(--border);
  text-transform: uppercase;
  letter-spacing: 1px;
}

.product-table th:first-child, .liquor-table th:first-child,
.product-table td:first-child, .liquor-table td:first-child {
  text-align: left;
  padding-left: 15px;
}

.product-table td, .liquor-table td {
  padding: 15px 10px;
  transition: var(--transition);
  text-align: center;
  vertical-align: middle;
}

.product-table td.product-name, .liquor-table td.product-name {
  font: 600 1rem 'Montserrat', sans-serif;
  color: var(--primary);
  letter-spacing: 0.5px;
  text-transform: uppercase;
}

/* Celdas especiales */
.product-table td.image-icon, .liquor-table td.image-icon,
.product-table td.video-icon, .liquor-table td.video-icon,
.product-table td.product-price, .liquor-table td.product-price {
  text-align: center;
  padding: 10px;
  vertical-align: middle;
}

.product-table td.image-icon img, .liquor-table td.image-icon img {
  display: block;
  margin: 0 auto;
}

.product-table td.product-ingredients {
  text-align: left;
  padding: 15px 10px;
}

.product-table tr:hover td, .liquor-table tr:hover td {
  background-color: rgba(0, 0, 0, 0.4);
}

/* Media Elements - Optimized */
.image-icon img, .product-table td.image-icon img {
  width: 40px;
  height: 40px;
  object-fit: contain;
  background: white;
  cursor: pointer;
  animation: glow 2s infinite;
  border-radius: var(--border-radius);
  transition: var(--transition);
  display: block;
}

.liquor-table td.image-icon img {
  width: 52px;
  height: 52px;
}

.image-icon img:hover, .category-image:hover {
  transform: scale(1.2);
  box-shadow: var(--glow-shadow-hover);
}

.product-table td.image-icon {
  text-align: left;
  padding-left: 10px;
  width: 60px;
}

/* Animations - Consolidated */
@keyframes glow {
  0%, 100% { box-shadow: var(--glow-shadow); }
  50% { box-shadow: 0 0 15px rgba(0, 247, 255, 0.5); }
}

@keyframes fadeIn {
  from { opacity: 0; transform: translateY(20px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes slideIn {
  from { transform: translateX(-100%); opacity: 0; }
  to { transform: translateX(0); opacity: 1; }
}

@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}

/* =================================================================
   GRID LAYOUTS - MOBILE FIRST RESPONSIVE SYSTEM
   ================================================================= */
/* CATEGORY GRID RULES MOVED TO COMPONENTS/CATEGORY-GRID.CSS */
/* Reglas de .category-grid ahora manejadas por el componente BEM */

/* PRODUCT GRID RULES MOVED TO COMPONENTS/PRODUCT-GRID.CSS */
/* Reglas de .product-grid ahora manejadas por el componente BEM */

/* Tipografía mobile-first */
.product-card .product-name,
.category-card .category-name {
  font-size: clamp(12px, 1.8vw, 14px);
  line-height: 1.2;
}

.product-card .product-ingredients {
  font-size: clamp(11px, 1.6vw, 13px);
  line-height: 1.3;
}

.price-button {
  font-size: clamp(11px, 1.6vw, 13px);
  padding: clamp(4px, 1vw, 8px) clamp(6px, 1.5vw, 12px);
}

/* =================================================================
   ESTANDARIZACIÓN MODO TABLA - SISTEMA DE COLUMNAS
   ================================================================= */

/* Standardized Tables - Already optimized above */

/* Modificadores de columna */
.cols-3.product-table, .cols-4.product-table,
.cols-5.liquor-table {
  width: 97%; /* Ancho estandarizado para todas las tablas */
  max-width: var(--table-max-width);
  margin: var(--table-margin) auto;
}

/* === THUMBNAILS ESTANDARIZADOS === */
/* 3 columnas */
.cols-3 .image-icon img {
  width: var(--thumb-size-3);
  height: var(--thumb-size-3);
}

/* 4 columnas */
.cols-4 .image-icon img,
.product-table .image-icon img {
  width: var(--thumb-size-4);
  height: var(--thumb-size-4);
}

/* 5 columnas */
.cols-5 .image-icon img,
.liquor-table .image-icon img {
  width: var(--thumb-size-5);
  height: var(--thumb-size-5);
}

/* === TIPOGRAFÍA ESTANDARIZADA === */
/* Nombres */
.cols-3 .product-name,
.cols-4 .product-name,
.cols-5 .product-name {
  font-size: var(--font-size-name);
  font-weight: 600;
  color: var(--primary-color);
  letter-spacing: 0.5px;
  text-transform: uppercase;
}

/* Precios */
.cols-3 .product-price,
.cols-4 .product-price,
.cols-5 .product-price {
  font-size: var(--font-size-price);
  color: var(--price-color);
}

/* === BOTONES LICORES === */
.cols-5 .price-button,
.liquor-table .price-button {
  transform: scale(var(--liquor-button-scale));
  font-size: calc(var(--font-size-price) * var(--liquor-button-scale));
}

/* === AJUSTES POR VISTA === */

/* Vista 4 columnas */
.cols-4.product-table {
  width: 97%; /* Reducción del 3% del contenedor padre */
  margin: 0 auto; /* Centrado horizontal */
}

/* Thumbnails 4 columnas */
.cols-4 .image-icon img,
.product-table .image-icon img {
  width: var(--thumb-size-4);
  height: var(--thumb-size-4);
}

/* Tipografía 4 columnas */
.cols-4 .product-name {
  font-size: var(--font-size-name);
  line-height: 1.2;
}

.cols-4 .product-price {
  font-size: var(--font-size-price);
  font-weight: 600;
}

/* Vista de 3 columnas - Ampliar ancho para mejor distribución */
.cols-3.product-table {
  width: 100%; /* Ancho completo para mejor distribución */
  margin: 0 auto;
}

/* Vista de 5 columnas - Igualar ancho al de 4 columnas */
.cols-5.liquor-table {
  width: 97%; /* Mismo ancho que 4 columnas */
  margin: 0 auto;
}

.category-grid .page-title, .product-grid .page-title {
  grid-column: 1 / -1;
  text-align: center;
  border-bottom: 2px solid var(--border-color);
  padding-bottom: 15px;
  margin-bottom: 20px;
}

.category-grid .page-title {
  margin-bottom: 5px;
}

/* Card Components - Unified */
.category-card, .product-card {
  background: var(--card-bg);
  border-radius: var(--border-radius);
  overflow: hidden;
  transition: var(--transition);
  cursor: pointer;
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 15px;
  box-shadow: var(--shadow-base);
}

.category-card:hover, .product-card:hover {
  transform: translateY(-5px) scale(1.02);
  box-shadow: var(--shadow-hover);
}

/* Thumbnails - Responsive System */
.category-image, .product-image {
  width: var(--thumb-size-4);
  height: var(--thumb-size-4);
  object-fit: contain;
  background: white;
  margin-bottom: clamp(5px, 1vw, 10px);
  animation: glow 2s infinite;
  border-radius: var(--border-radius);
  transition: var(--transition);
}

/* Column-specific thumbnail sizes */
.cols-3 .category-image, .cols-3 .product-image {
  width: var(--thumb-size-3);
  height: var(--thumb-size-3);
}

.cols-4 .category-image, .cols-4 .product-image {
  width: var(--thumb-size-4);
  height: var(--thumb-size-4);
}

.cols-5 .category-image, .cols-5 .product-image {
  width: var(--thumb-size-5);
  height: var(--thumb-size-5);
}

.category-name {
  font: 600 1rem 'Montserrat', sans-serif;
  color: white;
  text-align: center;
}

/* Product Card - Adaptación dentro del espacio asignado */
.product-card {
  /* Altura flexible que se adapta al contenido pero mantiene consistencia */
  min-height: clamp(300px, 35vh, 400px);
  /* max-height: removido para permitir expansión según contenido */
  height: auto;
  display: flex;
  flex-direction: column;
  padding: clamp(15px, 1.8vw, 20px);
  gap: clamp(10px, 1.2vw, 15px);
}

/* Product Card Elements - Sistema responsive de dos niveles */
.product-card .product-name {
  font: 600 1.1rem 'Montserrat', sans-serif;
  color: white;
  margin-bottom: 10px;
  text-align: center;
  order: 1;
  
  /* NIVEL 1: Espacio fijo asignado al componente - reducido 20% */
  height: clamp(1.92rem, 2.88vw + 0.8rem, 2.56rem);
  
  /* NIVEL 2: Contenido se adapta al espacio disponible - aumentado 25% */
  font-size: clamp(0.69rem, 1.46vw + 0.406rem, 0.975rem);
  line-height: clamp(1.2, 1.5vw + 1rem, 1.4);
  
  /* Configuración sin truncamiento - texto completo visible */
  display: block;
  overflow: visible;
  text-overflow: unset;
  word-wrap: break-word;
  hyphens: auto;
  
  /* Sin limitación de líneas - mostrar todo el contenido */
  -webkit-line-clamp: unset;
  line-clamp: unset;
  
  /* Forzar ellipsis cuando el contenido excede el espacio */
  position: relative;
}

/* Títulos de licores */
.product-card.liquor-card .product-name {
  font-size: clamp(0.63rem, 1.35vw + 0.375rem, 0.9rem);
  line-height: clamp(1.15, 1.8vw + 0.9rem, 1.35);
  -webkit-line-clamp: unset;
  line-clamp: unset;
  overflow: visible;
  text-overflow: unset;
  display: block;
  height: clamp(1.62rem, 2.16vw + 0.864rem, 2.376rem);
  min-height: unset;
  font-weight: 700;
  letter-spacing: 0.02em;
}



.product-card .product-media {
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 15px;
  min-height: 180px;
  order: 2;
  width: 100%;
}

.product-card .product-ingredients {
  color: var(--text-color);
  margin-bottom: 15px;
  text-align: justify;
  text-justify: inter-word;
  opacity: 0.8;
  flex-grow: 1;
  order: 3;
  
  font-size: clamp(0.7rem, 1.5vw + 0.3rem, 0.9rem);
  line-height: clamp(1.2, 1.3vw + 1rem, 1.4);
  display: block;
  overflow: visible;
  text-overflow: unset;
  word-wrap: break-word;
  hyphens: auto;
  -webkit-line-clamp: unset;
  line-clamp: unset;
  position: relative;
  height: auto;
  min-height: clamp(3.96rem, 4.95vw + 2.2rem, 5.5rem);
  max-height: none;
}


.product-card .product-ingredients::after {
  display: none;
}


.product-card .product-ingredients[data-truncated="true"]::after {
  display: none;
}

/* Imágenes de productos */
.product-card .product-image {
  width: 100%;
  height: 180px;
  object-fit: contain;
  background: white;
  border-radius: 8px;
  cursor: pointer;
  transition: transform 0.3s ease;
}

/* Imágenes de licores */
.product-card.liquor-card .product-image {
  height: clamp(120px, 15vw + 2vh, 200px);
  width: 100%;
  object-fit: contain;
  object-position: center;
  background: white;
  
  /* Transición suave para cambios de tamaño */
  transition: all 0.3s ease;
}

/* Ajustar el contenedor de media para licores */
.product-card.liquor-card .product-media {
  /* Altura responsiva del contenedor */
  min-height: clamp(120px, 15vw + 2vh, 200px);
  height: auto;
  
  /* Centrado perfecto */
  display: flex;
  justify-content: center;
  align-items: center;
  
  /* Margen responsivo */
  margin-bottom: clamp(8px, 1.2vw, 15px);
}

/* Configuración específica para thumbnails de video (mantener tamaño anterior) */
.product-card .video-thumbnail {
  width: 100%;
  height: 140px; /* Tamaño anterior */
  object-fit: cover; /* Tamaño anterior */
  border-radius: 8px;
  padding: 0;
  cursor: pointer;
  transition: transform 0.3s ease;
}

/* Hover effects separados */
.product-card .product-image:hover {
  transform: scale(1.1);
}

.product-card .video-thumbnail:hover {
  transform: scale(1.1);
}

/* Ajustar el contenedor de media para thumbnails */
.product-card:has(.video-thumbnail) .product-media {
  min-height: 140px; /* Mantener altura anterior para videos */
}

.product-card:has(.product-image) .product-media {
  min-height: 180px; /* Nueva altura para imágenes */
}

.product-card .product-prices {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  justify-content: center;
  order: 4;
  margin-top: auto;
}

/* =================================================================
   LIQUOR CARD LAYOUT STYLES - CLEANED
   ================================================================= */
.product-card.liquor-card .product-prices {
  display: flex;
  flex-direction: column;
  gap: clamp(3px, 1.5%, 8px);
  align-items: flex-start;
  width: 100%;
  min-height: clamp(75px, 25%, 140px);
  justify-content: space-between;
}

.product-card.liquor-card .price-item {
  display: flex;
  align-items: center;
  gap: clamp(4px, 2%, 10px);
  width: 100%;
  min-height: clamp(20px, 8%, 36px);
  flex-shrink: 0;
}

.product-card.liquor-card .price-label {
  color: var(--text-color);
  font-size: clamp(0.55rem, 3% + 0.1rem, 0.8rem);
  font-weight: 500;
  min-width: clamp(35px, 20%, 60px);
  opacity: 0.9;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  line-height: 1.2;
}

/* Liquor card price buttons - compact thumbnail style */
.product-card.liquor-card .price-button {
  padding: 4px 8px;
  font-size: 0.75rem;
  min-width: 50px;
  max-width: 100%;
  flex: 1;
  min-height: 28px;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  font-weight: 600;
  line-height: 1.1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  transition: all 0.2s ease;
}

/* Estilos optimizados para tarjetas de licores - ELIMINADOS */
/* Las tarjetas ahora usan tamaños naturales sin restricciones responsivas */

/* Price Buttons */
.price-button {
  background: var(--price-bg, transparent);
  color: var(--price-color);
  border: 1px solid var(--price-color);
  padding: 7px 12px;
  border-radius: 5px;
  cursor: pointer;
  transition: all var(--transition-time) ease;
  font: 600 0.9rem 'Montserrat', sans-serif;
  min-height: 32px;
}

.price-button:hover {
  background: var(--price-color);
  color: var(--background-color);
  transform: scale(1.05);
}

.price-button.non-selectable {
  opacity: 0.5;
  cursor: not-allowed;
  pointer-events: none;
}

.price-button.non-selectable:hover {
  transform: none;
  background: var(--price-bg, transparent);
  color: var(--price-color);
}

/* View Toggle */
.view-toggle-container {
  display: flex;
  justify-content: flex-end;
  margin-bottom: 20px;
  padding: 0 20px;
}

.subcategory-prompt {
  grid-column: 1 / -1;
  text-align: center;
  margin: 5px 0 15px 0;
}

.subcategory-prompt h3 {
  font-family: 'Playfair Display', serif;
  color: var(--primary-color);
  font-size: 1.3rem;
  font-weight: 400;
  opacity: 0.9;
}

/* =================================================================
   MODALS - CONSOLIDATED STYLES
   ================================================================= */

/* Modal backdrop */
.modal-backdrop, .modal {
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.8);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 1000;
}

.modal-backdrop {
  z-index: 9999;
}

.modal {
  padding: 10px;
  box-sizing: border-box;
}

/* Base modal content - SINGLE SOURCE OF TRUTH */
.modal-content {
  position: relative;
  width: 30%;
  max-width: 400px;
  max-height: 78.2vh;
  background: rgba(0, 0, 0, 0.95);
  border-radius: 15px;
  box-shadow: 0 0 30px var(--price-color);
  border: 1px solid var(--border-color);
  padding: 25px 15px;
  display: flex;
  flex-direction: column;
  flex: 1;
  min-height: 0;
  overflow: hidden;
}

/* Drink options modal specific sizing - Horizontal layout */
#drink-options-modal .modal-content {
  width: 60%;
  max-width: 700px;
  max-height: 92vh;
  padding: 20px;
  min-width: 450px;
  border-radius: 12px;
  height: auto;
}

/* Meat customization modal specific sizing */
#meat-customization-modal .modal-content {
  width: 42%;
  max-width: 535px;
  max-height: 43.7vh;
  padding: 21px;
  aspect-ratio: 1.4/1;
}

/* Reglas responsive de modales - ELIMINADAS */
/* Los modales ahora se adaptan naturalmente sin restricciones de dispositivo */

/* Image modals exception */
.modal-content.image-modal {
  width: auto;
  max-width: 450px;
  padding: 20px 15px;
  display: flex;
  flex-direction: column;
  align-items: center;
}

/* Video modal specific styles */
.modal-content.image-modal.video-modal {
  width: 69.83%; /* Increased another 10% from 63.48% (total 45.48% from original 48%) */
  max-width: 699px; /* Increased another 10% from 635px (total 45.63% from original 480px) */
}

/* Modal content elements */
.modal-content h3 {
  color: var(--primary-color);
  margin-bottom: 2.25vh;
  text-align: center;
  line-height: 1.4;
  font-size: clamp(0.9rem, 2.25vw, 1.26rem);
  font-weight: 600;
}

/* Drink options modal specific title */
#drink-options-modal .modal-content h3 {
  font-size: 1rem;
  margin-bottom: 12px;
  line-height: 1.3;
}

/* Meat modal specific title sizing */
#meat-customization-modal .modal-content h3 {
  font-size: clamp(0.9rem, 2.5vw, 1.2rem);
  margin-bottom: 2vh;
}

.modal-content h3 span {
  display: block;
  text-align: center;
  margin-top: 8px;
}

.modal-content img {
  width: auto;
  height: auto;
  max-width: 100%;
  max-height: 50vh;
  object-fit: contain;
  border-radius: 10px;
  margin: 10px 0;
  animation: modalGlow 2s infinite;
}

.modal-content.image-modal video {
  width: 100%;
  border-radius: 5px;
}

.modal-content.image-modal .error-message {
  color: var(--text-color);
  text-align: center;
  padding: 20px;
}

.modal-content.image-modal .nav-button {
  margin-top: 10px;
  padding: 10px 20px;
  display: block;
  margin: 10px auto 0;
  align-self: center;
}

@keyframes modalGlow {
  0%, 100% { box-shadow: 0 0 10px rgba(0, 247, 255, 0.3); }
  50% { box-shadow: 0 0 30px rgba(0, 247, 255, 0.5); }
}

/* Product table and image styles */
.product-table {
  width: var(--table-width);
  max-width: var(--table-max-width);
}

.product-image {
  object-fit: contain;
  cursor: pointer;
}

.video-hidden {
  display: none;
}

.counter-container {
    display: flex;
    align-items: center;
    gap: 8px;
  }
  
  .modal-actions {
    margin-top: 15px;
    gap: 10px;
    flex-wrap: wrap;
    justify-content: center;
    width: 100%;
    display: flex;
  }
  
  .modal-actions .nav-button {
    min-width: 80px;
    padding: 10px 15px;
    font-size: 0.9rem;
  }
  
  /* Drink options modal specific button actions */
  #drink-options-modal .modal-actions {
    margin-top: 10px;
    gap: 8px;
    flex-shrink: 0;
  }
  
  #drink-options-modal .modal-actions .nav-button {
    min-width: 70px;
    padding: 8px 12px;
    font-size: 0.85rem;
  }
  
  .cooking-options {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 8px;
    margin-bottom: 15px;
    width: 100%;
  }
  
  .cooking-option {
    min-width: auto;
    width: 100%;
    padding: 10px 8px;
    font-size: 0.9rem;
  }
  
  .ingredients-choice,
  .garnish-choice {
    flex-direction: row;
    gap: 10px;
    width: 100%;
    justify-content: center;
  }
  
  .ingredients-choice .nav-button,
  .garnish-choice .nav-button {
    flex: 1;
    max-width: 120px;
    text-align: center;
  }
  
  textarea {
    min-height: 80px;
    font-size: 0.9rem;
    padding: 8px;
  }
  
  .total-count-container {
    font-size: 0.9rem;
    padding: 6px;
    margin: 10px 0;
  }
  
  .drink-options-message {
    font-size: 0.9rem;
    line-height: 1.4;
    margin-bottom: 15px;
    padding: 0 5px;
  }
/* Duplicated styles removed - consolidated in main sections */
  
  .counter-btn {
    width: 28px;
    height: 28px;
    font-size: 1rem;
  }
  
  .count-display {
    width: 25px;
    font-size: 0.9rem;
  }
  
  .modal-actions .nav-button {
    min-width: 70px;
    padding: 8px 12px;
    font-size: 0.8rem;
  }
  
  .cooking-option {
    min-width: 100px;
    max-width: 120px;
    padding: 10px 8px;
    font-size: 0.9rem;
  }
  
  .cooking-options {
    gap: 10px;
  }
  
  textarea {
    min-height: 70px;
    font-size: 0.8rem;
    padding: 6px;
  }
  
  .total-count-container {
    font-size: 0.8rem;
    padding: 5px;
  }
  
  .drink-options-message {
    font-size: 0.8rem;
    line-height: 1.3;
    margin-bottom: 12px;
  }
  
  .exclusive-option-group {
    padding: 10px;
    gap: 8px;
  }
  
  .jager-option-container {
    padding: 8px;
    font-size: 0.9rem;
  }
  
  .jager-radio {
    margin-right: 8px;
  }

/* Reglas de modales móviles - ELIMINADAS */
/* Los modales ahora se adaptan naturalmente sin restricciones de dispositivo */

/* Additional Animations */
@keyframes fadeOut { from { opacity: 1; } to { opacity: 0; } }
@keyframes pulseGlow { 0% { box-shadow: 0 0 0 0 rgba(0, 247, 255, 0.4); } 70% { box-shadow: 0 0 0 10px rgba(0, 247, 255, 0); } 100% { box-shadow: 0 0 0 0 rgba(0, 247, 255, 0); } }
.fade-in { animation: fadeIn 1s ease-in-out forwards; }
.fade-out { animation: fadeOut 1s ease-in-out forwards; }

/* =================================================================
   ORDER SIDEBAR - ELEMENTO FLEX DE IGUAL JERARQUÍA
   ================================================================= */

#order-sidebar {
  /* Posicionamiento como flex item */
  position: relative;
  
  /* Dimensiones responsivas */
  flex: 0 0 300px; /* Base: 300px */
  min-width: 250px;
  max-width: 350px;
  
  /* Altura y overflow */
  max-height: calc(100vh - 40px);
  overflow-y: auto;
  overflow-x: hidden;
  
  /* Espaciado */
  padding: 16px;
  margin-top: 20px;
  
  /* Estilos visuales */
  background: var(--card-bg);
  border: 1px solid var(--border-color);
  border-radius: 8px;
  backdrop-filter: blur(10px);
  box-shadow: var(--glow-shadow);
  
  /* Comportamiento */
  display: none;
  transition: all 0.3s ease;
  box-sizing: border-box;
}

/* Cuando el sidebar está visible, mostrarlo como flex item */
body.order-mode-active #order-sidebar {
  display: block;
}

/* Responsividad al reducir espacio */
@media screen and (max-width: 1024px) {
  #order-sidebar {
    flex: 0 0 250px;
    min-width: 200px;
  }
  
  #content-container {
    flex: 1 1 auto;
    min-width: 300px;
  }
}

/* Sidebar para móvil portrait - parte inferior */
/* REGLA MÓVIL ELIMINADA - Ahora manejada por mobile.css */

/* REGLA TABLET ELIMINADA - Ahora manejada por tablet.css */

/* Sidebar Content - Consolidated */

.order-item-header {
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
  flex-wrap: wrap;
  gap: 5px;
  width: 100%;
  box-sizing: border-box;
}

#order-sidebar h3 {
  color: var(--primary);
  font: 1.5rem 'Playfair Display', serif;
  margin-bottom: 15px;
  text-align: center;
}

.order-item {
  border-bottom: 1px solid var(--border);
  padding: 10px 0;
  margin-bottom: 10px;
  width: 100%;
  box-sizing: border-box;
  word-wrap: break-word;
  overflow-wrap: break-word;
}

.order-item-name {
  font-weight: 600;
  color: var(--primary);
  margin-bottom: 5px;
  width: 100%;
  word-wrap: break-word;
  overflow-wrap: break-word;
  hyphens: auto;
}

.order-item-price {
  color: var(--price-color);
  font-weight: 500;
}

.order-item-customization {
  color: #ccc;
  font-size: 0.85rem;
  font-style: italic;
  margin-top: 5px;
  width: 100%;
  word-wrap: break-word;
  overflow-wrap: break-word;
  hyphens: auto;
}

.order-total {
  margin-top: var(--spacing);
  padding-top: 10px;
  border-top: 2px solid var(--border);
}

.order-total h4 {
  font: 1.2rem 'Montserrat', sans-serif;
  color: var(--price-color);
  text-align: right;
}

.order-actions {
  margin-top: 20px;
  display: flex;
  gap: 10px;
  justify-content: space-between;
  width: 100%;
  box-sizing: border-box;
  flex-direction: row;
}

.order-actions button {
  flex: 1;
  min-width: 0;
  padding: 10px 8px;
  font-size: 0.9rem;
}

.modal-actions {
  margin-top: 2.25vh;
  display: flex;
  gap: 1.8vw;
  justify-content: center;
  flex-wrap: wrap;
}

/* Centrar específicamente los botones de Sí/No en modales de carnes */
.ingredients-choice,
.garnish-choice {
  display: flex;
  gap: 18px;
  justify-content: center;
  align-items: center;
  flex-direction: row;
  width: 100%;
  margin-top: 13.5px;
}

/* Meat modal specific spacing */
#meat-customization-modal .ingredients-choice,
#meat-customization-modal .garnish-choice {
  gap: 3%;
  margin-top: 2vh;
}

/* Meat modal specific button sizing */
#meat-customization-modal .ingredients-choice .nav-button,
#meat-customization-modal .garnish-choice .nav-button {
  flex: 0 0 auto;
  min-width: 28%;
  max-width: 32%;
  padding: 1.2vh 1.6vw;
  text-align: center;
  font-size: clamp(0.7rem, 1.6vw, 0.9rem);
  font-weight: 600;
  border-radius: 6px;
  transition: all 0.3s ease;
}

.ingredients-choice .nav-button,
.garnish-choice .nav-button {
  flex: 0 0 auto;
  min-width: 31.5%;
  max-width: 36%;
  padding: 1.35vh 1.8vw;
  text-align: center;
  font-size: clamp(0.81rem, 1.98vw, 0.99rem);
  font-weight: 600;
  border-radius: 7.2px;
  transition: all 0.3s ease;
}

.ingredients-choice .nav-button:hover,
.garnish-choice .nav-button:hover {
  transform: scale(1.05);
  box-shadow: 0 4px 12px rgba(0, 247, 255, 0.4);
}

.modal-header, .modal-footer {
  flex-shrink: 0;
}

.modal-body {
  flex: 1;
  overflow-y: auto;
  width: 100%;
  padding: 0 10px;
}

.options-container {
  display: flex;
  flex-direction: column;
  height: 100%;
}

.options-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(120px, 1fr));
  gap: 12px;
  padding: 10px;
  width: 100%;
  box-sizing: border-box;
}

/* Drink options modal specific grid adjustments */
#drink-options-modal .options-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 20px;
  padding: 20px;
  width: 100%;
  align-content: start;
  justify-content: center;
}

.drink-option {
  background: rgba(0, 247, 255, 0.1);
  border: 2px solid var(--price-color);
  border-radius: 6px;
  padding: 11px 8px;
  color: var(--text-color);
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  cursor: pointer;
  transition: all 0.3s ease;
  min-height: 60px;
  text-align: center;
  word-break: break-word;
  font-size: 0.9rem;
}

/* Drink options modal specific button styling */
#drink-options-modal .drink-option {
  min-height: 50px;
  padding: 10px 8px;
  font-size: 1rem;
  border-radius: 8px;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  align-items: center;
  flex-shrink: 0;
  font-weight: 500;
  word-wrap: break-word;
  hyphens: auto;
  line-height: 1.3;
  width: 100%;
}

.drink-option:hover {
  background: rgba(0, 247, 255, 0.2);
  transform: translateY(-3px);
  box-shadow: 0 5px 15px rgba(0, 247, 255, 0.3);
}

.drink-option.selected {
  background: rgba(0, 247, 255, 0.3);
  border-color: white;
  box-shadow: 0 0 20px var(--price-color);
  transform: scale(1.05);
}

.drink-option-name {
  font-size: 0.85rem;
  font-weight: 500;
  margin-bottom: 4px;
}

.drink-option-price {
  font-size: 0.9rem;
  color: var(--price-color);
  font-weight: bold;
}

.cooking-options {
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  gap: 1.5%;
  margin-bottom: 2vh;
  width: 100%;
  flex-wrap: wrap;
}

.cooking-option {
  min-width: 28%;
  width: auto;
  max-width: 32%;
  padding: 1.2vh 1.5vw;
  font-size: 0.9rem;
  font-weight: 500;
  border-radius: 8px;
  transition: all 0.3s ease;
  flex: 0 0 auto;
}

.cooking-option:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 247, 255, 0.3);
}

.cooking-option.selected {
  background-color: var(--primary-color);
  color: var(--background-color);
}

textarea {
  width: 100%;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid var(--border-color);
  padding: 1.35vh 1.8vw;
  color: var(--text-color);
  min-height: 10.8vh;
  margin-top: 1.8vh;
  font-family: 'Montserrat', sans-serif;
  font-size: clamp(0.81rem, 1.8vw, 0.9rem);
  transition: all var(--transition-time) ease;
}

textarea:focus {
  outline: none;
  border-color: var(--price-color);
}

.price-selection-mode .price-button:not(.product-grid .product-card.liquor-card .price-button) { background: rgba(0, 247, 255, 0.2); transform: scale(1.05); transition: all 0.3s ease; animation: pulseGlow 2s infinite; }

.remove-order-item {
  background: transparent;
  border: none;
  color: #ff6b6b;
  cursor: pointer;
  font-size: 1rem;
  margin-left: 10px;
  flex-shrink: 0;
  min-width: 24px;
  padding: 2px;
}

.order-item-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.drink-options-message {
  color: var(--primary-color);
  margin-bottom: 20px;
  text-align: center;
  font-style: italic;
  max-width: 100%;
  word-wrap: break-word;
}

.total-count-container {
  width: 100%;
  text-align: center;
  margin: 15px 0;
  padding: 8px;
  border: 1px solid var(--border-color);
  border-radius: 5px;
  color: var(--price-color);
}

.drink-option-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding: 12px;
  margin: 8px 0;
  border: 1px solid var(--border);
  transition: var(--transition);
  min-height: 80px;
  width: 100%;
  box-sizing: border-box;
  text-align: center;
  border-radius: 8px;
}

.drink-option-container.selected {
  background-color: rgba(0, 247, 255, 0.2);
  transform: translateY(-2px);
  box-shadow: 0 2px 8px rgba(0, 247, 255, 0.3);
}

.drink-option-name {
  font-weight: 500;
  margin-bottom: 8px;
  text-align: center;
  width: 100%;
}

.counter-container {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 8px;
}

.counter-btn {
  width: 30px;
  height: 30px;
  border-radius: 50%;
  border: 1px solid var(--border);
  background: transparent;
  color: var(--text);
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.2rem;
  cursor: pointer;
  transition: var(--transition);
}

.counter-btn:hover:not(:disabled) {
  background-color: var(--primary);
  color: var(--bg);
}

.counter-btn:disabled {
  opacity: 0.5;
  cursor: not-allowed;
}

.count-display {
  width: 30px;
  text-align: center;
  font-weight: bold;
  color: var(--price-color);
  font-size: 1.1rem;
  min-width: 30px;
}

.saved-orders {
  width: 100%;
  margin-bottom: 20px;
}

.saved-order {
  background: var(--card-bg);
  border: 1px solid var(--border);
  backdrop-filter: blur(10px);
  padding: 15px;
  margin-bottom: 15px;
  transition: var(--transition);
}

.saved-order h3 {
  color: var(--primary);
  font: 1.3rem 'Playfair Display', serif;
  margin-bottom: 10px;
  text-align: center;
  border-bottom: 1px solid var(--border);
  padding-bottom: 5px;
}

.saved-order-items {
  margin-bottom: 10px;
}

.saved-order-item {
  padding: 5px 0;
  margin-bottom: 5px;
  border-bottom: 1px solid rgba(0, 247, 255, 0.1);
}

.saved-order-item-name {
  font-weight: 600;
  color: var(--primary);
  margin-bottom: 3px;
}

.saved-order-item-price {
  color: var(--price-color);
  font-weight: 500;
  font-size: 0.9rem;
}

.saved-order-item-customization {
  color: #ccc;
  font-size: 0.85rem;
  font-style: italic;
  margin-top: 3px;
}

.saved-order-total {
  color: var(--price-color);
  font-weight: 600;
  text-align: right;
  margin: 10px 0;
  font-size: 1.1rem;
}

.delete-order-btn {
  background: rgba(255, 99, 71, 0.2);
  border-color: rgba(255, 99, 71, 0.5);
  color: rgba(255, 99, 71, 1);
  margin: 0 auto;
  display: block;
}

.delete-order-btn:hover {
  background: rgba(255, 99, 71, 0.8);
  color: white;
}

/* Reglas responsive de tablet consolidadas - ELIMINADAS */
/* La página ahora se adapta naturalmente sin restricciones de dispositivo */

/* Optimized disabled states and selection modes */
.price-button:disabled { cursor: not-allowed; opacity: 0.5; }
.price-button.non-selectable:hover, .price-button:disabled:hover { background: transparent; transform: none; box-shadow: none; }
.price-selection-mode .price-button.non-selectable, .price-selection-mode .price-button:disabled { animation: none; background: transparent; transform: none; }
.price-selection-mode .product-grid .product-card.liquor-card .price-button { background: rgba(0, 247, 255, 0.2); animation: pulseGlow 2s infinite; transform: scale(1.02); }

/* Reglas responsive de tablet y móvil - ELIMINADAS */
/* La página ahora se adapta naturalmente sin restricciones de dispositivo */
  
/* Más reglas responsive móviles - ELIMINADAS */
/* La página ahora se adapta naturalmente sin restricciones de dispositivo */
/* Todas las reglas responsive móviles - ELIMINADAS */
/* La página ahora se adapta naturalmente sin restricciones de dispositivo */

/* Reglas de touch targets para tablets - ELIMINADAS */
/* Los elementos ahora usan sus tamaños naturales sin restricciones de dispositivo */

/* =================================================================
   TOP NAVIGATION - RESPONSIVE FIXED HEIGHT
   ================================================================= */
/* Mobile devices */
@media (max-width: 480px) {
  #top-nav {
    height: var(--top-nav-height-mobile) !important;
    min-height: var(--top-nav-height-mobile) !important;
    max-height: var(--top-nav-height-mobile) !important;
    padding: 0 15px;
  }
  
  body.top-nav-visible {
    padding-top: var(--top-nav-height-mobile) !important;
  }
}

/* Tablets */
@media (min-width: 481px) and (max-width: 1024px) {
  #top-nav {
    height: var(--top-nav-height-tablet) !important;
    min-height: var(--top-nav-height-tablet) !important;
    max-height: var(--top-nav-height-tablet) !important;
    padding: 0 18px;
  }
  
  body.top-nav-visible {
    padding-top: var(--top-nav-height-tablet) !important;
  }
}

/* Desktop */
@media (min-width: 1025px) {
  #top-nav {
    height: var(--top-nav-height-desktop) !important;
    min-height: var(--top-nav-height-desktop) !important;
    max-height: var(--top-nav-height-desktop) !important;
  }
  
  body.top-nav-visible {
    padding-top: var(--top-nav-height-desktop) !important;
  }
}

/* =================================================================
   RESPONSIVE DESIGN - LARGE DESKTOP (min-width: 1200px)
   ================================================================= */
@media (min-width: 1200px) {
  .order-item {
    padding: 12px 0;
    margin-bottom: 12px;
  }
  
  .order-item-name {
    font-size: 1rem;
    margin-bottom: 6px;
  }
  
  .order-item-price {
    font-size: 0.95rem;
  }
  
  .order-item-customization {
    font-size: 0.9rem;
    margin-top: 6px;
  }
  
  .order-total {
    margin-top: 25px;
    padding-top: 12px;
  }
  
  .order-total h4 {
    font-size: 1.3rem;
  }
  
  .order-actions {
    margin-top: 25px;
    gap: 12px;
  }
  
  /* PRODUCT GRID DESKTOP RULES MOVED TO COMPONENTS/PRODUCT-GRID.CSS */
  /* Reglas desktop de .product-grid ahora manejadas por el componente BEM */
  
  /* CATEGORY GRID DESKTOP RULES MOVED TO COMPONENTS/CATEGORY-GRID.CSS */
  /* Reglas desktop de .category-grid ahora manejadas por el componente BEM */
  
  .category-image {
    width: clamp(110px, 13vw, 150px);
    height: clamp(110px, 13vw, 150px);
  }
  
  .product-card {
    min-height: 350px;
    height: auto;
    /* max-height removido para permitir expansión */
  }
  
  .product-card .product-name {
    font-size: 0.975rem;
    height: clamp(1.386rem, 2.07vw + 0.576rem, 1.845rem);
    -webkit-line-clamp: unset;
    line-clamp: unset;
    overflow: visible;
    text-overflow: unset;
    display: block;
  }
  
  .product-card .product-ingredients {
    font-size: 0.9rem;
  }
}

.password-input {
  width: 100%;
  background: rgba(255, 255, 255, 0.1);
  border: 1px solid var(--border-color);
  padding: 10px;
  color: var(--text-color);
  margin: 15px 0;
  font-family: 'Montserrat', sans-serif;
  transition: all var(--transition-time) ease;
}

.password-input:focus {
  outline: none;
  border-color: var(--price-color);
}

.clear-history-btn {
  background: rgba(255, 99, 71, 0.2);
  border-color: rgba(255, 99, 71, 0.5);
  color: rgba(255, 99, 71, 1);
  margin-left: auto;
}

.clear-history-btn:hover {
  background: rgba(255, 99, 71, 0.8);
  color: white;
}

/* =================================================================
   BARRA SUPERIOR GLOBAL
   ================================================================= */
#top-nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  width: 100%;
  height: var(--top-nav-height);
  min-height: var(--top-nav-height);
  max-height: var(--top-nav-height);
  background: var(--top-nav-bg);
  border-bottom: 1px solid rgba(0, 247, 255, 0.3);
  backdrop-filter: blur(10px);
  z-index: 1000;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 0 20px;
  box-shadow: var(--glow-shadow);
  /* Ocultar inicialmente hasta que termine la inicialización */
  opacity: 0;
  transform: translateY(-100%);
  transition: opacity 0.5s ease, transform 0.5s ease;
  /* Prevent content from affecting the navbar size */
  flex-shrink: 0;
  flex-grow: 0;
  overflow: hidden;
}

/* Mostrar la barra superior cuando la app esté lista */
#top-nav.show {
  opacity: 1;
  transform: translateY(0);
}

.nav-left,
.nav-center,
.nav-right {
  display: flex;
  align-items: center;
  flex: 1;
  height: 100%;
  min-height: var(--top-nav-height);
  max-height: var(--top-nav-height);
  overflow: hidden;
}

.nav-center {
  justify-content: center;
}

.nav-right {
  justify-content: flex-end;
}

#nav-title {
  color: var(--accent-color);
  font-size: 1.2rem;
  font-weight: bold;
  text-shadow: 0 0 10px rgba(0, 247, 255, 0.5);
  line-height: 1;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  max-height: 40px;
  display: flex;
  align-items: center;
}

.top-nav-btn {
  background: var(--card-bg);
  border: 2px solid var(--primary-color);
  color: var(--text-color);
  font-size: 1.2rem;
  width: 40px;
  height: 40px;
  min-width: 40px;
  min-height: 40px;
  max-width: 40px;
  max-height: 40px;
  border-radius: 8px;
  cursor: pointer;
  transition: all var(--transition-time) ease;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 5px;
  backdrop-filter: blur(5px);
  flex-shrink: 0;
  flex-grow: 0;
  overflow: hidden;
  line-height: 1;
}

.top-nav-btn:hover, .top-nav-btn.active {
  background-color: transparent;
  transform: scale(1.02);
  border-color: var(--price-color);
  color: var(--price-color);
  box-shadow: 0 0 15px var(--price-color);
}

.top-nav-btn:active {
  transform: scale(0.95);
}

/* Ajustes para el contenido principal */
body {
  padding-top: 0;
  transition: padding-top 0.5s ease;
}

/* Agregar padding cuando la barra superior esté visible */
body.top-nav-visible {
  padding-top: var(--top-nav-height);
}

#app {
  padding-top: 0;
}

/* =================================================================
   NAVIGATION DRAWER & HAMBURGER MENU
   ================================================================= */
.hamburger-btn {
  position: fixed;
  top: 20px; 
  left: calc((100vw - var(--table-width)) / 2 + 20px);
  background: var(--card-bg);
  border: 2px solid var(--primary-color);
  color: var(--text-color);
  font-size: 1.5rem;
  width: 50px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  z-index: 1000;
  transition: all var(--transition-time) ease;
}

.hamburger-btn:hover {
  background-color: var(--primary-color);
  color: var(--background-color);
}

/* Optimized drawer menu */
.drawer-menu { position: fixed; top: 0; left: 0; width: 300px; height: 100vh; background: rgba(0, 0, 0, 0.9); backdrop-filter: blur(10px); z-index: 999; transform: translateX(-100%); transition: transform 0.3s ease-in-out; overflow-y: auto; /* Borde cyan eliminado */ }
.drawer-menu.open { transform: translateX(0); }
.drawer-content { padding: 80px 20px 20px 20px; display: flex; flex-direction: column; gap: 15px; }
.drawer-logo-container { display: flex; justify-content: center; margin-bottom: 10px; }
.drawer-logo { width: 100px; height: auto; object-fit: contain; margin-bottom: 10px; }
.drawer-footer { margin-top: 20px; text-align: center; font-size: 0.9rem; color: var(--primary-color); opacity: 0.8; font-style: italic; }
.drawer-menu .nav-button { width: 100%; text-align: left; padding: 12px 15px; font: 700 1.1rem 'Playfair Display', serif; text-transform: none; transition: all 0.3s ease; border: 1.4px solid rgba(255, 255, 255, 0.2); background: rgba(255, 255, 255, 0.02); border-radius: 5px; /* Bordes y efectos cyan eliminados */ }
.drawer-menu .nav-button:hover, .drawer-menu .nav-button.active { background-color: transparent; transform: scale(1.02); border-color: var(--price-color); color: var(--price-color); box-shadow: 0 0 15px var(--price-color); }
.drawer-overlay { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: rgba(0, 0, 0, 0.5); z-index: 998; opacity: 0; pointer-events: none; transition: opacity 0.3s ease; }
.drawer-overlay.active { opacity: 1; pointer-events: all; }

.title-row {
  background: transparent;
}

.title-row td {
  padding: 0;
  background: transparent;
}

/* =================================================================
   CATEGORY-SPECIFIC STYLES - SISTEMA ESTANDARIZADO
   ================================================================= */

/* Refrescos y Cervezas ahora usan .cols-3 aplicado dinámicamente en JavaScript */

/* Estilos específicos que se mantienen */
.product-table[data-category="refrescos"] th,
.product-table[data-category="cervezas"] th,
.product-table[data-category="refrescos"] td,
.product-table[data-category="cervezas"] td {
  text-align: center;
}

.product-table[data-category="refrescos"] th:first-child,
.product-table[data-category="cervezas"] th:first-child,
.product-table[data-category="refrescos"] td.product-name,
.product-table[data-category="cervezas"] td.product-name {
  text-align: left;
  padding-left: 15px;
  width: 45%;
}

/* Anchos de columnas ahora controlados por .cols-3 */
.modal-content[data-category="refrescos"], 
.modal-content[data-category="cervezas"] { 
  width: 33.6%; 
  max-width: 336px; 
}
/* Category-specific tablet styles consolidated into main 768px media query above */
/* Category-specific styles consolidated into main 480px media query above */
.exclusive-option-group { background: rgba(0, 247, 255, 0.05); border: 1px solid rgba(0, 247, 255, 0.2); border-radius: 8px; padding: 15px; margin: 15px 0; display: flex; flex-direction: column; gap: 10px; }
.exclusive-option-group h4 { color: var(--primary-color); margin: 0 0 10px 0; font-size: 1rem; text-align: center; }
.jager-option-container { display: flex; align-items: center; padding: 10px; background: rgba(0, 0, 0, 0.3); border-radius: 5px; transition: background-color 0.3s ease; cursor: pointer; font-size: 1rem; }
.jager-option-container:hover { background: rgba(0, 247, 255, 0.1); }
.jager-option-container.selected { background: rgba(0, 247, 255, 0.2); transform: translateY(-2px); box-shadow: 0 2px 8px rgba(0, 247, 255, 0.3); }
.jager-radio { margin-right: 10px; accent-color: var(--primary-color); }
.jager-label { font-weight: 500; color: var(--text-color); }

/* =================================================================
   INLINE STYLE REFACTORING - UTILITY CLASSES
   ================================================================= */

/* Screen display utilities */
.screen-hidden {
  display: none !important;
}

.screen-visible {
  display: flex !important;
  opacity: 1;
  visibility: visible;
}

.screen-flex {
  display: flex !important;
}

.screen-block {
  display: block !important;
}

/* Hamburger menu visibility */
.hamburger-hidden {
  display: none;
}

.hamburger-visible {
  display: block;
}

/* Sidebar and container display states */
.sidebar-hidden {
  display: none !important;
}

.sidebar-visible {
  display: block !important;
}

.content-hidden {
  display: none;
}

.content-visible {
  display: block;
}

/* Input container states */
.input-container-hidden {
  display: none;
}

.input-container-visible {
  display: block;
}

/* Choice container states */
.choice-hidden {
  display: none;
}

.choice-visible {
  display: block;
}

/* Body overflow control */
.body-no-scroll {
  overflow: hidden;
}

.body-scroll {
  overflow: auto;
}

/* Error display utilities */
.error-red {
  color: red;
}

.error-visible {
  display: block;
}

.error-hidden {
  display: none;
}

/* Modal display states */
.modal-flex {
  display: flex;
}

.modal-hidden {
  display: none;
}

/* Opacity utilities */
.opacity-0 {
  opacity: 0;
}

.opacity-1 {
  opacity: 1;
}

/* Left positioning utilities */
.left-0 {
  left: 0;
}

.left-auto {
  left: auto;
}

/* Product image size utilities */
.product-image-small {
  width: 40px !important;
  height: 40px !important;
}

.product-image-large {
  width: 70px !important;
  height: 70px !important;
}

/* Height and min-height utilities */
.height-auto {
  height: auto !important;
}

.min-height-auto {
  min-height: auto !important;
}

/* Modal subtitle styling */
.modal-subtitle {
  font-size: 0.85em;
  font-weight: normal;
  color: var(--text-color);
}

/* Page title visibility */
.page-title-hidden {
  display: none;
}

.page-title-visible {
  display: block;
}

/* Custom Scrollbar Styles */
/* Webkit browsers (Chrome, Safari, Edge) */
::-webkit-scrollbar {
  width: 12px;
  height: 12px;
}

::-webkit-scrollbar-track {
  background: rgba(0, 0, 0, 0.3);
  border-radius: 6px;
}

::-webkit-scrollbar-thumb {
  background: var(--card-bg);
  border-radius: 6px;
  border: 2px solid rgba(0, 0, 0, 0.3);
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(0, 247, 255, 0.3);
  box-shadow: var(--glow-shadow);
}

::-webkit-scrollbar-corner {
  background: rgba(0, 0, 0, 0.3);
}

/* Firefox */
* {
  scrollbar-width: thin;
  scrollbar-color: var(--card-bg) rgba(0, 0, 0, 0.3);
}

/* Implementación móvil específica - ELIMINADA */
/* La página ahora se adapta naturalmente sin restricciones de dispositivo */

/* =================================================================
   GRID ENHANCED - PLAN DE ESTANDARIZACIÓN
   ================================================================= */

/* Variables CSS para centralizar tamaños y espacios */
:root {
  --card-min: 260px;
  --grid-gap: clamp(12px, 2vw, 20px);
  --grid-pad: clamp(12px, 2vw, 20px);
  --slot-gap: clamp(6px, 1.2cqw, 12px);
  --price-gap: clamp(6px, 1.2cqw, 10px);
  --media-slot: auto;
  --name-slot: auto;
  --ing-slot: auto;
  --price-slot: auto;
}

/* 1. Activación segura - Solo cuando body tiene clase grid-enhanced */
/* ENHANCED PRODUCT GRID RULES MOVED TO COMPONENTS/PRODUCT-GRID.CSS */
/* Reglas de body.grid-enhanced .product-grid ahora manejadas por el componente BEM */

/* ENHANCED CATEGORY GRID RULES MOVED TO COMPONENTS/CATEGORY-GRID.CSS */
/* Reglas de body.grid-enhanced .category-grid ahora manejadas por el componente BEM */

/* 2. Estructura base de las cards con grid interno */
body.grid-enhanced .product-card {
  display: grid;
  grid-template-rows:
    var(--media-slot)
    var(--name-slot)
    var(--ing-slot)
    var(--price-slot);
  row-gap: var(--slot-gap);
}

/* 3. Ajustes por tipo de grid */
/* Tipo 2: Refrescos, Cervezas - Sin ingredientes */
body.grid-enhanced .product-grid.grid-type-2 .product-card {
  --ing-slot: 0px;
}

body.grid-enhanced .product-grid.grid-type-2 .product-ingredients {
  display: none;
}

/* Tipo 3: Subcategorías de Licores */
body.grid-enhanced .product-card.liquor-card {
  --media-slot: minmax(clamp(140px, 32cqw, 220px), auto);
  --price-gap: clamp(4px, 1cqw, 8px);
}

body.grid-enhanced .product-card.liquor-card .product-prices {
  display: flex;
  flex-direction: column;
  gap: var(--price-gap);
}

/* Tipo 4: Categorías de licores */
body.grid-enhanced .category-grid.grid-type-4 .category-name {
  font-size: clamp(0.95rem, 1.8vw, 1.2rem);
}

/* 4. Tipografía fluida */
body.grid-enhanced .product-card .product-name {
  font-size: clamp(0.9rem, 2.2cqw, 1.05rem);
  line-height: 1.2;
}

body.grid-enhanced .product-card .product-ingredients {
  font-size: clamp(0.8rem, 1.9cqw, 0.95rem);
  line-height: 1.3;
}

/* 5. Espaciado y ritmo visual */
body.grid-enhanced .product-card {
  --slot-gap: clamp(6px, 1.2cqw, 12px);
  --price-gap: clamp(6px, 1.2cqw, 10px);
}

/* ================================================================= 
   GRID ENHANCED – Fixes críticos y pulido
   ================================================================= */
/* Container queries support - aplicar solo en contexto grid-enhanced */
@supports (container-type: inline-size) {
  body.grid-enhanced .product-card {
    container-type: inline-size;
  }
}

/* Mapeo explícito a filas: evita depender del DOM y de order (flex) */
body.grid-enhanced .product-card .product-media        { grid-row: 1; margin: 0; }
body.grid-enhanced .product-card .product-name         { grid-row: 2; margin: 0; }
body.grid-enhanced .product-card .product-ingredients  { grid-row: 3; margin: 0; }
body.grid-enhanced .product-card .product-prices       { grid-row: 4; margin: 0; }

/* Unificar gaps de precios en todos los tipos (no solo licores) */
body.grid-enhanced .product-card .product-prices { gap: var(--price-gap); }

/* Microcontracción armónica en cards angostos */
@supports (container-type: inline-size) {
  @container (max-width: 340px) {
    body.grid-enhanced .product-card {
      --slot-gap:   clamp(4px, 1cqw, 8px);
      --name-slot:  clamp(24px, 6cqw, 36px);
      --ing-slot:   clamp(56px, 14cqw, 96px);
      --media-slot: minmax(clamp(100px, 26cqw, 150px), auto);
    }
  }
}

/* =================================================================
   CONFIGURACIÓN MÓVIL Y TABLET - SISTEMA RESPONSIVO AVANZADO
   ================================================================= */

/* 📱 MODO GRID - TELÉFONO EN VERTICAL (PORTRAIT) */
/* REGLAS GRID MÓVILES ELIMINADAS - Ahora manejadas por mobile.css */

/* REGLAS TABLA MÓVILES ELIMINADAS - Ahora manejadas por mobile.css */

/* 📐 MODO HORIZONTAL (LANDSCAPE) - MÓVILES Y TABLETS */
@media (orientation: landscape) and (min-width: 640px) {
  /* Replicar comportamiento de ordenadores */
  .content-container-flex {
    flex-direction: row;
    gap: clamp(12px, 2.5vw, 20px);
    max-width: 1400px;
  }
  
  #content-container {
    flex: 1 1 auto;
    width: auto;
    max-width: none;
    padding: 0 clamp(12px, 2.5vw, 20px);
  }
  
  /* 3 columnas de Grid en lugar de 2 */
  .product-grid,
  .category-grid {
    grid-template-columns: repeat(3, 1fr);
    gap: clamp(15px, 2.5vw, 25px);
    padding: clamp(15px, 2.5vw, 25px);
    width: 100%;
  }
  
  /* Sidebar como parte integral del layout - NO superpuesto */
  body.order-mode-active .content-container-flex {
    gap: clamp(15px, 2vw, 20px);
  }
  
  body.order-mode-active #order-sidebar {
    position: relative !important;
    flex: 0 0 280px;
    min-width: 250px;
    max-width: 320px;
    height: auto;
    max-height: calc(100vh - 60px);
    margin-top: 0;
    display: block;
    /* Sidebar scrollable junto con la página - NO fijo */
    position: static !important;
  }
  
  /* Contenido se ajusta al espacio restante */
  body.order-mode-active #content-container {
    flex: 1 1 auto;
    min-width: 0;
    /* Separación mínima entre contenido y sidebar */
    margin-right: clamp(10px, 1.5vw, 15px);
  }
  
  /* Tipografía optimizada para landscape */
  .product-card .product-name,
  .category-card .category-name {
    font-size: clamp(14px, 2vw, 18px);
  }
  
  .product-card .product-ingredients {
    font-size: clamp(12px, 1.8vw, 16px);
  }
  
  .price-button {
    font-size: clamp(12px, 1.8vw, 16px);
    padding: clamp(6px, 1.2vw, 10px) clamp(8px, 1.8vw, 15px);
  }
}

/* 📱 TABLETS EN MODO PORTRAIT - MÓVIL VERTICAL (768px - 1024px) */
/* REGLAS TABLET PORTRAIT ELIMINADAS - Ahora manejadas por tablet.css */

/* REGLAS TABLET LANDSCAPE ELIMINADAS - Ahora manejadas por tablet.css */

/* REGLAS TABLET ESPECÍFICAS ELIMINADAS - Ahora manejadas por tablet.css */

/* Desktop (min-width: 1025px) - Restaurar comportamiento original */
@media (min-width: 1025px) {
  .content-container-flex {
    flex-direction: row;
    gap: 1rem;
  }
  
  body:not(.order-mode-active) .content-container-flex {
    justify-content: center;
  }
  
  body:not(.order-mode-active) #content-container {
    flex: 0 1 auto;
    width: 72%;
    max-width: 1120px;
  }
  
  /* CATEGORY GRID FINAL DESKTOP RULES MOVED TO COMPONENTS/CATEGORY-GRID.CSS */
  /* Reglas finales desktop de .category-grid ahora manejadas por el componente BEM */
  
  /* PRODUCT GRID FINAL DESKTOP RULES MOVED TO COMPONENTS/PRODUCT-GRID.CSS */
  /* Reglas finales desktop de .product-grid ahora manejadas por el componente BEM */
  
  .product-card .product-name,
  .category-card .category-name {
    font-size: clamp(14px, 2vw, 18px);
  }
  
  .product-card .product-ingredients {
    font-size: clamp(12px, 1.8vw, 16px);
  }
  
  .price-button {
    font-size: clamp(12px, 1.8vw, 16px);
    padding: clamp(8px, 1.5vw, 12px) clamp(12px, 2vw, 18px);
  }
}