# Cena 3D Cyberpunk Procedural - Three.js

Projeto de cena 3D interativa utilizando Three.js com formas geométricas animadas por fórmulas matemáticas no estilo cyberpunk.

## 📁 Arquivos do Projeto

- `index.html` - Código-fonte principal da cena 3D
- `RELATORIO.md` - Mini relatório detalhado do projeto
- `README.md` - Este arquivo com instruções

## 🚀 Como Executar

### Opção 1: Servidor Local (Recomendado)
```bash
# Navegue até a pasta do projeto
cd "c:/Users/aluno/Documents/trabalho do edjalma/projeto blanca"

# Inicie um servidor Python
python -m http.server 8000

# Abra no navegador:
# http://localhost:8000
```

### Opção 2: Abrir Diretamente
Basta abrir o arquivo `index.html` diretamente no navegador (duplo clique).

## 🎨 Características da Cena

### Formas Geométricas
- **Terreno procedural cyberpunk**: Superfície com ondulações usando sin/cos e textura neon
- **Núcleo flutuante (Icosaedro)**: Geometria de 20 faces com rotação e levitação
- **300 Partículas**: Sistema de partículas ciano flutuando no espaço

### Texturas Procedurais
Textura neon gerada via código usando HTML5 Canvas:
- Grade cyberpunk com linhas ciano (#00ffcc) e magenta (#ff007f)
- Fundo escuro (#0a0a1a)
- Repetida 20x20 para cobrir o terreno

### Equações Matemáticas
- `Math.sin()` e `Math.cos()` para movimentos oscilatórios
- Funções trigonométricas para órbitas de luzes
- Interpolação linear (lerp) para câmera suave
- Terreno: `z = sin(x * 0.3) * cos(y * 0.3) * 2 + sin(x * 0.1) * 1.5`

### Controles
- **Mouse**: Mova o cursor para controlar a câmera
- A câmera segue suavemente a posição do mouse

## 📊 Performance

- **Meta**: 60 FPS (estável)
- **Objetos**: 302 objetos renderizados
- **Tamanho**: ~6 KB (extremamente leve)
- **Texturas**: Geradas em tempo real (sem download)
- **Estilo**: Cyberpunk com cores neon

## 📹 Como Gravar o Vídeo/GIF

### Usando ferramentas gratuitas:

1. **OBS Studio** (Windows/Mac/Linux)
   - Download: https://obsproject.com/
   - Selecione "Fonte de Janela" e escolha o navegador
   - Grave por 30-60 segundos
   - Exporte como MP4 ou GIF

2. **Loom** (Windows/Mac)
   - Download: https://www.loom.com/
   - Grave a tela do navegador
   - Exporte como GIF ou MP4

3. **ShareX** (Windows)
   - Download: https://getsharex.com/
   - Use o gravador de tela
   - Exporte como GIF

### Dicas para Gravação:
- Grave por 30-60 segundos
- Mostre a cena rodando suavemente
- Movimente o mouse para demonstrar o controle de câmera
- Destaque as luzes orbitais e o núcleo rotativo

## 📝 Entrega na Sala de Aula

### Checklist:
- [ ] Código-fonte (index.html)
- [ ] Vídeo/GIF da animação (30-60 segundos)
- [ ] Mini relatório (RELATORIO.md)

### Informações para o Relatório:
Edite o arquivo `RELATORIO.md` e adicione:
- Seu nome completo
- Nomes dos outros integrantes (se for em grupo até 3 pessoas)

## 🛠️ Tecnologias Utilizadas

- **Three.js r128** - Biblioteca 3D via CDN
- **HTML5 Canvas** - Geração de textura procedural neon
- **JavaScript ES6+** - Lógica da aplicação
- **Math.sin/cos** - Equações matemáticas para animação

## 📌 Notas Importantes

- O código é 100% contido em um único arquivo HTML
- Não requer instalação de dependências
- Funciona offline (apenas o primeiro carregamento do Three.js via CDN)
- Otimizado para rodar em 60 FPS na maioria dos computadores
- Estilo cyberpunk com paleta de cores neon (ciano e magenta)

## 🎯 Requisitos Atendidos

✅ Cena 3D com Three.js  
✅ Formas geométricas (terreno, icosaedro, partículas)  
✅ Fórmulas matemáticas (Math.sin, Math.cos)  
✅ Cores e texturas geradas via código  
✅ Desempenho otimizado (meta 60 FPS)  
✅ Código enxuto e leve (~6 KB)  
✅ Relatório detalhado incluído  
✅ Controle interativo via mouse  

---

**Desenvolvido para disciplina de Computação Gráfica / 3D**
