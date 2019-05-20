# Petros
#### API - Captura Novas ações
#### API - Web
#### API - Sincronização de Processos
#### API - Sincronização de Publicações

# Instalação

###### Assemblies
- assembly-captura-novas-acoes
- assembly-sincronizacao-publicacao
- assembly-web

###### Maven
<pre>
mvn clean install -P prod|dev
</pre>
# Execução
<pre>
java -jar -Dspring.profiles.active=prod|dev applicacao.jar
</pre>
# Docker
###### Docker Compose (Exemplo)
<pre>
version: '3'
services:
    nome-do-projeto:
        build:
            context: ./
        container_name: nome-do-projeto
        restart: always
        volumes:
            - "./public/:/public"
        environment:
            - "TZ=America/Sao_Paulo"
            - "SPRING_PROFILES_ACTIVE=dev"
            - "crawler.application.name=Finch Soluções - Petros"
            - "crawler.queue.prefix=finch-automacao"
            - "crawler.queue.consumer.name=petros"
            - "crawler.exchange.name=petros"
            - "crawler.exchange.routing-key=cnj"
            - "crawler.max-consumers=1"
        network_mode: bridge
</pre>

# Jenkins
##### Configuração# petros
