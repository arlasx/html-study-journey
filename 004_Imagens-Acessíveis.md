# HTML

## Imagens Acessíveis

### `alt`

- **Atributo utilizado para indicar um texto alternativo para uma imagem;**

  ```html
  <img src="imagem.png" alt="Descrição da imagem">
  ```

  - **O seu valor deve conter uma descrição da imagem, da forma mais detalhada possível;**

- **O seu valor é lido por:**

  1. **Leitores de tela;**
  2. **Navegadores (quando a imagem não é carregada);**
  3. **Motores de busca;**



#### Casos de uso

##### 1)

- **Imagem informativa:**

  ```html
  <img 
       src="grafico-vendas.png"
       alt="Gráfico de barras mostrando aumento de vendas de 2024 para 2025"
  >
  ```

  - **Se a imagem transmite uma informação que não está no texto ao redor, devemos descrevê-la de forma clara e curta (devemos descrever o que é e o que importa na imagem);**

  

##### 2)

- **Imagem funcional:**

  - **Quando a imagem executa uma ação (está dentro de um link ou funciona como um botão, por exemplo), o `alt` descreve a função (ou ação que ele executa), não a aparência (a imagem em si)**

    ```html
    <a href="/carrinho">
      <img 
           src="icone-carrinho.svg" 
           alt="Ir para o carrinho"
       >
    </a>
    ```



##### 3)

- **Imagem decorativa:**

  - **A imagem não adiciona informação:**

    ```html
    <img src="detalhe.png" alt="">
    ```

    - **O `alt` vazio indica ao leitor de tela para ignorar aquela imagem (evitando poluição sonora para o usuário);**

  - **O que não fazer:**

    ```html
    <img src="detalhe.png" alt="imagem linha azul decorativa">
    ```

    - **Isso só polui a navegação;**

- **Quando usar o `alt=""`:**

  - **Fundo decorativo;**

  - **Ícone repetido ao lado de texto já explicativo;**

  - **Elemento visual sem significado;**

  - **Separador gráfico;**

  - **Detalhe estético;**

    - **Exemplo:**

      ```html
      <img src="linha-divisoria.png" alt="">
      ```

- **Quando não usar `alt=""`:**

  - **Quando a imagem:**
    1. **Contém informação;**
    2. **Representa conteúdo;**
    3. **É um botão ou link;**
    4. **Mostra um produto;**
    5. **Tem texto importante;**
    6. **É um gráfico;**
    7. **É um logo;**



##### 4)

- **Logo da empresa:**

  - **Logo informativo:**

    ```html
    <img 
         src="logo.png" 
         alt="Logo da empresa empresa X"
     >
    ```

  - **Se o logo também for um link:**

    ```html
    <img 
         src="logo.png" 
         alt="Página inicial da empresa X"
     >
    ```



##### 5)

- **Imagem com texto dentro:**

  ```html
  <img 
       src="banner.png"
       alt="Promoção: 50% de desconto em cursos de programação"
  >
  ```

  - **Deve-se evitar esse tipo de imagem, mas em caso que não há alternativas, devemos repetir o texto tido como importante;**
    - **Por exemplo, temos a imagem de um banner de promoção, o texto da promoção deve estar no `alt`;**



##### 6)

- **Gráficos, diagramas e infográficos:**

  ```html
  <img 
       src="grafico.png"
       alt="Gráfico comparando consumo de energia por setor"
  >
  <p>O setor industrial lidera o consumo com 45%...</p>
  ```

  - **O que fazer:**
    - **Usar o `alt` para resumo;**
    - **Usar um texto próximo para uma explicação mais detalhada;**



##### 7)

- **Imagens de pessoas:**

  ```html
  <img 
       src="pessoa.jpg"
       alt="Mulher sorrindo usando notebook em um escritório"
  >
  ```

  - **Devemos descrever só o que é relevante;**
  - **OBS.:**
    - **Não devemos inventar emoções;**
    - **Não devemos descrever aparência desnecessária;**



##### 8)

- **Imagens de produtos (e-commerce):**

  ```html
  <img 
       src="tenis.jpg"
       alt="Tênis esportivo preto com solado branco, vista lateral"
  >
  ```

  - **Devemos ser objetivos (uma descrição física do objeto);**



##### 9)

- **Ícones (com ou seu texto):**

  - **Se já houver texto visível:**

    ```html
    <img src="icone-email.svg" alt="">
    <span>Email</span>
    ```

  - **Se o ícone estiver sozinho:**

    ```html
    <img src="icone-email.svg" alt="Enviar email">
    ```

    

#### Erros

##### 1)

- **Usar: "Imagem de"...**

  ```scss
  alt="Imagem de um carro" ❌
  alt="Carro vermelho estacionado" ✅
  ```

  - **O leitor de tela já indica que se trata de uma imagem;**



##### 2)

- **Usar palavras-chave forçadas (SEO spam):**

  ```scss
  alt="curso html css javascript barato online" ❌
  ```



##### 3)

- **Deixar sem `alt`:**

  ```scss
  alt="..." <!-- Imagem relevante -->
  alt="" <!-- Imagem decorativa -->
  ```




#### Dicas

1. **Ser conciso:** 
   - **Tentar não passar de 125 caracteres;**
   - **Se a explicação for muito longa, usar o texto da página para explicar e um `alt` resumido;**
2. **Se atentar ao contexto:** 
   - **A mesma foto de uma xícara de café pode ter `alt="Xícara de café preto"` em um blog de culinária, ou `alt=""` se for apenas um detalhe decorativo num site de contabilidade;**



##### `figure`  + `figcaption`

- **Exemplo:**

  - **HTML:**

    ```html
    <figure>
        <img src="cristo-redentor.jpg" 
             alt="Estátua do Cristo Redentor vista de baixo contra um céu azul limpo" 
             width="600">
        
        <figcaption>
            O Cristo Redentor, no Rio de Janeiro, foi eleito uma das sete maravilhas do mundo moderno. 
            <small>Foto: João Silva/2025</small>
        </figcaption>
    </figure>
    ```

  - **CSS:**

    ```css
    figure {
        border: 1px solid #ddd;
        padding: 10px;
        margin: 20px auto;
        max-width: 500px;
        text-align: center;
    }
    
    figcaption {
        font-size: 0.9rem;
        color: #555;
        font-style: italic;
        margin-top: 8px;
    }
    ```

- **Quando usar:**

  - **Para fotos em artigos, gráficos, ilustrações técnicas ou diagramas que precisam de uma explicação logo abaixo;**

- **Quando não usar:**

  - **Para ícones de menu, logos de cabeçalho ou imagens meramente decorativas que ficam no fundo do site;**
    - **Nesses casos, a `<img>` sozinha (com `alt=""` se for decorativa) é o suficiente;**

- **OBS.:**

  - **O `alt` e o `figcaption` (legenda) possuem funções diferentes (mas são usados em conjunto):**
    - **`alt`: para casos onde a imagem não pode ser visualizada (erro de carregamento ou usuários que usam leitores de tela) — deve ser descritivo;**
    - **`<figcaption>`: serve para dar contexto, crédito ao criador da imagem ou uma explicação técnica que complementa o que está escrito no texto;**



#### Resumo

| Tipo de imagem | Como usar `alt`        |
| -------------- | ---------------------- |
| Informativa    | Descreve o conteúdo    |
| Funcional      | Descreve a ação        |
| Decorativa     | `alt=""`               |
| Logo           | Nome da empresa        |
| Produto        | Descrição objetiva     |
| Gráfico        | Resumo + texto externo |
| Ícone          | Função ou vazio        |