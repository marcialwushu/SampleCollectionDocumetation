# SampleCollectionDocumetation
:book: Insomnia documenter 


![Insomnia Documenter](https://github.com/jozsefsallai/insomnia-documenter/blob/master/assets/logo.png?raw=true)



## Requirements
  * Node.js (8.x or higher is recommended)
  * An exported Insomnia workspace JSON (v4)

## Getting Started

Insomnia Documenter offers a CLI tool to make it super easy to set up a documentation page. You can use it in two ways.

### Using `npx`

```sh
npx insomnia-documenter --config /path/to/insomnia/config.json
```

### By installing the package globally

```sh
npm i -g insomnia-documenter
insomnia-documenter --config /path/to/insomnia/config.json
```

### Options

```
Options:
  -c, --config <location>  Location of the exported Insomnia JSON config.
  -l, --logo <location>    Project logo location (48x48px PNG).
  -o, --output <location>  Where to save the file (defaults to current working directory).
  -h, --help               output usage information
```

## Custom Root Paths

Maybe you want to document multiple APIs on the same domain? Perhaps you want to host your documentation page on GitHub pages? In this (any many other cases), you will need to specify what the root path is. To do this, you have to open `index.html` and replace the following line:

```html
<div id="app"></div>
```

with something like this:

```html
<div id="app" data-root="/path/to/docs"></div>
```

In this case, the app will pick up the `insomnia.json` file from the `/path/to/docs` directory. This gives you more flexibility over how you want to maintain your documentation page (for example, you can store the export file somewhere other than the root directory of the webpage). You should NOT put a trailing slash in the `data-root` property.

Please note that setting this attribute will not affect the favicon and the logo of the page. They will still be loaded from the same directory where `index.html` is.

## Running the Page Locally

Opening the `index.html` file will fail to load in 99.9% of cases because that's just how fetch works. To preview the page locally, you might want to use a tool such as [zeit/serve](https://github.com/zeit/serve):

```sh
npx serve
```

The page will be available at http://localhost:5000.

## Vercel 

### 1. Criar a conta/fazer login no Vercel

Primeiro, vamos acessar o site https://vercel.com, você pode clicar em Sign Up para o fazer o cadastro, ou já fazer o Login:


![](https://miro.medium.com/max/1400/1*wNE00KXhOhVz1T0VtbluBg.gif)

Você pode fazer o login com seu github, gitlab ou bitbucket. No meu caso, fiz o login com o meu github! Assim que finalizar, essa será sua tela inicial:

### 2. Importar seu projeto

Agora, vamos escolher o projeto que você quer fazer o deploy. Para isso, clique em Import Project. Em seguida, clique em Continue para importar um repositório do git.


