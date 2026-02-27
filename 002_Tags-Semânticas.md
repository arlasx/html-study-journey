# HTML

## Tags Semânticas

- **Apresentam significado;**
  - **Indicam ao navegador, mecanismos de busca e leitores de tela, o significado de cada parte da página;**



### `<header>`

- **O que é?**
  - **Cabeçalho de uma página ou seção;**
- **O que pode conter?**
  - **Logo;**
  - **Títulos (`h1` - `h6`);**
  - **Menu (`nav`);**
  - **Barra de busca;**
- **O que não deve conter?**
  - **Conteúdo principal (`main`);**
  - **Rodapé (`footer`);**
- **OBS.:**
  - **Seção = outras partes do site;**




### `<nav>`

- **O que é?**
  - **Área de navegação principal do site;**
    - **Também pode ser usada para navegação secundária, como um menu no rodapé, onde temos links para: **
      1. **Páginas de suporte;**
      2. **Políticas de privacidade;**
      3. **Redes sociais;**
- **O que pode conter?**
  - **Listas (`ul` e `li`);**
  - **Links (`a`);**
- **Quando usar?**
  - **Quando se têm links que levam para outras páginas ou seções importantes do documento atual;**
- **Quando não usar?**
  - **Para definir links soltos nomeio do texto;**



### `<main>`

- **O que é?**
  - **Conteúdo principal e único da página;**
- **Regras importantes:**
  - **Só pode existir um elemento `main` por página;**
  - **Deve conter o conteúdo exclusivo da página (que não se repete no site todo);**
  - **O elemento `main` não pode ser definido dentro de outros elementos, como:**
    1. **`header`;**
    2. **`footer`;**
    3. **`article`;**
    4. **`aside`;**



### `<section>`

- **O que é?**
  - **Cabeçalho de uma página ou seção;**
- **O que pode conter?**
  - **Logo;**
  - **Títulos (`h1` - `h6`);**
  - **Menu (`nav`);**
  - **Barra de busca;**
- **O que não deve conter?**
  - **Conteúdo principal (`main`);**
  - **Rodapé (`footer`);**



### `<section>`

- **O que é?**
  - **Elemento que agrupa conteúdos relacionados (que apresentam o mesmo tema);**
- **Considerações importantes:**
  - **Se precisa de um título para definir determinada parte de uma página, podemos utilizar o elemento `section`;**
  - **Não deve ser utilizada para fins de estilização (nesse caso é recomendado o uso de `divs`);**



### `<article>`

- **O que é?**
  - **Representa um conteúdo independente — que faz sentido sozinho;**
    - **Um conteúdo independente é aquele tipo de conteúdo que você pode colocar em qualquer parte da página, que ele ainda vai fazer sentido por si só;**
- **O que pode ser?**
  - **Post de blog;**
  - **Notícia;**
  - **Card de produto;**
  - **Comentários;**



### `<aside>`

- **O que é?**
  - **Área de conteúdo complementar ao principal;**
- **Exemplos:**
  - **Barra lateral;**
  - **Links relacionados;**
  - **Anúncios;**
  - **Autor do post;**



### `<footer>`

- **O que é?**
  - **Rodapé da página ou de uma seção;**
- **O que pode conter?**
  - **Copyright;**
  - **Links extras;**
  - **Autor;**
  - **Contato;**
  - **Data;**



### `<figure>` + `<figcaption>`

- **O que é?**

  - **Elementos usados em conjunto, utilizados para agrupar algum tipo de mídia (imagem, gráfico, trechos de código, ilustração, áudio ou vídeo);**

- **Exemplo:**

  ```html
  <figure>
  	<img src="imagem.png" alt="Texto alternativo">
      <figcaption>Legenda para a imagem</figcaption>
  </figure>
  ```

  

### `<address>`

- **O que é?**
  - **Agrupa informações de contato do autor ou organização;**
- **O que pode conter?**
  - **Email;**
  - **Telefone;**
  - **Endereço;**
  - **Redes Sociais;**



### `<time>`

- **O que é?**

  - **Indica datas e horários que podem ser interpretáveis por máquinas (através do atributo `datetime`);**

- **Exemplo:**

  ```html
  <time datetime="2026-02-03">3 de fevereiro de 2026</time>
  ```

  - **O valor do atributo `datetime` é o valor que é lido/legível para a máquina;**
  - **Enquanto conteúdo da tag `time` é o valor que lido/legível para os usuários;**



### `<mark>`

- **O que é?**
  - **Representa um destaque semântico/contextual (não visual);**
    - **Porém, o navegador geralmente aplica um fundo amarelo e texto preto;**
- **Exemplo:**
  - **Resultado de busca, destacando a palavra encontrada;**




### `<details>` + `<summary>`

- **O que é?**

  - **Conteúdo expansível (tipo FAQ — seção de dúvi);**

- **Exemplo:**

  ```html
  <details>
    <summary>Pergunta</summary>
    <p>Resposta</p>
  </details>
  ```

  