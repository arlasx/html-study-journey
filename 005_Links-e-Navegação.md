# HTML

## Links e Navegação

### `<a>`

- **Estrutura básica:**

  ```html
  <a href="/sobre">Sobre</a>
  ```

  - **`href`: indica o destino do link;**

- **OBS.:**

  - **`<a>`: para navegar para algum local;**

  - **`<button>`: para executar uma ação;**

  - **Erro:**

    ```html
    <a href="#" onclick="abrirModal()">Abrir</a> 
    ```

    - **Isso não é navegação, é ação;**

  - **Correto:**

    ```html
    <button type="button">Abrir</button>
    ```



### Tipos de links

#### Interno (mesmo site):

```html
<a href="/contato">Contato</a>
```



#### Externo:

```html
<a href="https://exemplo.com">Visitar site</a>
```

- **Boa prática:**

  ```html
  <a 
     href="https://exemplo.com"
     target="_blank"
     rel="noopener noreferrer"
  >
     Abrir em nova aba
  </a>
  ```

  - **`noopener`:**
    - **Foco em segurança;**
    - **Para que serve:** 
      1. **Impede que a página de destino (o site que você está abrindo) assuma o controle da sua página original através do JavaScript (`window.opener`);**
    - **Por que é boa prática:** 
      1. **Evita um ataque de segurança chamado "tabnabbing";**
      2. **Sem o noopener, um site malicioso aberto em uma nova aba pode forçar a sua página original a se redirecionar para um site de phishing (falso), após a página ficar inativa por um tempo;**
      3. **Por exemplo: um usuário que retorna depois de um tempo e vê a página de login pode ser induzido a acreditar que a página é legítima e inserir seu login, senha e outros dados que serão usadospara fins ilícitos;**
  - **`noreferrer`:**
    - **Foco em privacidade;**
    - **Para que serve:** 
      1. **Impede que o navegador passe informações de referência (o endereço da sua página) para o site de destino;**
    - **Por que é boa prática:** 
      1. **Aumenta a privacidade do usuário e protege dados, pois o site de destino não saberá de onde o visitante veio (a referência aparecerá como "direta" em ferramentas de análise, não como um link no seu site);**



#### Âncora (mesma página)

```html
<a href="#faq">Ir para FAQ</a>

<section id="faq">
  <h2>FAQ</h2>
</section>
```



#### Email

```html
<a href="mailto:contato@site.com">Enviar email</a>
```



#### Telefone

```html
<a href="tel:+5511999999999">Ligar</a>
```



#### Whatsapp

```html
<a href="https://wa.me/seunumeroaqui">Chamar no Zap</a>
```



### Texto do link

- **Deve fazer sentido sozinho:**

  ```html
  <a href="/curso">Curso completo de HTML5</a>
  ```

  - **O link deve indicar para onde o usuário está indo (ao clicar nele);**

- **O que não fazer:**

  ```html
  <a href="/curso">Clique aqui</a>
  
  <a href="/curso">Saiba mais</a>
  ```

  - **Isso é ruim para:**
    - **SEO;**
    - **Leitor de tela;**



### Acessibilidade

- **O texto do link deve estar claro;**

- **Ícones sozinhos precisam de `aria-label`:**

  ```html
  <a href="/buscar" aria-label="Buscar no site">
    🔍
  </a>
  ```



### Estrutura ideal de navegação (navbar)

- **Estrutura 1:**

  ```html
  <header>
    <div class="container">
      
      <a href="/" class="logo">
        <img src="logo.png" alt="TechNova - Página inicial">
      </a>
  
      <nav aria-label="Navegação principal">
        <ul>
          <li><a href="/sobre">Sobre</a></li>
          <li><a href="/servicos">Serviços</a></li>
          <li><a href="/blog">Blog</a></li>
          <li><a href="/contato">Contato</a></li>
        </ul>
      </nav>
  
    </div>
  </header>
  ```

- **OBS.:**

  - **`<header>` define topo;**
  - **`<nav>` indica navegação;**
  - **`<ul>` agrupa links relacionados;**
  - **`aria-label` para leitores de tela;**
  - **Logo leva para home;**

- **Erros comuns:**

  - **Usar `<div>` no lugar de `<nav>`;**
  - **Não usar lista;**
  - **Não ter foco visível;**
  - **Usar apenas ícones sem rótulo;**

