
# Kafka, Zookeeper e Kafdrop com Docker Compose

Este repositório contém um exemplo de configuração do Kafka e Zookeeper utilizando o Docker Compose. A configuração também inclui o Kafdrop, uma interface web para visualizar os tópicos e mensagens no Kafka.

## Pré-requisitos

- Docker instalado. Você pode seguir as instruções de instalação no [site oficial do Docker](https://docs.docker.com/get-docker/).
- Docker Compose instalado. O Docker Desktop já vem com o Docker Compose, mas se você estiver em um ambiente Linux, pode precisar instalá-lo separadamente. Veja [como instalar o Docker Compose](https://docs.docker.com/compose/install/).

## Estrutura dos Serviços

O arquivo `docker-compose.yml` define os seguintes serviços:

1. **Zookeeper**: Responsável por gerenciar a configuração do Kafka. O Zookeeper escuta na porta 2181.
2. **Kafka**: Broker de mensagens que se conecta ao Zookeeper. O Kafka está configurado para expor a porta 9092 para conexões externas e a porta 29092 para conexões internas entre os containers.
3. **Kafdrop**: Uma interface web para monitorar os tópicos, partições e mensagens no Kafka. O Kafdrop está disponível na porta 19000.

## Uso

1. Clone este repositório:

   ```bash
   git clone https://github.com/williamsartijose/kafka-docker-compose.git
   cd kafka-docker-compose
   ```

2. Inicie os serviços com o Docker Compose:

   ```bash
   docker-compose up -d
   ```

3. Verifique o status dos containers:

   ```bash
   docker-compose ps
   ```

4. Acesse o Kafdrop no seu navegador em [http://localhost:19000](http://localhost:19000).

5. Para visualizar os logs dos serviços:

   ```bash
   docker-compose logs -f
   ```

6. Para parar os serviços:

   ```bash
   docker-compose down
   ```

7. Se quiser parar os serviços e remover os volumes associados:

   ```bash
   docker-compose down -v
   ```

## Imagens Utilizadas

- **Zookeeper**: [confluentinc/cp-zookeeper](https://hub.docker.com/r/confluentinc/cp-zookeeper)
- **Kafka**: [confluentinc/cp-kafka](https://hub.docker.com/r/confluentinc/cp-kafka)
- **Kafdrop**: [obsidiandynamics/kafdrop](https://hub.docker.com/r/obsidiandynamics/kafdrop)

## Docker Hub

Clique na imagem abaixo para acessar o Docker Hub e obter mais informações sobre as imagens utilizadas neste projeto.

[![Docker Hub](https://www.docker.com/wp-content/uploads/2023/08/logo-guide-logos-1.svg)](https://hub.docker.com/)

## Personalização

Você pode ajustar as configurações no arquivo `docker-compose.yml` conforme necessário, como a modificação das portas ou dos parâmetros de ambiente.



