# DashON

Sistema web para análise de gargalos de hardware e recomendação térmica, desenvolvido para auxiliar entusiastas e montadores de PCs a escolherem a melhor combinação entre processador, placa de vídeo e sistema de resfriamento.

📌 Sobre o Projeto

O DashON é uma aplicação web que permite ao usuário selecionar componentes de hardware e obter uma análise da compatibilidade entre eles.

O sistema calcula possíveis gargalos entre CPU e GPU, exibindo uma porcentagem estimada de limitação de desempenho, além de fornecer recomendações de refrigeração com base no consumo energético e na geração de calor dos componentes escolhidos.

O objetivo é tornar a montagem de computadores mais acessível, ajudando usuários a evitar combinações desequilibradas que possam comprometer o desempenho do sistema.

🚀 Tecnologias Utilizadas
Backend
Java 21
Spring Boot
Spring Web
Spring Data JPA
Maven
Frontend
HTML5
CSS3
JavaScript (Vanilla JS)
Banco de Dados
MySQL
Ferramentas
Git
GitHub
Postman
IntelliJ IDEA
🎯 Funcionalidades
Análise de Gargalo
Seleção de processador.
Seleção de placa de vídeo.
Cálculo de percentual de gargalo.
Classificação do resultado:
0% a 5% → Excelente combinação.
5% a 10% → Boa combinação.
10% a 20% → Atenção.
Acima de 20% → Gargalo significativo.
Recomendação Térmica

O sistema sugere o método de resfriamento adequado:

Consumo estimado	Recomendação
Até 95W	Cooler Box ou Air Cooler básico
95W - 150W	Air Cooler intermediário
150W - 220W	Air Cooler Premium ou Water Cooler 240mm
Acima de 220W	Water Cooler 240mm ou superior
Dashboard Interativo
Exibição gráfica dos resultados.
Indicadores visuais de desempenho.
Interface responsiva para desktop e mobile.
Base de Componentes
Processadores AMD Ryzen Série 5000.
Processadores AMD Ryzen Série 7000.
GPUs NVIDIA RTX Série 3000.
GPUs NVIDIA RTX Série 4000.
GPUs NVIDIA RTX Série 5000.
📊 Como Funciona o Cálculo de Gargalo

O cálculo utiliza uma pontuação de desempenho para CPU e GPU baseada em benchmarks previamente cadastrados.

Exemplo:

Ryzen 5 5500 = 100 pontos
RTX 5050 = 110 pontos

Gargalo = |CPU - GPU| / GPU * 100

Gargalo = |100 - 110| / 110 * 100
Gargalo = 9,09%

Quanto menor o percentual obtido, melhor a sinergia entre os componentes.

🏗️ Arquitetura do Projeto
Frontend (HTML/CSS/JS)
          │
          ▼
     Spring Boot API
          │
          ▼
   Serviço de Análise
          │
 ┌────────┴────────┐
 ▼                 ▼
Cálculo       Recomendação
de Gargalo      Térmica
          │
          ▼
       MySQL
       
📂 Estrutura de Pastas
hardware-bottleneck-analyzer/
│
├── backend/
│   ├── controller/
│   ├── service/
│   ├── repository/
│   ├── model/
│   └── dto/
│
├── frontend/
│   ├── css/
│   ├── js/
│   ├── assets/
│   └── index.html
│
├── database/
│   └── scripts.sql
│
└── README.md

🔧 Instalação
Clone o repositório
git clone https://github.com/seu-usuario/hardware-bottleneck-analyzer.git
Entre no diretório
cd hardware-bottleneck-analyzer
Configure o banco de dados
CREATE DATABASE hardware_analyzer;
Execute o Backend
mvn spring-boot:run

Servidor iniciado em:

http://localhost:8080
Execute o Frontend

Abra o arquivo:

frontend/index.html

ou utilize uma extensão como Live Server.

📡 Exemplo de Endpoint
Analisar Configuração

POST

/api/analisar
Requisição
{
  "cpu": "Ryzen 5 5500",
  "gpu": "RTX 5050"
}
Resposta
{
  "gargalo": 9.09,
  "classificacao": "Boa combinação",
  "refrigeracao": "Air Cooler intermediário"
}

🔮 Melhorias Futuras
Comparação entre múltiplas configurações.
Integração com APIs de preços.
Sistema de montagem completa de PC.
Histórico de análises.
Cadastro de usuários.
Dashboard com gráficos utilizando Chart.js.
Suporte para processadores Intel.
Estimativa de FPS em jogos populares.
Consumo total da fonte recomendado.
👨‍💻 Autor

Luiz Gustavo
Estudante de Sistemas de Informação - UNIVAS

📜 Licença

Este projeto é distribuído sob a licença MIT. Sinta-se livre para estudar, modificar e contribuir.
