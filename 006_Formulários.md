# HTML

## Formulários

### Estrutura base correta

```html
<form action="/cadastro" method="POST">
    <!-- Campos -->
    <button type="submit">
        Enviar
    </button>
</form>
```

- **`action`:**
  - **Indica para onde os dados vão;**
- **`method`:**
  - **`GET`: dados aparecem na URL (busca, filtros);**
  - **`POST`: recomendado para o envio de dados sensíveis (login, cadastro);**



### Estrutura ideal

```html
<form action="/cadastro" method="POST">
    <fieldset>
        <legend>Informações pessoais</legend>
        
        <div class="form-group">
            <label for="nome">Nome completo</label>
            <input type="text" id="nome" name="nome" required>
        </div>
        
        <div class="form-group">
            <label for="email">Email</label>
            <input type="email" id="email" name="email" required>
        </div>
    </fieldset>
    
    <button type="submit">Cadastrar</button>
</form>
```

- **Resumo:**

  ```scss
  <form>
   ├─ fieldset
   │   ├─ legend
   │   ├─ label
   │   ├─ input
   │   ├─ mensagens
   └─ button submit
  ```

- **Exemplo:**

  ```html
  <form action="/enviar-dados" method="POST">
      <fieldset>
          <legend>Informações Pessoais</legend>
  
          <div class="form-group">
              <label for="nome-completo">Nome Completo:</label>
              <input type="text" id="nome-completo" name="nome" placeholder="Ex: João Silva" required>
          </div>
  
          <div class="form-group">
              <label for="email-usuario">E-mail Corporativo:</label>
              <input type="email" id="email-usuario" name="email" required>
          </div>
      </fieldset>
  
      <fieldset>
          <legend>Sua Mensagem</legend>
          
          <div class="form-group">
              <label for="assunto">Assunto:</label>
              <select id="assunto" name="assunto">
                  <option value="suporte">Suporte Técnico</option>
                  <option value="vendas">Vendas</option>
              </select>
          </div>
  
          <div class="form-group">
              <label for="mensagem">Mensagem:</label>
              <textarea id="mensagem" name="mensagem" rows="4"></textarea>
          </div>
      </fieldset>
  
      <button type="submit">Enviar Formulário</button>
  </form>
  ```

  - **Uma forma de estruturar (mais recomendada) é colocar o par `label/input` dentro de um container (como uma `div`) para facilitar o *layout*;**



### `<label>`

- **Etiqueta (nome/identificador) do campo de entrada;**

- **Todo `<input>` precisa de um `label`;**

  ```html
  <label for="email">Email</label>
  <input type="email" id="email">
  ```

  - **O atributo `for` do `<label>` se conecta ao atributo `id` do `<input>` (devem ter o mesmo valor);**
    - **Isso possibilita:**
      1. **Clicar no texto do `label` e ativar o `input` (amplia a área de clique);**
      2. **O leitor de tela anuncia o `input` corretamente (a partir do texto/conteúdo do `label`);**

- **OBS.:**

  - **O `placeholder` não substitui o uso do `<label>`;**

    - **Ele serve apenas como um exemplo de formato (quando o usuário começar a digitar ele some);**

  - **Alternativa válida:**

    ```html
    <label>
    	Aceito os termos
        <input type="checkbox" name="termos">
    </label>
    
    <!-- Muito usado para checkboxes/radios -->
    ```



### `<fieldset>` e `<legend>`

- **`<fieldset>`:**

  - **Usado para agrupar campos relacionados;**

    ```html
    <fieldset>
        <legend>Endereço</legend>
        ...
    </fieldset>
    ```


  - **`<legend>`:**
    - **Título para o `fieldset`;**

- **Benefícios:**

  1. **Organizar visualmente;**
  2. **Leitor de tela anuncia o grupo;**

- **Quando usar:**

  1. **Dados pessoais;**
  2. **Pagamento;**
  3. **Endereço;**
  4. **Preferências;**



### `<input>`

- **Campo de entrada;**

  - **O atributo `type` define que ele aceita: texto, email, senha etc.;**

- **Principais tipos:**

  ```html
  <!-- Texto -->
  <input type="text">
  
  <!-- Email (valida o formato automaticamente) -->
  <input type="email">
  
  <!-- Senha -->
  <input type="password">
  
  <!-- Número -->
  <input type="number">
  
  <!-- Telefone -->
  <input type="tel">
  
  <!-- Data -->
  <input type="date">
  
  <!-- Checkbox -->
  <input type="checkbox">
  
  <!-- Radio (radios devem compartilhar o mesmo name) -->
  <input type="radio" name="...">
  ```

  - **OBS.:**
    - **Devemos usar os tipos de `input` específicos para o teclado do celular mudar automaticamente:**
      1. **`type="email"`: Abre o teclado com "@";**
      2. **`type="tel"`: Abre o teclado numérico;**
      3. **`type="number"`: Abre o seletor de números;**
      4. **`type="date"`: Abre um calendário nativo;**



