# 💻 api-flask-faturamento

# 📕 Descrição
Este projeto é uma API criada com Flask que fornece dados de faturamento a partir de uma tabela Excel. A API possui diferentes endpoints para retornar o faturamento total, vendas por produto e vendas de um produto específico. Os dados são processados utilizando a biblioteca pandas, permitindo operações como agrupamento e soma dos valores.

# ☕ Como Usar
1. **Pré-requisitos:**
   - Instale as dependências necessárias:
     ```bash
     pip install flask pandas
     ```
   - Certifique-se de que o arquivo Excel (`Vendas - Dez.xlsx`) está no mesmo diretório do script ou ajuste o caminho no código:
     ```python
     tabela = pd.read_excel("Vendas - Dez.xlsx")
     ```

2. **Configuração do Código:**
   - O arquivo Excel deve conter, pelo menos, as colunas:
     - `Produto`: Nome do produto vendido.
     - `Valor Final`: Valor da venda.

3. **Endpoints Disponíveis:**
   - **Faturamento Total:** 
     - Endpoint: `/`
     - Retorna o faturamento total somado da coluna `Valor Final`.
     - Exemplo de retorno:
       ```json
       {"faturamento": 50000.0}
       ```
   - **Vendas por Produto:** 
     - Endpoint: `/vendas/produtos`
     - Retorna as vendas agrupadas por produto.
     - Exemplo de retorno:
       ```json
       {
         "Produto A": {"Valor Final": 30000.0},
         "Produto B": {"Valor Final": 20000.0}
       }
       ```
   - **Faturamento de um Produto Específico:** 
     - Endpoint: `/vendas/produtos/<produto>`
     - Substitua `<produto>` pelo nome do produto desejado.
     - Retorna os dados de vendas do produto, ou indica se o produto não existe.
     - Exemplo de retorno:
       ```json
       {"Valor Final": 30000.0}
       ```

4. **Executando a API:**
   - Inicie o servidor Flask com:
     ```bash
     python app.py
     ```
   - A API ficará disponível localmente no endereço:
     ```
     http://127.0.0.1:5000
     ```
   - Caso esteja rodando em um ambiente como o Replit, utilize:
     ```python
     app.run(host='0.0.0.0')
     ```

5. **Testando os Endpoints:**
   - Utilize ferramentas como Postman, Insomnia ou o próprio navegador para acessar os endpoints.

# Contribuindo para api-flask-faturamento
1. Para contribuir com api-flask-faturamento, siga estas etapas:
2. Bifurque este repositório.
3. Crie um branch: `git checkout -b <nome_branch>`.
4. Faça suas alterações e confirme-as: `git commit -m '<mensagem_commit>'`.
5. Envie para o branch original: `git push origin api-flask-faturamento/<local>`.
6. Crie a solicitação de pull.

Como alternativa, consulte a documentação do GitHub em [como criar uma solicitação pull](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request).