- **Estrutura 2:**

  ```html
  <header>
      <div class="logo">
          <a href="/">MeuSite</a>
      </div>
  
      <nav aria-label="Navegação Principal">
          <ul>
              <li><a href="/" aria-current="page">Home</a></li>
              <li><a href="/servicos">Serviços</a></li>
              <li><a href="/blog">Blog</a></li>
              <li><a href="/contato">Contato</a></li>
          </ul>
      </nav>
  </header>
  ```



### Estados de link

- **Links possuem os seguintes estados:**

  - **`:link`;**
  - **`:visited`;**
  - **`:hover`;**
  - **`:focus`;**
  - **`:active`;**

- **Não devemos remover o `:focus` sem substituir por algo visível:**

  ```css
  a:focus {
    outline: 2px solid blue;
  }
  ```



### Navegação estruturada (Arquitetura da Informação)

- **Uma boa navegação:**
  - **Não possui 30 links no menu;**
  - **Agrupa os itens por categoria;**
  - **Usa dropdown com cuidado;**
  - **Funciona sem mouse;**
  - **Funciona sem JavaScript;**



### Breadcrumb (navegação contextual)

- **Elemento de interface que mostra ao usuário sua localização exata dentro da estrutura hierárquica do site;**

  <img src="/home/xella/Área de trabalho/Zzz.../Estudos/HTML/imgs/breadcrumb-navigation.jpg" />

  - **Exemplo:**

    ```scss
    Home > Eletrodomésticos > Geladeiras > Refrigeradores Frost Free
    ```

- **HTML:**

  ```html
  <nav aria-label="Breadcrumb">
    <ol>
      <li><a href="/">Home</a> > </li>
      <li><a href="/produtos">Produtos</a> > </li>
      <li aria-current="page">Camisetas</li>
    </ol>
  </nav>
  ```

  - **Considerações:**
    - **Devemos  utilizar `<nav aria-label="breadcrumb">` e o atributo `aria-current="page"` no último item para indicar a página atual;**
    - **Usamos algum separador (como `>` ou `/`) que pode ser adicionado diretamente no HTML ou via CSS (usando `::before` ou `::after` para melhor acessibilidade);**
    - **O último item não deve conter link, pois representa a página atual;**
    - **Ajuda os motores de busca a entenderem a hierarquia do site;**

- **Curiosidade:**

  - **O nome é inspirado na história de João e Maria, que deixavam migalhas para encontrar o caminho de volta;**
    - **Da mesma forma, os breadcrumbs fornecem uma trilha de links que permite aos usuários rastrear seus passos desde a página atual até a página inicial (Home);**



### Quando não usar `<a>`

- **Não devemos usar links para:**

  - **Para abrir um modal;**

  - **Para submeter formulário;**

  - **Para trocar aba interna;**

    - **Trocar a aba interna (ou *tab*) em um site significa alterar o conteúdo exibido em uma parte específica da página sem recarregar o site inteiro;**

    - **Não devemos usar o `<a>`, pois:**
      1. **Reload (recarregamento) da página: como a tag `<a>` é projetada para navegar para uma outra URL, ao utilizá-la ela recarrega todo o site, causando um "piscar" na tela, o que quebra a experiência de fluidez para o usuário;**
      2. **Perda de estado: caso um usuário tenha preenchido um formulário ou estava rolando um texto longo em uma aba, ao clicar em um `<a>` que simula a troca de aba, a página irá recarregar e o usuário perde o que estava fazendo;**
      3. **Semântica incorreta: abas internas não são "novas páginas", mas sim estados diferentes da mesma página;**

  - **Para realizar uma ação com JavaScript;**

- **Para esses casos devemos usar o `<button>`;**



### Estrutura para header

- **Estrutura recomendada:**

  ```scss
  <header>
   ├─ Logo (link para home)
   ├─ Nav principal
   ├─ Busca (opcional)
   └─ CTA (login, botão destaque)
  ```

- **Exemplo (HTML):**

  ```html
  <header>
    <a href="/">Logo</a>
  
    <nav aria-label="Principal">
      <ul>
        <li><a href="/produtos">Produtos</a></li>
        <li><a href="/precos">Preços</a></li>
        <li><a href="/sobre">Sobre</a></li>
      </ul>
    </nav>
  
    <a href="/login" class="btn">Entrar</a>
  </header>
  ```

  

### Boas práticas

1. **Um único `<nav>` principal;**
2. **Podemos ter múltiplos `<nav>` (rodapé, sidebar);**
3. **Sempre use `aria-label` quando houver mais de um;**
4. **Nunca usar link vazio (`href="#"`);**
5. **Evitar JS que quebra navegação padrão;**
6. **Links devem ser navegáveis por TAB;**