#### `checkbox` (caixa de seleção)

```html
<form>
  <p>Selecione suas cores favoritas:</p>
    
  <input type="checkbox" id="azul" name="cores" value="azul">
  <label for="azul">Azul</label><br>
  
  <input type="checkbox" id="verde" name="cores" value="verde" checked>
  <label for="verde">Verde (padrão)</label><br>
  
  <input type="checkbox" id="vermelho" name="cores" value="vermelho">
  <label for="vermelho">Vermelho</label>
</form>
```

- **`name`: nome do campo enviado ao servidor (agrupa `checkboxes` relacionados);**
  - **Para receber múltiplos valores selecionados, o `checkboxes` compartilham do mesmo valor do atributo `name`;**
- **`value`: valor enviado quando a caixa está marcada;**



#### `radio`

```html
<input type="radio" id="opcao1" name="grupo" value="valor1">
<label for="opcao1">Opção 1</label>

<input type="radio" id="opcao2" name="grupo" value="valor2">
<label for="opcao2">Opção 2</label>

<input type="radio" id="opcao3" name="grupo" value="valor3">
<label for="opcao3">Opção 2</label>
```

- **`name`: usado para agrupar as opções;**
  - **Apenas um item com o mesmo `name` pode ser selecionado;**
- **`value`: valor exclusivo de cada opção (valor enviado ao servidor);**



### `<textarea>`

```html
<label for="mensagem">Mensagem</label>
<textarea id ="mensagem" name="mensagem"></textarea>
```



### `<select>`

```html
<label for="pais">País</label>
<select id="pais" name="pais">
    <option value="">Selecione</option>
    <option value="br">Brasil</option>
</select>
```



### Atributos

- **Principais atributos na tag `<form>`:**
  - **`action`:** 
    - **Define a URL para onde os dados do formulário serão enviados após o clique no botão de enviar;**
  - **`method`:** 
    - **Define o método HTTP para envio;** 
      1. **`GET` anexa os dados à URL (ideal para buscas);** 
      2. **`POST` envia os dados no corpo da requisição (seguro para dados sensíveis);**
- **Principais atributos para os campos de entrada (`<input>`, `<textarea>` e `<select>`:**
  - **`name`:** 
    - **Fundamental para identificar o campo no back-end;**
    - **Sem `name`, o dado não é enviado;**
  - **`type`:** 
    - **Determina o tipo de input (`text`, `password`, `email`, `submit`, `checkbox`, `radio`, etc.);**
  - **`value`:** 
    - **Define o valor inicial ou o valor a ser enviado do campo;**
  - **`placeholder`:** 
    - **Exibe uma dica curta dentro do campo antes do usuário digitar;**
  - **`required`:** 
    - **Atributo booleano que valida se o campo foi preenchido antes do envio;**
  - **`minlength / maxlength`:** 
    - **Define o número mínimo ou máximo de caracteres permitidos;**
  - **`autofocus`:** 
    - **Foca automaticamente no campo ao carregar a página;**



### Acessibilidade

- **`required`:**

  ```html
  <input type="email" required>
  ```

  - **O leitor de tela anuncia que o campo é obrigatório;**

- **`aria-describedby`:**

  ```html
  <label for="senha">Senha</label>
  <input type="password" id="senha" aria-describedby="senhaHelp">
  
  <p id="senhaHelp">
      Deve conter pelo menos 8 caracteres.
  </p>
  ```

  - **Utilizado para mensagens de ajuda;**

- **Mensagens de erro acessíveis:**

  ```html
  <p id="erroEmail" role="alert">
      Email inválido
  </p>
  ```



#### `aria-describedby`

- **Conecta um elemento (`input`) a outro elemento que contém informação complementar;**

  - **Oferece uma descrição adicional ao campo;**

- **Exemplo 1)**

  ```html
  <div class="form-group">
      <label for="usuario">Nome do usuário</label>
      <input
             type="text"
             id="usuario"
             aria-describedby="usuarioHelp"
      >
      
      <p id="usuarioHelp">
          Deve conter entre 4 e 12 caracteres.
      </p>
  </div>
  ```

  - **O leitor de tela anuncia:**

    > "Nome de usuário, campo texto. Deve conter entre 4 e 12 caracteres."

- **Exemplo 2:**

  - **Com senha:**

    ```html
    <div>
        <label for="senha">Senha</label>
        <input
               type="password"
               id="senha"
               aria-describedby="senhaRegras"
        >
        
        <p id="senhaRegras">
            A senha deve ter no mínimo 8 caracteres, incluindo uma letra maiúscula e um número.
        </p>
    </div>
    ```

- **OBS.:**

  - **Embora possa ser definido estaticamente no HTML, pode ser usado com JavaScript para adicionar ou modificar descrições de acessibilidade em tempo de execução (como mensagens de erro dinâmicas, dicas de preenchimento ou diálogos);**



