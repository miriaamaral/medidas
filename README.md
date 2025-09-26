# 📏 Estudo de Medidas CSS: px, %, vw/vh e rem ✨

E aí, meu 🐙! Este projeto é um laboratório de estudos para entender e visualizar na prática as **principais unidades de medida em CSS**. O objetivo é demonstrar a diferença entre medidas **fixas (`px`)** e **relativas (`%, vw, rem`)** e como elas se comportam na construção de layouts responsivos.

É um mergulho nas unidades que definem a estrutura e a acessibilidade da web! Vem explorar! 😉

---

## 🎥 Veja as Medidas em Ação!

Que tal dar uma olhada na responsividade de cada medida ao vivo?
[Medidas (Seu Deploy)](https://miriaamaral.github.io/medidas/)

<img width="1366" height="640" alt="Visão da medida fixa px" src="https://via.placeholder.com/600x300.png?text=IMAGEM+DA+CAIXA+COM+PX" />
<img width="1366" height="643" alt="Visão da medida relativa %" src="https://via.placeholder.com/600x300.png?text=IMAGEM+DA+CAIXA+COM+%25" />
<img width="1366" height="637" alt="Visão da medida vw/vh" src="https://via.placeholder.com/600x300.png?text=IMAGEM+DA+CAIXA+COM+VW+e+VH" />
<img width="1366" height="641" alt="Visão da medida rem" src="https://via.placeholder.com/600x300.png?text=IMAGEM+DA+CAIXA+COM+REM" />

---

### 🎨 Visualizando as Medidas e Suas Regras

Aqui estão os conceitos e a aplicação de cada unidade no código:

| Unidade | Tipo | Regra de Uso e Comportamento |
| :---: | :---: | :--- |
| **`px`** | Fixa | Não muda com o zoom ou tamanho da tela. Ótima para espaçamentos e bordas, onde a consistência visual é importante. |
| **`%`** | Relativa | A largura e altura se ajustam de acordo com o **elemento pai**. Torna o layout responsivo, mas depende do container. |
| **`vw` / `vh`** | Relativa | Proporcionais à **tela inteira (viewport)**. 1vw = 1% da largura da tela. Ideais para elementos que precisam sempre ocupar uma porcentagem da tela. |
| **`rem`** | Relativa | A dimensão é relativa ao tamanho da **fonte raiz (`<html>`)**. Ideal para acessibilidade, pois o design se adapta se o usuário alterar o tamanho base da fonte. |

---

### 🛠 CSS vs. SASS/SCSS: Onde as Medidas se Destacam

Você usou o SASS/SCSS (pré-processador) para escrever o CSS, e isso é ótimo para organização, mas é importante lembrar:

* **Diferença de Renderização de Medidas:** Não há diferença! As medidas (`px`, `rem`, `vw`, etc.) são parte do CSS padrão. O **SASS (ou SCSS)** é apenas um intermediário; ele pega seu código organizado e o **compila** para o CSS puro, que é o que o navegador realmente lê.
* **Boas Práticas de Medida com SASS:** O SASS brilha ao usar medidas relativas. Você pode definir uma variável (`$font-base: 1rem;`) e usá-la em todo o projeto. Se precisar mudar a escala do layout, você altera **apenas a variável** e todos os elementos que usam `rem` escalam automaticamente, sem tocar no CSS individual!

---

### ⚙️ As Medidas no Código

As diferentes medidas são aplicadas nas caixas do arquivo `style.scss`, que usa pré-processador SASS para estilos mais organizados.

#### **HTML**
A estrutura HTML é simples e direta.
```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Medidas</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div class="caixa box-fixa">Caixa com o px - Medida Fixa</div>
    <div class="caixa box-porcentagem">Caixa com % - Medida Relativa</div>
    <div class="caixa box-viewport">Caixa com vw e vh - Medida Relativa</div>
    <div class="caixa box-rem">Caixa com rem - Medida Relativa</div>
</body>
</html>

#### **SCSS/SASS**
A estrutura SCSS mantive as anotações do projeto para ficar mais facil absorver as aplicações: 
```// Anotações sobre Medidas no SCSS/SASS

// Reset global para remover espaçamentos padrão do navegador
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box; // Garante que padding e border não alterem o tamanho total do elemento
}

```// Estilo base para todas as caixas
.caixa { // formas de selecionar as tags => .nomedaclass | selecionar ID => #nomedAID
  background-color: gold;
  border: solid 3px chocolate;
  text-align: center;
  font-size: 1rem; // Definindo o tamanho da fonte para 1rem como base
  padding: 1rem; // Adicionando padding com unidade relativa
}

```.box-fixa {
  // PX: Medida fixa.
  // 1 pixel = 1 ponto na tela. O tamanho não muda com o zoom ou tamanho da tela.
  // Ótima para espaçamentos e bordas, onde a consistência visual é importante.
  width: 300px;
  height: 100px;
}

```.box-porcentagem {
  // %: Medida relativa ao elemento pai.
  // A largura é 80% do elemento que a contém. Se o pai mudar, ela também muda.
  // Ideal para criar layouts que se ajustam, como em um design responsivo.
  width: 80%;
  height: 100px; // A altura pode ser fixa, se necessário, para manter a proporção
}

```.box-viewport {
  // VW (Viewport Width) e VH (Viewport Height): Medidas relativas à tela inteira.
  // 1vw = 1% da largura da tela. 1vh = 1% da altura da tela.
  // Perfeitas para elementos que precisam sempre ocupar uma porcentagem específica da tela.
  width: 50vw;
  height: 30vh;
}

```.box-rem {
  // REM (Root Em): Medida relativa ao tamanho da fonte do elemento raiz (<html>).
  // Por padrão, 1rem = 16px. Se você mudar o font-size do <html>, todos os rems mudam.
  // Excelente para acessibilidade, pois o design se adapta se o usuário alterar o tamanho da fonte.
  width: 32rem;
  height: 14.4rem;
  // Anotações Adicionais sobre REM e responsividade:
  // Essa abordagem é muito usada em design responsivo para que o layout escale com a fonte.
  // Por exemplo, você pode usar media queries para mudar o font-size do <html> em telas menores.
}

### *⚙️ Como Rodar o Projeto (Localmente):*

1.  *Clone este repositório:*
    bash
    git clone [https://github.com/miriaamaral/medidas.git](https://github.com/miriaamaral/medidas.git)

2.  *Entre na pasta do projeto:*
    bash
    cd medidas

3.  *Abra o arquivo index.html no seu navegador.*
    *Se você usou SASS, lembre-se de rodar o comando de compilação (ex: npm run sass:watch se tiver configurado) para garantir que o style.css esteja atualizado antes de abrir o arquivo.

---

### **Conecte-se Comigo! 👋**

Gostou do projeto com anotações ou quer trocar uma ideia sobre medidas no Frontend? Ficarei super feliz!

[![LinkedIn Badge](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/miriaamaralcs) [![GitHub Badge](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/miriaamaral) [![Discord Badge](https://img.shields.io/badge/Discord-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.com/channels/miriaamaralcustodiosantos)
* **Plataforma de Estudos (DIO):** [https://www.dio.me/sign-up?ref=6F1F401485F9459BA6AC879FEA95D1B5](https://www.dio.me/sign-up?ref=6F1F401485F9459BA6AC879FEA95D1B5)

Vamos juntos construir o futuro da tecnologia! ✨

---