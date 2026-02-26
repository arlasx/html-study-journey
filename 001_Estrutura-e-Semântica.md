# HTML

## Estrutura Básica

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título do Site</title>
</head>
<body>
</body>
</html>
```



## Semântica

```html
<body>
    <header>
        <h1>Meu Blog de Tecnologia</h1>
        <nav>
            <ul>
                <li><a href="#">Home</a></li>
                <li><a href="#">Tutoriais</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <article>
            <h2>Aprendendo HTML5</h2>
            <p>O HTML5 mudou a forma como estruturamos a web...</p>
        </article>

        <section>
            <h3>Comentários dos Leitores</h3>
        </section>
    </main>

    <aside>
        <h4>Sobre o autor</h4>
        <p>Apenas um entusiasta de código.</p>
    </aside>

    <footer>
        <p>&copy; 2026 - Desenvolvido com foco em semântica.</p>
    </footer>
</body>
```

- **`<header>`:** 
  - **Cabeçalho da página (ou de uma seção);**
  - **Geralmente agrupa a logo/título;**
- **`<nav>`:** 
  - **Menus de navegação;**
  - **Pode agrupar os links principais (sistema principal de navegação da página/site) ou secundários;**
- **`<main>`: representa o conteúdo principal página (dever ser único — só podemos ter um elemento `main` por página);**
  - **`<article>`:** 
    - **Conteúdo independente, que faz sentido sozinho (como um post de blog);**
  - **`<section>`:** 
    - **Agrupa conteúdos relacionados dentro do site;**
- **`<aside>`:** 
  - **Conteúdo complementar (ex.: barra lateral);**
  - **Agrupa conteúdo secundário, como anúncios ou "posts relacionados";**
- **`<footer>`:** 
  - **Rodapé do site (rodapé principal) ou de uma seção do site;**
  - **Reúne informações de contato, redes sociais e copyright;**



### Importância

- **SEO (Google):** 
  - **Os robôs de busca entendem melhor o conteúdo do site e ranqueiam a página/site de uma forma melhor (mais positiva);**
- **Acessibilidade:** 
  - **Leitores de tela para pessoas que apresentam algum tipo de deficiência conseguem "explicar" o site de uma forma muito melhor;**
- **Organização/Manutenção:** 
  - **O código fica muito mais limpo e fácil de ler;**



## Estrutura (Básica) Moderna

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título da Página</title>
    <!-- SEO básico -->
    <meta name="description" content="Descrição da página">
    <meta name="author" content="Seu nome">
    <!-- CSS -->
    <link rel="stylesheet" href="style.css">
    <!-- Ícone -->
    <link rel="icon" href="favicon.ico">
</head>

<body>
    <!-- Header -->
    <header>
        <h1>Logo / Título</h1>
        <!-- Nav -->
        <nav>
            <ul>
                <li><a href="#">Início</a></li>
                <li><a href="#">Sobre</a></li>
                <li><a href="#">Contato</a></li>
            </ul>
        </nav>
    </header>
	<!-- Main -->
    <main>
		<!-- Section -->
        <section>
            <h2>Seção principal</h2>
            <p>Conteúdo principal da página.</p>
        </section>
		<!-- Article -->
        <article>
            <h2>Artigo</h2>
            <p>Conteúdo independente, como post ou notícia.</p>
        </article>
		<!-- Aside -->
        <aside>
            <h3>Conteúdo lateral</h3>
            <p>Links, anúncios, infomações extras.</p>
        </aside>
    </main>
	<!-- Footer -->
    <footer>
        <p>&copy; 2026 - Seu site</p>
    </footer>

    <!-- JS -->
    <script src="script.js" defer></script>
</body>
</html>
```



### Boas práticas (modernas)

- **CSS externo;**
- **JS no final do `<body>`;**
- **Um elemento `main` por página;**
- **Hierarquia correta de títulos (`h1 ⮕ h2 ⮕ h3`);**
- **Evitar o uso de `<div>` (não apresenta semântica);**