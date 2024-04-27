# Links para os scripts
## Script 1
## Script 2
# Links para os programas
## Programa 1
## Programa 2
# ODBC em Node.js

ODBC, ou **Open Database Connectivity**, é um padrão de API que facilita a comunicação entre aplicações e sistemas de gerenciamento de banco de dados (DBMS). No ambiente do JavaScript e Node.js, o ODBC é utilizado para realizar operações em bancos de dados SQL por meio de drivers específicos.

ODBC em Node.js ajuda a manter uma interface consistente para operações de banco de dados, facilitando a portabilidade do código entre diferentes DBMS.

## Utilização do ODBC em Node.js

Para usar ODBC em Node.js, siga estes passos:

1. **Instale os pacotes necessários**: como `unixODBC` e `unixODBC-devel`, que são essenciais para compilar o módulo `node-odbc`.
2. **Instale os drivers ODBC**: para o DBMS que você deseja acessar.
3. **Configure os arquivos DSN**: para estabelecer as fontes de dados e os drivers ODBC.

Com o pacote `node-odbc`, você pode realizar consultas, inserções, atualizações e exclusões no banco de dados.

## Exemplo de Código

Aqui está um exemplo de como o ODBC pode ser usado em um script Node.js:

Obs: Substitua "DSN=MeuBancoDeDados" pela sua string de conexão real. Este exemplo é simplificado e o uso prático pode variar conforme o seu ambiente e banco de dados específico.

```javascript
const odbc = require('odbc');

async function queryDatabase() {
  try {
    const connection = await odbc.connect('DSN=MeuBancoDeDados');
    const result = await connection.query('SELECT * FROM MinhaTabela');
    console.log(result);
    await connection.close();
  } catch (error) {
    console.error('Erro:', error);
  }
}

queryDatabase();
