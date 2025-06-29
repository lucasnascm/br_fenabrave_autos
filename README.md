# Relatórios Fenabrave
A Fenabrave (Federação Nacional da Distribuição de Veículos Automotores) produz diversos estudos, dentre eles, Emplacamentos e Seminovos e Usados. Consiste em relatórios em pdf divulgados mensalmente com os resultados das transações de veículos novos e usados ocorridas no Brasil no período de referência. Na página inicial de cada arquivo consta os valores consolidados por segmento, isto é, o total transacionado por segmento (autos, comerciais leves, caminhão, ônibus, motos...). Nas páginas seguintes, são apresentados alguns gráficos e tabelas. O ponto focal desde processo de ETL, além da captura, é a leitura dos arquivos .pdf tabulando a tabela com o total mensal por segmento e o ranking dos 50 Automóveis e dos 50 Comerciais Leves mais vendidos, tanto para usados quanto novos.

## Estrutura do Projeto
```
br_fenabrave_autos/
├── code/
│   ├── [ETL] scraping.ipynb
│   ├── [ETL] treatment.ipynb
│   └── [ETL] analysis.ipynb
├── input/
│   ├── novos
│   ├── usados
├── output/
│   └── clip_used_fenabrave.mp4
├── requirements.txt
└── README.md
```

A pasta ```code/``` contém os scripts em Jupyter-Notebook que realiza a extração e tratamento. Também contém um de análise que cria um bar chart race com os 20 modelos de Autos usados mais comercializados durante 20 anos.

A pasta ```input/``` é a estrutura criada para armazenar os relatórios após download, tanto novos quanto usados. 

A pasta ```output/``` armazena os arquivos resultado do pós-tratamento e análises geradas, como gráficos e vídeos. Não há tabela, a princípio, dado que na etapa final do tratamento, gera-se um Google Sheets com a tabela completa. Se você deseja este arquivo, sinta-se a vontade para entrar em contato lucas.nasc.m@gmail.com ou https://www.linkedin.com/in/moreiranlucas/


## Next Steps
[ ] O código de tratamento requer ainda mais refinamento. 
    Exemplo: Alguns modelos que contém números em seu nome (Sprinter 315, Tigger 3, etc.), pelo regex, sobrescrevem o resultado da tabela
[ ] Aplicar o bar chart race aos novos mais vendidos a partir de 2003
[ ] Criar novas análises, como substituição de frota ou match de inventário
[ ] Incrementar com outros dados: tabela Fipe, frota dos municípios 
