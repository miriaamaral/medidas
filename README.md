# 📏 Estudo de Medidas CSS: px, %, vw/vh e rem ✨

E aí, meu 🐙! Este projeto é um laboratório de estudos para entender e visualizar na prática as **principais unidades de medida em CSS**. O objetivo é demonstrar a diferença entre medidas **fixas (`px`)** e **relativas (`%, vw, rem`)** e como elas se comportam na construção de layouts responsivos.

É um mergulho nas unidades que definem a estrutura e a acessibilidade da web! Vem explorar! 😉

---

## 🎥 Veja as Medidas em Ação!

Que tal dar uma olhada na responsividade de cada medida ao vivo?
[Medidas](https://miriaamaral.github.io/medidas/)


<img width="1366" height="645" alt="medidas photo" src="https://github.com/user-attachments/assets/4714c30f-df44-4af3-b8d4-99766f0ad365" />

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

Vamos juntos construir o futuro da tecnologia! ✨

---