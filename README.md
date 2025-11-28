Resumo do Projeto
1. O Conceito (Sonificação de Dados)
O objetivo foi criar uma aplicação web interativa que traduz dados visuais (tamanho e temperatura de estrelas) em experiência sonora e auditiva. O projeto une Visualização de Dados, Computação Gráfica 3D e Síntese de Áudio Digital.

2. Stack Tecnológica
Linguagem: JavaScript (ES6 Modules).

Renderização 3D: Three.js (WebGL).

Áudio: Tone.js (Web Audio API wrapper).

Estilização: CSS3 (Glassmorphism & Responsividade).

Pós-Processamento: Three.js EffectComposer (Unreal Bloom).

3. Etapas do Desenvolvimento
Fase 1: Arquitetura e MVP (Mínimo Produto Viável)
Desafio: Configurar um ambiente 3D funcional sem build tools complexas (Webpack/Vite) para prototipagem rápida.

Solução: Uso de importmaps via CDN e estruturação em arquivo único (index.html) para evitar erros de CORS e facilitar o deploy.

Lógica Base: Criação de uma cena com câmera, renderizador e objetos 3D (esferas) posicionados aleatoriamente em um espaço 3D (eixos X, Y, Z).

Fase 2: Lógica de Sonificação (Data Mapping)
Implementamos a regra de conversão de dados visuais para sonoros:

Temperatura (Cor):

Estrelas Vermelhas (Frias) → Frequências Graves (~100Hz).

Estrelas Azuis (Quentes) → Frequências Agudas (~1000Hz).

Tamanho (Raio):

Estrelas Maiores → Maior sustentação da nota (Duration).

Motor de Áudio: Uso do PolySynth (Sintetizador Polifônico) do Tone.js para permitir que múltiplas estrelas toquem simultaneamente sem cortar o som uma da outra.

Fase 3: Refinamento Visual (O "Glow Up")
Transformamos esferas simples em corpos celestes brilhantes.

Bloom Effect: Implementação de Pós-Processamento (UnrealBloomPass) para criar o brilho neon intenso.

Materiais: Mudança de MeshStandardMaterial (dependente de luz) para MeshBasicMaterial (cor pura), maximizando o efeito do Bloom.

Ambiente: Criação de um sistema de partículas (BufferGeometry) com 3.000 pontos para simular poeira estelar ao fundo, gerando profundidade.

UI/UX: Interface flutuante com efeito de vidro fosco e fontes futuristas (Rajdhani) para imersão sci-fi.

4. Destaques do Código (Pontos Fortes)
Raycaster: Uso de matemática vetorial para detectar cliques do mouse em objetos 3D no espaço.

Interatividade: O sistema exige interação do usuário (clique no botão "Iniciar") para respeitar as políticas de Autoplay dos navegadores modernos.

Performance: Uso de instâncias leves e geometria otimizada para rodar suavemente no navegador.

O que isso demonstra sobre você como dev?
Fullstack Criativo: Sabe manipular o DOM (HTML/CSS) e o Canvas (WebGL).

Lógica Matemática: Entende coordenadas 3D e mapeamento linear de valores (física → som).

Resolução de Problemas: Contornou problemas de importação de módulos e políticas de áudio do browser.


