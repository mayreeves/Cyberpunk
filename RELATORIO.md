# Mini Relatório - Cena 3D Cyberpunk Procedural

## Integrantes do Grupo
- [Seu Nome] (Individual)

## Formas e Equações Matemáticas Utilizadas

### 1. Terreno Procedural Cyberpunk
- **Forma**: PlaneGeometry (superfície plana com 80x80 segmentos)
- **Equações**: 
  - `z = sin(x * 0.3) * cos(y * 0.3) * 2 + sin(x * 0.1) * 1.5`
  - Combinação de funções seno e cosseno para criar ondulações orgânicas no terreno
  - Grid neon gerado proceduralmente via Canvas API

### 2. Núcleo Flutuante (Icosaedro)
- **Forma**: IcosahedronGeometry (geometria de 20 faces)
- **Equações**:
  - `rotation.x = time * 0.5`
  - `rotation.y = time * 0.8`
  - `position.y = 4 + sin(time * 2) * 0.5`
  - Rotação dupla e levitação oscilatória usando função seno

### 3. Sistema de Partículas
- **Forma**: BufferGeometry com Points (300 partículas)
- **Equações**:
  - Posição inicial aleatória: `(random - 0.5) * 40`
  - Distribuição espacial uniforme no volume da cena
  - Cor ciano (#00ffcc) para estética cyberpunk

### 4. Iluminação Dinâmica Orbital
- **Forma**: PointLights (2 luzes coloridas)
- **Equações**:
  - Luz 1 (Ciano): `x = sin(time * 1.5) * 8`, `z = cos(time * 1.5) * 8`
  - Luz 2 (Magenta): `x = cos(time * 1.2) * -8`, `z = sin(time * 1.2) * -8`
  - Movimento orbital circular usando seno e cosseno

### 5. Controle de Câmera via Mouse
- **Equações**:
  - `camera.position.x += (sin(mouseX * 5) * 12 - camera.position.x) * 0.05`
  - `camera.position.y += (5 + mouseY * 10 - camera.position.y) * 0.05`
  - Interpolação linear (lerp) para movimento suave

## Otimizações para Desempenho

### 1. Textura Procedural via Canvas
- Grade neon gerada dinamicamente usando HTML5 Canvas
- Evita carregamento de imagens externas
- Textura repetida 20x20 usando RepeatWrapping
- Reduz tamanho do arquivo para ~6 KB

### 2. BufferGeometry para Partículas
- Uso de BufferGeometry com Float32Array
- 300 partículas renderizadas em um único draw call
- Atributos de posição armazenados eficientemente

### 3. Pixel Ratio Limitado
- `renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2))`
- Limita o pixel ratio para máximo de 2x
- Evita sobrecarga em telas de alta densidade (4K, Retina)

### 4. Power Preference High-Performance
- `powerPreference: "high-performance"` no WebGLRenderer
- Prioriza GPU dedicada sobre integrada
- Melhor utilização de hardware disponível

### 5. Névoa Exponencial Otimizada
- `FogExp2` em vez de `Fog` regular
- Cálculo mais eficiente para efeito de profundidade
- Cor escura (#050515) integra com tema cyberpunk

### 6. Iluminação Minimalista
- Apenas 2 PointLights + 1 AmbientLight
- Distância de iluminação limitada (30 unidades)
- Intensidade balanceada para performance

### 7. Geometria Otimizada
- Terreno com 80x80 segmentos (6400 vértices)
- Icosaedro com detalhe nível 1 (12 vértices)
- Sem geometrias desnecessárias ou excessivas

## Resultados
- **Meta de FPS**: 60 FPS (estável)
- **Objetos na cena**: 302 (1 terreno + 1 núcleo + 300 partículas)
- **Tamanho do arquivo**: ~6 KB (extremamente leve)
- **Carregamento**: Instantâneo (textura gerada em tempo real)
- **Estilo**: Cyberpunk com cores neon (ciano #00ffcc e magenta #ff007f)

## Como Executar
1. Abra o arquivo `index.html` em qualquer navegador moderno
2. Mova o mouse para controlar a câmera
3. A cena 3D será renderizada automaticamente a 60 FPS
4. Não é necessário servidor web (funciona localmente)
