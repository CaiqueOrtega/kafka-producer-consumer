## Documentação do Projeto: Sistema de Fila com Apache Kafka

### Introdução

Este documento descreve a implementação de um sistema de fila utilizando Apache Kafka para comunicação de mensagens entre um produtor e um consumidor, integrado em um ambiente Docker. O objetivo deste sistema é receber requisições REST, processá-las e colocá-las em uma fila Kafka para posterior processamento pelo consumidor.

## 1. Instalação

#### Pré-requisitos:
- **Docker**: Certifique-se de ter o Docker instalado em seu sistema. Você pode baixá-lo e instalá-lo a partir do site oficial do Docker.

## 2. Passos de Instalação

  #### 1. Clone o repositório do projeto do GitHub:

```bash
git clone <link_do_repositorio>
```

  ####  2. Navegue até o diretório do projeto:

```bash
cd nome_do_diretorio_do_projeto
```

## 3. Configuração

### Docker Compose

O sistema utiliza Docker Compose para gerenciar os contêineres. O arquivo `docker-compose.yml` já está configurado para iniciar os serviços necessários. Não são necessárias modificações adicionais.

## 4. Operação

### Inicialização do Sistema

Para iniciar o sistema, execute o seguinte comando no diretório do projeto:

```bash
docker-compose up
```
Este comando iniciará os contêineres do produtor, consumidor e Kafka.

## 5. Uso do Sistema

### 1. Produtor:

O produtor expõe um endpoint REST para receber requisições. Envie requisições POST contendo dados em formato JSON para:

    http://localhost:8080/produce

#### Exemplo de requisição:
  
```json
{
  "message": "Sua mensagem" 
}
```
### Exemplo de Resposta

```json
{
    "message": "Mensagem enviada para o Kafka"
}
```

### 2. Consumidor:

O consumidor está constantemente ouvindo as mensagens enviadas para o Kafka. Ele irá processar automaticamente as mensagens recebidas.

## 6. Encerramento do Sistema

Para encerrar o sistema, pressione `Ctrl + C` no terminal onde o Docker Compose está em execução.

## 7. Testes

Foram realizados testes para verificar a funcionalidade completa do sistema. Os testes incluem envio de requisições para o produtor e verificação do processamento das mensagens pelo consumidor.

## 8. Conclusão

Esta documentação forneceu instruções detalhadas sobre como instalar, configurar e operar o sistema de fila desenvolvido com Apache Kafka e Docker. Siga os passos fornecidos para começar a utilizar o sistema em seu ambiente local.
