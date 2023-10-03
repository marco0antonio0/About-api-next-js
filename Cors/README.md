# Configurando CORS em uma API base

Para aplicar as configurações de CORS na API do Next.js e adicionar o trecho de código que você forneceu, siga este tutorial aprimorado:

1. **Em sua api base:** Se você ainda não tem o Next.js instalado, você pode criar uma api base va para [Inicio](./../README.md)

2. **Crie um middleware para CORS:** Dentro do seu projeto api base, crie um diretório chamado `middleware` na raiz do projeto.

3. **Dentro do arquivo da sua api, adicione este trecho de codigo** :

```javascript
export default function corsMiddleware(req, res, next) {
  //=============================================================
  // codigo cors aplicado
  res.setHeader("Access-Control-Allow-Credentials", true);
  res.setHeader("Access-Control-Allow-Origin", "*");
  res.setHeader(
    "Access-Control-Allow-Methods",
    "GET, OPTIONS, PATCH, DELETE, POST, PUT"
  );
  res.setHeader(
    "Access-Control-Allow-Headers",
    "X-CSRF-Token, X-Requested-With, Accept, Accept-Version, Content-Length, Content-MD5, Content-Type, Date, X-Api-Version"
  );
  //=============================================================
  // Chame o próximo middleware ou manipulador de rota
  // neste no caso seria o demais do seu codigo api
  // ... codigo api aqui ...
}
```

4. **Teste a API com CORS:** Agora, você pode acessar sua rota personalizada `minha-rota` e as configurações de CORS serão aplicadas a ela. Você pode fazer isso chamando a rota API no seu aplicativo ou através de ferramentas como o Postman ou o cURL.

Por exemplo, você pode acessar sua rota no navegador em `http://localhost:3000/api/minha-rota` ou usando o cURL:

```bash
curl -X GET http://localhost:3000/api/minha-rota
```

Lembre-se de que este é um exemplo simples de como aplicar o CORS em uma rota da API do Next.js. Você pode ajustar as configurações e os endpoints de acordo com as necessidades do seu aplicativo. Certifique-se de testar e verificar se as configurações de CORS estão funcionando conforme o esperado.
