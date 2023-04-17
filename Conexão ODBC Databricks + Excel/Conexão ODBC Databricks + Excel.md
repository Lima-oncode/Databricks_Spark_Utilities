# Conexão ODBC Databricks + Excel

## 1.0 Baixar e instalar o Driver

[ODBC Drivers Download – Databricks](https://www.databricks.com/spark/odbc-drivers-download)

## 1.1 Criar um acess token para autenticação na API Databricks

**Na plataforma databricks:** User Settings > Generate new token (importante colar num bloco de notas para uso posterior)

## 1.2 Configuração Simba Spark

Na barra de pesquisa do windows acesse **ODBC data source (64 bits)**

![Untitled](Conexa%CC%83o%20ODBC%20Databricks%20+%20Excel%20e0da91175e7f455083a94643a06988b0/Untitled.png)

Acesse a guia **DSN de sistema** selecione **simba spark** e vá para **configurar**

![Untitled](Conexa%CC%83o%20ODBC%20Databricks%20+%20Excel%20e0da91175e7f455083a94643a06988b0/Untitled%201.png)

Na guia de configuração será necessário informações das **opções avançadas do cluster** databricks na **guia JDBC/ODBC**

A tabela logo abaixo será uma correspôndencia entre simba spark e informações da guia JDBC/ODBC do cluster. 

| Simba Spark | JDBC/ODBC Cluster Databricks  |
| --- | --- |
| Host(s): | Server Hostname |
| Port: | Port |

Na configuração simba spark em **Mechanism** seleciona a opção **User Name and Password.**

Em **User Name** poderá ser identificado como **“token”** em referência ao token de acesso pessoal ou um outra descrição de sua escolha.

Em **Password** será usado o **token gerado uma única vez no passo 1.1.**

Em Thrift Transport selecione a opção HTTP.

Selecione **HTTP Options…** , Em **HTTP Path** cole a URL disponível em **HTTP Path na configuração do cluster databricks na guia JDBC/ODBC.**

Selecione **SSL Options…** , Deixe preenchido a caixa  **Enable SSL.**

Após todos estes processos selecione a opção **Test** e caso retorne a mensagem de conexão realizada com sucesso selecione a opção **OK**

## Conectando o MS Excel com Simba Spark data source

Com o Excel aberto, siga o seguinte caminho dentro do software: **Guia dados > Obter Dados > De Outras Fontes > Do ODBC.**

Em DSN selecione Simba Spark.

Quando solicitado, informe o **User Name e Password (Mesmo token do passo 1.1) feito no passo 1.2**  e será apresentado os databases e suas respectivas tabelas.