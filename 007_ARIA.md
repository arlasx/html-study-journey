# HTML

## ARIA

- ***Accessible Rich Internet Application* (Aplicações Ricas de Internet Acessíveis);**
- **Especificação do W3C;**
- **Permite:**
  1. **Melhorar a acessibilidade em interfaces dinâmicas;**
  2. **Dar significado extra quando o HTML não é suficiente;**
  3. **Tornar componentes complexos utilizáveis por leitores de tela;**



## Categorias

1. ***Roles* (papéis);**
1. ***States* (estados);**
1. ***Properties* (propriedades);**



### *Roles*

- **Definem o tipo do elemento quando o próprio HTML não é suficiente;**



#### `role=button`

- **Exemplo:**

  ```html
  <div role="button" tabindex="0">
    Abrir menu
  </div>
  ```

  - **OBS.:**

    1. **Isso não seria necessário, pois o próprio HTML disponibiliza o elemento `button` (isto é só um exemplo de como definir um elemento, que não é um `button`, como um botão);**

    2. **Nesse caso, apenas o uso do atributo `role` não é suficiente, sendo necessário o uso do JavaScript para:**
       - **Tornar o elemento clicável via teclado (Enter + Espaço);**
       - **Gerenciar estados;**
    3. **Mais sobre `tabindex` na seção de considerações;**



#### `role=navigation`

- **Exemplo:**

  ```html
  <div role="navigation">...</div>
  ```

  - **OBS.:**
    - **Mais um exemplo desnecessário, já que o HTML disponibiliza o elemento `nav` para a definição de uma "seção" de navegação;**



#### `role=alert`

- **Exemplo:**

  ```html
  <p role="alert">
    Senha incorreta
  </p>
  ```

  - **Usados para mensagens de teor urgente;**
    - **Pode ser só HTML (sem uso de JS);**
    - **O leitor de tela anuncia automaticamente;**
    - **Muito usado como forma de validação;**



#### `role=dialog`

- **Exemplo:**

  ```html
  <div role="dialog" aria-modal="true">
    ...
  </div>
  ```

  - **Usado para modais;**
  - **OBS.:**
    - **É necessário o uso de JavaScript para:**
      - **Controlar foco;**
      - **Prender foco dentro do modal;**
      - **Restaurar foco ao fechar;**



### *States*

- **Estados importantes...**



#### `aria-expanded`

- **Exemplo:**

  ```html
  <button aria-expanded="false">
    Abrir Menu
  </button>
  ```

  - **Indica se algo está aberto ou fechado;**

  - **No JavaScript:**

    ```js
    aria-expanded="true"
    ```

    - **Sempre vai precisar do JavaScript para ficar atualizando o valor;**

  - **Muito usado em:**

    - **Menus *dropdown*;**
    - **Menus *accordion*;**
    - **Menus mobile;**



#### `aria-pressed`

- **Exemplo:**

  ```html
  <button aria-pressed="false">
    Curtir
  </button>
  ```

  - **Usado para botões alternáveis (*toggle*);**

  - **No JavaScript:**

    ```js
    aria-pressed="true"
    ```

    - **Também precisa do JavaScript para atualizar o valor;**



#### `aria-hidden`

- **Exemplo:**

  ```html
  <span aria-hidden="true">🔍</span>
  ```

  - **Esconde elementos de leitores de tela;**
  - **Pode ser só HTML (sem uso de JavaScript);**
  - **Muito usado em ícones decorativos;**



### *Properties*



#### `aria-label`

- **Exemplo:**

  ```html
  <button aria-label="Fechar">
    ✖
  </button>
  ```

  - **Dá um identificador (nome) quando não há um texto visível;**
  - **Pode ser estático (o valor não muda);**
  - **Não precisa de JavaScript;**



#### `aria-labelledby`

- **Exemplo:**

  ```html
  <h2 id="tituloModal">Cadastro</h2>
  
  <div role="dialog" aria-labelledby="tituloModal">
  ```

  - **Referencia a outro elemento como nome;**
  - **Pode ser estático;**



#### `aria-describedby`

- **Exemplo:**

  ```html
  <input aria-describedby="ajuda">
  ```

  - **Usado para associar elementos de interface (como campos de formulário ou botões) a textos descritivos adicionais, instruções ou mensagens de erro presentes na página;**
  - **Pode ser estático/dinâmico;**



#### `aria-live`

- **Exemplo:**

  ```html
  <div aria-live="polite">
    Produto adicionado ao carrinho.
  </div>
  ```

  - **Usado para conteúdos que atualizam automaticamente;**
  - **Tipos:**
    - **`polite`: espera o terminar a leitura atual;**
    - **`assertive`: interrompe a leitura;**
  - **Normalmente usado com JavaScript;**



## ARIA + JS

| Atributo           |   Precisa JS?    |
| ------------------ | :--------------: |
| `aria-label`       |        ❌         |
| `aria-describedby` |        ❌         |
| `aria-hidden`      |        ❌         |
| `role="alert"`     |        ❌         |
| `aria-expanded`    |        ✅         |
| `aria-pressed`     |        ✅         |
| `role="dialog"`    |        ✅         |
| `aria-live`        | ⚠️ geralmente sim |



## Erros 

1. **Usar ARIA para substituir HTML semântico;**
2. **Esquecer de atualizar estados;**
3. **Usar aria-hidden em botão interativo;**
4. **Criar botão com div e esquecer teclado;**
5. **Usar aria-label quando já existe label visível**



## Exemplo

```html
<button 
  aria-expanded="false"
  aria-controls="menuPrincipal">
  Menu
</button>

<nav id="menuPrincipal" hidden>
  ...
</nav>
```

- **JavaScript:**
  - **Alterna o `hidden`;**
  - **Alterna o `aria-expanded`;**



## Recomendações

1. **Usar HTML primeiro;**
2. **Usar ARIA para complementar;**
3. **Se o estado for dinâmico: atualizar via JavaScript;**
4. **Nunca usar ARIA para maquiar HTML ruim;**



## Considerações

- **O ARIA não deve ser utilizado quando o próprio HTML é suficiente;**

  - **Por exemplo:**

    - **Desnecessário:**

      ```html
      <div role="button">Enviar</div>
      ```

    - **Já que se tem:**

      ```html
      <button>Enviar</button>
      ```

- **`tabindex`:**

  - **Atributo HTML global que define se um elemento pode receber foco do teclado e sua ordem na navegação via tecla *Tab*;**
    - **Essencial para acessibilidade;**
  - **Usos e valores:**
    1. **`tabindex="0"`:**
       - **Insere um elemento não interativo (como um `<div>`) na ordem de tabulação natural da página (baseado na ordem do DOM);**
    2. **`tabindex="-1":`**
       - **Remove o elemento da navegação sequencial (tecla *Tab*), mas permite que ele receba foco via JavaScript usando o método `.focus()`;**
    3. **`tabindex="1"` (ou maior):**
       - **Define uma ordem de tabulação específica e personalizada;**
       - **OBS.: evite valores positivos (maiores que `0`), pois podem quebrar a ordem de navegação lógica da página e dificultar a usabilidade;**