#### Mensagens de erro acessíveis

- **`aria-invalid`:**

  - **Quando há erro:**

    ```html
    <input 
      type="email"
      id="email"
      aria-describedby="erroEmail"
      aria-invalid="true"
    >
    ```

  - **`aria-invalid="true"`: informa que o campo está com erro ou possui um valor inválido;**

    - **Usado com o JavaScript, para ser ativado dinamicamente após a validação do formulário;**

- **`role="alert":`**

  ```html
  <p id="erroEmail" role="alert">
      O email informado é inválido;
  </p>
  ```

  - **Utilizado para comunicar mensagens importantes, urgentes ou de erro aos utilizadores de tecnologias assistivas, como leitores de tela;**
  - **Ele notifica instantaneamente o usuário sobre alterações dinâmicas na página, sem interromper o foco da navegação atual (o usuário não precisa navegar até determinada parte do site para ser informado);**
  - **OBS.:**
    - **O contêiner de alerta deve estar no HTML, mas muitas vezes oculto com CSS (`display: none`), sendo exibido via JavaScript apenas quando o erro ocorre;**

- **Fluxo idela com erro dinâmico:**

  - **Quando o erro surge após validação:**
    1. **Campo recebe:**
       - **`aria-invalid="true"`;**
       - **`aria-describedby="erroEmail";`**
    2. **Mensagem aparece com:**
       - **`role="alert"`;**

- **Exemplo completo:**

  ```html
  <div class="form-group">
  
    <label for="email">Email</label>
  
    <input 
      type="email"
      id="email"
      aria-describedby="emailHint emailError"
      aria-invalid="true">
  
    <p id="emailHint">
      Usaremos seu email para enviar notificações.
    </p>
  
    <p id="emailError" role="alert">
      O email deve conter um "@" válido.
    </p>
  
  </div>
  ```

  - **Comportamento para leitor de tela:**

    > "Email, campo de edição inválido.
    > Usaremos seu email para enviar notificações.
    > O email deve conter um arroba válido."

  - **OBS.:**

    - **Um único `aria-describedby` pode ter vários IDs separados por espaço;**

- **Erros comuns (o que não fazer):**

  - **Colocar o erro longe do campo (o usuário não vai saber qual campo está errado/que ele errou);**
  - **Usar só cor vermelha (pessoas com daltonismo não percebem);**
  - **Não usar `aria-invalid`;**
  - **Atualizar o erro sem o `role="alert"`;**

- **Caso de `checkbox`:**

  ```html
  <div>
    <input 
      type="checkbox"
      id="termos"
      aria-describedby="erroTermos"
      aria-invalid="true">
  
    <label for="termos">
      Aceito os termos
    </label>
  
    <p id="erroTermos" role="alert">
      Você precisa aceitar os termos.
    </p>
  </div>
  ```

- **Dicas:**

  - **Quando houver erros:**

    1. **Focar automaticamente no primeiro campo com erro;**

    2. **Mostrar resumo de erros no topo;**

    3. **Se a informação é importante para preencher corretamente o campo, ela deve estar associada via `aria-describedby`;**

    4. **Cada erro *linka* para o campo correspondente;**

       - **Exemplo:**

         ```html
         <div role="alert">
           <p>Há erros no formulário:</p>
           <ul>
             <li><a href="#email">Email inválido</a></li>
             <li><a href="#senha">Senha muito curta</a></li>
           </ul>
         </div>
         ```

         


#### `aria-label`

- **Substitui o nome (quando o `label` não está visível);**
  - **Se já tivermos o `label`, não é necessário o uso do `aria-label`;**



### Principais erros

1. **Não usar label;**
2. **Usar só placeholder;**
3. **Não indicar campo obrigatório;**
4. **Não agrupar campos relacionados;**
5. **Usar link no lugar de botão;**
6. **Remover foco do teclado;**
7. **Não validar corretamente;**



### Botões

- **Correto:**

  ```html
  <button type="submit">Enviar</button>
  ```

- **Nunca usar:**

  ```html
  <button>Enviar</button>
  ```

- **Tipos:**

  - **`submit`;**
    - **Utilizado para que ao clicar, o formulário seja enviado para o local definido;**
  - **`reset`;**
    - **Limpa todos os campos do formulário, retornando-os ao estado inicial ou vazio;**
    - **Evitar seu uso (quase sempre é clicado sem querer, o que irrita os usuários);**
  - **`button`;**
    - **Não possui comportamento automático;**
    - **Usado para disparar scripts personalizados;**



### Ordem e UX

1. **Ordem lógica de TAB;**
2. **Label acima ou ao lado;**
3. **Campos obrigatórios claramente indicados;**
4. **Mensagens de erro próximas ao campo;**
5. **Evitar formulário gigante;**
6. **Separar por etapas se necessário;**

