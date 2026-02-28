# HTML

## Headings

- **`H1...H6`**
  - **Representam títulos hierárquicos que estruturam o conteúdo da página;**
    - **Utilizados para organização semântica;**



### Hierarquia correta

```scss
H1  ⮕ Título principal da página
 └─ H2 ⮕ Seções principais
     └─ H3 ⮕ Sub-seções
         └─ H4 ⮕ Detalhes
             └─ H5 ⮕ Subdetalhes
                 └─ H6 ⮕ Último nível
```



#### `H1`

- **Representa o título (assunto) principal da página;**

- **Regras:**

  - **Devemos usar um `H1` por página;**
  - **Ele deve representar o assunto central;**
  - **Pode estar dentro de um `header` ou `main`;**

- **Exemplo:**

  ```html
  <h1>Receitas</h1>
  ```

  



#### `H2`

- **Divide o conteúdo em grandes blocos (seções principais);**

  - **Exemplo:**

    ```html
    <h2>Ingredientes</h2>
    <h2>Modo de Preparo</h2>
    ```




#### `H3`

- **Subdivide os blocos definidos pelo `H2` (sub-seções);**

  - **Exemplo:**

    ```html
    <h2>Ingredientes</h2>
    	<h3>Massa</h3>
        <h3>Recheio</h3>
    ```




#### `H4`, `H5` e `H6`

- **Representam níveis mais profundos de detalhes;**
- **OBS.:**
  - **São poucos usados;**
  - **Mais comuns em:**
    - **Documentação;**
    - **Artigos técnicos;**
    - **Trabalhos acadêmicos;**



### Exemplo de estrutura

```html
<main>
  <h1>Guia de HTML5</h1>

  <section>
    <h2>Introdução</h2>
    <p>...</p>
  </section>

  <section>
    <h2>Semântica</h2>

    <article>
      <h3>Header</h3>
      <p>...</p>
    </article>

    <article>
      <h3>Main</h3>
      <p>...</p>
    </article>
  </section>
</main>
```