# White-Label a Documentação (Mintlify)

A Mayahub é uma plataforma de IA de voz para chamadas automáticas de entrada e saída, SMS e automação de fluxos de trabalho.\
Você pode aplicar white-label completo ao produto e a esta documentação com a sua própria marca.

Para saber mais sobre o white-label da plataforma além da documentação, consulte o nosso **programa White-Label**.

Este guia mostra passo a passo como criar sua própria cópia white-label da nossa documentação usando o **Mintlify**, atualizando a identidade visual (cores, logotipos, nome), publicando-a no seu subdomínio Mintlify ou domínio personalizado e, por fim, vinculando a documentação publicada ao seu painel de administração.

## O que você configurará

- Um novo repositório GitHub na sua organização, contendo esta documentação
- Sua marca aplicada via **mint.json** (nome, cores, logotipos, favicon)
- A documentação publicada no seu subdomínio Mintlify (ou domínio personalizado)
- A URL final da documentação referenciada no painel de administração do seu aplicativo

---

### Pré-requisitos

- Uma organização ou conta GitHub com permissão para criar repositórios
- Uma conta Mintlify com acesso para criar um site e conectar um repositório GitHub
- Conhecimento básico de Git

---

### 1) Crie seu repositório no GitHub

Escolha uma das opções abaixo para colocar este código em um novo repositório na sua organização.

**Opção A — Usar este repositório como modelo (recomendado)**

- No GitHub, clique em **"Use this template"** (ou **"Create a new repository from template"**) neste repositório.
- Dê um nome ao novo repositório dentro da sua organização.

**Opção B — Importar o repositório (mantém apenas o estado mais recente)**

- No GitHub, vá até **"Import repository"**.
- Cole a URL deste repositório e importe-o para a sua organização.

---

### 2) Execute a documentação localmente (opcional, mas recomendado)

Instale o **Mintlify CLI**, depois inicie uma pré-visualização local a partir da raiz do repositório onde o arquivo **mint.json** está localizado.

```
npm i -g mintlify
mintlify install
mintlify dev
```

A pré-visualização local estará disponível na URL exibida no seu terminal.

---

### 3) Aplique sua identidade visual no arquivo _mint.json_

Abra o arquivo **mint.json** na raiz do repositório e atualize os campos de marca.\
Campos comuns que você pode querer ajustar incluem:

```
{
  "name": "Your Brand Docs",
  "favicon": "/favicon.png",
  "logo": "/resources/logo-light.svg",
  "logoDark": "/resources/logo-dark.svg",
  "colors": {
    "primary": "#0041E6",
    "light": { "primary": "#0041E6" },
    "dark": { "primary": "#7DA2FF" }
  }
}
```

### Notas

- **name**: Exibido na interface e nos metadados.
- **logo / logoDark**: Caminhos para seus logotipos claro/escuro (SVG ou PNG). Mantenha os caminhos relativos à raiz do repositório.
- **favicon**: Caminho para um ícone quadrado (recomenda-se .png).
- **colors.primary**: Cor primária da sua marca. Se sua configuração incluir variantes claras/escura, ajuste-as também.

Seu arquivo **mint.json** pode incluir campos adicionais, como navegação, rodapé, links sociais, análises, etc. Atualize conforme necessário para a sua marca.

---

### 4) Substitua logotipos e recursos

Coloque seus arquivos de identidade visual no repositório e direcione o **mint.json** para eles:

- Substitua o **favicon.png** da raiz pelo favicon da sua marca (recomendado: PNG 512×512).
- Adicione seus logotipos na pasta **resources/** (por exemplo: `resources/logo-light.svg` e `resources/logo-dark.svg`).
- Atualize os caminhos **logo**, **logoDark** e **favicon** no arquivo **mint.json** para corresponderem aos seus arquivos.

💡 **Dica:** Logotipos em **SVG** geralmente oferecem o melhor resultado visual. Forneça uma versão adequada para fundos claros (**logo**) e outra para fundos escuros (**logoDark**).

---

### 5) (Opcional) Atualize navegação e metadados

Dependendo de como o seu **mint.json** está estruturado, você pode ver campos como **navigation**, **topbarLinks**, **footerLinks**, **github** ou **ogImage**.\
Personalize esses campos para refletir sua marca e a estrutura da sua documentação, mantendo os caminhos consistentes com a estrutura de pastas.

---

### 6) Conecte seu repositório ao Mintlify e publique

- No **Painel do Mintlify**, crie um novo site.
- Conecte o **GitHub** e selecione o repositório que você criou.
- Escolha a **branch** padrão (geralmente `main`) e o diretório raiz da documentação (onde está o **mint.json**).
- Defina seu **subdomínio** Mintlify (exemplo: `suamarca.mintlify.site`).
- Clique em **Deploy**. O Mintlify irá compilar e hospedar sua documentação.

**Opcional:** Se preferir usar um **domínio personalizado** (exemplo: `docs.suamarca.com`), adicione-o no painel do Mintlify e siga as instruções de DNS (geralmente um registro **CNAME** apontando para o destino do Mintlify).\
Aguarde a propagação do DNS e a emissão do certificado SSL.

---

### 7) Referencie a URL da documentação publicada no seu painel de administração

Quando a publicação estiver ativa, copie a **URL final da documentação**.\
No painel de administração do seu aplicativo:

- Vá em **Configurações → White Label (ou Marca)**.
- Localize o campo **"URL da Documentação"** (ou equivalente).
- Cole a sua URL Mintlify (subdomínio ou domínio personalizado) e salve.

Isso tornará a documentação white-label acessível diretamente dentro do seu produto para os seus usuários.

---

### 8) Atualizações contínuas

- Edite o conteúdo (**arquivos .mdx**) e as configurações (**mint.json**) no seu repositório.
- Visualize localmente com `mintlify dev`.
- Faça commit e push para a branch padrão. Se o aplicativo GitHub do Mintlify estiver instalado e conectado, seu site será publicado automaticamente após cada push.

---

### Solução de problemas

- `mintlify dev`**não está rodando:**  execute `mintlify install` para reinstalar as dependências.
- **Erro 404 localmente:** verifique se você está na raiz do repositório onde o **mint.json** está localizado.
- **Marca não atualizando:** confirme se os caminhos dos arquivos no **mint.json** estão corretos e se os arquivos existem no repositório.
- **Publicação não atualizou:** verifique se o Mintlify está conectado ao repositório/branch corretos e se o último commit foi compilado com sucesso no painel do Mintlify.