# **Kit Inicial do Mintlify**

Clique em **"Use this template"** para copiar o kit inicial do Mintlify. O kit contém exemplos como:

- Páginas de guias (Guide pages)
- Navegação (Navigation)
- Personalizações (Customizations)
- Páginas de referência de API (API Reference pages)
- Uso de componentes populares

### **Desenvolvimento**

Instale o **Mintlify CLI** para visualizar as alterações da documentação localmente. Para instalar, use o seguinte comando:

```
npm i -g mintlify
```

Execute o seguinte comando na raiz da sua documentação (onde está o arquivo `mint.json`):

```
mintlify dev
```

### **Publicando Alterações**

Instale o nosso **Github App** para propagar automaticamente as alterações do seu repositório para o seu site.

As alterações serão implantadas automaticamente em produção após o push para a branch padrão.

Você encontrará o link para instalar o app no seu **dashboard**.

#### **Solução de Problemas**

- **Mintlify dev não está rodando** – Execute `mintlify install` para reinstalar as dependências.
- **Página carregando como 404** – Verifique se você está executando dentro de uma pasta que contém o arquivo `mint.json`.