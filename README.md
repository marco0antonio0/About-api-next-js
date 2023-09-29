
# Como iniciar uma api next clean
### > deploy netlify como api ✅
### > funcionando corretamente para deploy ✅
### > next js versão para pdoer funcionar no netlify >> 13.4.19 ✅ 

**Passo 1: Inicialização do Projeto**
Crie um novo diretório para o seu projeto e acesse-o:

```bash
mkdir meu-projeto-api-nextjs
cd meu-projeto-api-nextjs
```

Inicialize um novo projeto Node.js:

```bash
npm init -y
```

Configure o package.json com os scripts necessários:

```json
"scripts": {
  "dev": "next",
  "build": "next build",
  "start": "next start"
}
```

**Passo 2: Instalação do Next.js**
Execute o seguinte comando para instalar o Next.js, React e React DOM:

```bash
npm install next@13.4.19 react react-dom
```

**Passo 3: Criação da Estrutura de Diretórios**
Crie a seguinte estrutura de diretórios:

```
meu-projeto-api-nextjs/
  |-- pages/
  |    |-- api/
  |         |-- exemplo.js
```
### comando rapido de criação 
```bash
mkdir -p pages/api
```

**Passo 4: Criação de uma Rota de API de Exemplo**
Dentro do diretório api, crie um arquivo chamado exemplo.js para criar uma rota de API de exemplo:

```javascript
// api/exemplo.js

export default function handler(req, res) {
  res.status(200).json({ message: "Esta é uma rota de API de exemplo" });
}
```

**Passo 5: Inicialização do Servidor de Desenvolvimento**
Execute o seguinte comando para iniciar o servidor de desenvolvimento:

```bash
npm run dev
```

Isso iniciará seu aplicativo Next.js em http://localhost:3000.

**Passo 6: Acesso à Rota de API**
Abra seu navegador ou use uma ferramenta como o Postman para acessar a rota de API de exemplo em http://localhost:3000/api/exemplo
