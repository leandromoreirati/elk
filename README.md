![alt tag](https://images.contentstack.io/v3/assets/bltefdd0b53724fa2ce/blt9a6279ac82c4aac5/5c11ebcf5b046c520d3f7506/logo-elastic-stack-lt.svg)

"ELK" é o acrônimo para três projetos de código aberto: Elasticsearch, Logstash e Kibana. O Elasticsearch é um mecanismo de pesquisa e análise. O Logstash é um pipeline de processamento de dados do lado do servidor que insere dados de várias fontes simultaneamente, os transforma e envia para um "stash", como o Elasticsearch. Kibana permite que os usuários visualizem dados com gráficos e tabelas no Elasticsearch

# SERVIÇOS
 - O Elasticsearch é um mecanismo distribuído de pesquisa e análise RESTful capaz de solucionar um número crescente de casos de uso. Como o coração do Elastic Stack, ele centraliza os dados armazenados para que você possa descobrir o esperado e descobrir o inesperado.
Logstash:
 - O Logstash é um pipeline de processamento de dados de código-fonte aberto, que insere dados de várias fontes simultaneamente, transforma e envia para o seu "stash" .
Kibana:
 - O Kibana permite que você visualize os dados do Elasticsearch e navegue no Elastic Stack, para que você possa fazer qualquer coisa.
Metricbeat:
 - Colete métricas de seus sistemas e serviços. Da CPU à memória, do Redis ao NGINX e muito mais, o Metricbeat é uma maneira leve de enviar estatísticas de sistema e serviço.
Filebeat
 - Esqueça o uso do SSH quando você tem dezenas, centenas ou até milhares de servidores, máquinas virtuais e containers gerando logs. O Filebeat ajuda você a simplificar as coisas simples, oferecendo uma maneira leve de encaminhar e centralizar logs e arquivos.

A stack de serviços e composta por um cluster do elasticsearch com 2 nos, além dos serviços do logstash, kibana, filebeat e metricbeat.

# NOTAS DE VERSÃO
°  Versão 1.0 - 01/02/2019 ==> Criação e configuração do composefile.

# PRÉ-REQUISITO
Os pre-requisitos necessários para execução da stack de serviço:
 1) Docker Instalado e configurado.
 2) Docker Swarm configurado.

# INSTALANDO E CONFIGURANDO DOCKER
   curl -fsSL https://get.docker.com | bash

# INSTALANDO DOCKER SWARM
   docker swarm init --advertise-addr  <IP_DO_SERVIDOR>

   Onde <IP_DO_SERVIDOR> deve ser substituído pelo ip do seu servidor.

# BAIXANDO AS IMAGENS
 
   docker pull elasticsearch:6.5.0
   docker pull elasticsearch:6.5.0
   docker pull kibana:6.5.0
   docker pull logstash:6.5.0
   docker pull filebeat:6.5.0
   docker pull metricbeat:6.5.0
   
# CLONANDO O REPOSITÓRIO E INICIANDO O SERVIÇO
git clone https://github.com/leandromoreirati/elk.git
cd elk
docker stack deploy -c docker-compose.yml elk
