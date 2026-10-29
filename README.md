# Agamotto

Agamotto é uma aplicação web de análise de dados e correlação de ficheiros CSV, desenhada para comparar registos, identificar relações entre entidades e organizar informação num quadro visual interativo.

A ferramenta funciona em navegador, sem necessidade de backend nem dependências externas, e foi pensada para cenários de investigação, análise documental, reconciliação de dados e organização de informação dispersa em múltiplos CSVs.

## Visão geral

O projeto permite:

- importar vários ficheiros CSV/TSV em simultâneo;
- reconhecer colunas relevantes automaticamente;
- pesquisar nomes, termos e campos em diferentes fontes;
- criar cartões com registos de cada linha;
- arrastar, organizar e relacionar cartões num painel visual;
- definir tipos de ligação entre entidades;
- agrupar registros por regiões ou conjuntos de dados;
- exportar o projeto e as tabelas resultantes em CSV/ZIP;
- guardar o estado em JSON localmente no navegador.

A interface principal foi concebida como uma "mesa de trabalho" (canvas) onde cada linha de um CSV pode transformar-se em cartão, e esses cartões podem ser ligados entre si para representar relações, vínculos e hierarquias.

## Funcionalidades principais

### 1. Importação e leitura de CSVs

O Agamotto aceita ficheiros em vários formatos tabulares, incluindo:

- CSV;
- TSV;
- ficheiros de texto delimitados;
- múltiplos ficheiros em upload simultâneo.

Durante a importação, a aplicação:

- detecta o separador mais provável (vírgula, ponto e vírgula, tabulação);
- identifica as colunas da tabela;
- sugere campos-chave para busca e agrupamento;
- apresenta pré-visualização das linhas e metadados do ficheiro.

A interface também permite ajustar manualmente a configuração de cada fonte, como:

- definir colunas usadas para nome e busca;
- selecionar colunas visíveis nos cartões;
- definir colunas de agrupamento;
- indicar a coluna de imagem/PDF quando aplicável.

### 2. Pesquisa avançada dentro dos dados

A aplicação inclui um painel de pesquisa para localizar registos em qualquer CSV carregado.

As opções disponíveis incluem:

- pesquisa por termos no nome de uma entidade;
- pesquisa por cargo, função ou atributo complementar;
- pesquisa com correspondência parcial ou exacta;
- filtragem por múltiplos ficheiros;
- análise simultânea de várias fontes.

Isto permite, por exemplo, localizar rapidamente uma pessoa, instituição ou referência presente em diferentes ficheiros, mesmo que os dados estejam dispersos em estruturas distintas.

### 3. Cartões interativos e organização no canvas

Uma vez importados os dados, cada registo pode ser transformado num cartão visual. Cada cartão:

- representa uma entidade ou linha de dados;
- mostra as colunas mais relevantes;
- pode ser movido livremente no quadro;
- pode ser redimensionado;
- pode ter texto editável diretamente no painel;
- pode conter múltiplas linhas internas de informação.

Os cartões ajudam a visualizar dados de forma analítica, em vez de apenas os consultar em tabelas. O utilizador pode:

- agrupar registos por semelhanças;
- alinhar entidades em diferentes áreas do canvas;
- reorganizar manualmente a mesa de trabalho;
- criar novos cartões de forma rápida.

### 4. Correlação e relações entre entidades

Uma das funcionalidades centrais é a criação de ligações entre cartões.

O utilizador pode:

- selecionar dois cartões;
- definir o tipo de relação;
- indicar se a ligação é firme ou hipotética;
- adicionar nota e autor/data;
- manter um histórico visual das relações criadas.

Tipos de relação podem ser personalizados, por exemplo:

- mesma pessoa;
- marido e mulher;
- pai/mãe e filho(a);
- senhor e escravo;
- outras relações definidas pelo utilizador.

As ligações podem ser visualizadas por linhas com diferentes cores e estilos, e podem ser marcadas como descartadas ou exibidas/ocultadas conforme o contexto.

### 5. Regiões, agrupamentos e organização da mesa

Além dos cartões, a aplicação permite criar regiões no canvas, úteis para:

- agrupar entidades por categoria;
- marcar grupos de investigação;
- organizar áreas por contexto geográfico, temporal ou temática;
- delimitar subconjuntos de trabalho no quadro.

As regiões podem ser movidas, redimensionadas e coloridas de acordo com a análise em curso.

### 6. Gestão de origem e rastreabilidade

Cada cartão pode conservar a origem do dado, mantendo referência ao:

- ficheiro CSV;
- linha do CSV;
- coluna de origem;
- contexto de proveniência.

Isto é especialmente útil em cenários de investigação, porque o utilizador consegue verificar rapidamente a fonte original da informação e confirmar a sua rastreabilidade.

### 7. Fonte completa e inspeção dos dados

A aplicação disponibiliza a visualização da informação completa da fonte de um cartão ou registo.

A partir desta vista é possível:

- consultar todas as colunas de uma linha;
- verificar dados originais que não foram expostos no cartão;
- confirmar metadados e valores que justificam a relação criada.

### 8. Exportação de dados e projetos

O Agamotto oferece recursos de exportação para facilitar a continuidade do trabalho:

- exportação do projeto em JSON;
- salvamento local no navegador;
- abertura de projetos guardados;
- exportação das tabelas para ficheiros CSV em ZIP;
- exportação de diferentes datasets relacionados, como cartões, linhas, ligações, regiões e tipos.

O ficheiro exportado inclui tabelas estruturadas com informação relevante para análise posterior em Excel, LibreOffice, Python ou outros ferramentas de processamento de dados.

### 9. Ambiente local e sem instalação

O projeto é um front-end estático em HTML, CSS e JavaScript. Não exige:

- servidor de aplicação;
- base de dados;
- compilação;
- instalação de pacotes;
- dependências externas.

Pode ser aberto diretamente no navegador ou servido localmente com um pequeno servidor simples, por exemplo:

```bash
python -m http.server 8000
```

Em seguida, aceda a:

```text
http://localhost:8000
```

## Estrutura do repositório

```text
Agamotto/
├── index.html
├── README.md
└── (arquivos gerados pelo utilizador em execução)
```

## Como utilizar

### Passo 1: abrir a aplicação

Abra o ficheiro `index.html` no navegador ou inicie um servidor local.

### Passo 2: importar fontes de dados

Clique no botão de importação e carregue um ou mais ficheiros CSV/TSV. O sistema irá interpretar os dados e mostrar as tabelas carregadas.

### Passo 3: pesquisar e explorar

Use o painel de busca para localizar registos, acrescentar filtros e navegar pelos ficheiros carregados.

### Passo 4: criar cartões

A partir de uma linha ou registro, crie um cartão no canvas. Pode personalizar o conteúdo visível, mover o cartão e ajustar o layout do trabalho.

### Passo 5: definir relações

Selecione dois cartões e marque a relação entre eles. Escolha o tipo de ligação, a certeza da associação e anote detalhes adicionais.

### Passo 6: guardar ou exportar

Quando terminar a análise:

- guarde o projeto em JSON;
- exporte as tabelas em CSV/ZIP;
- mantenha as fontes orginais e o estado da mesa para trabalhos futuros.

## Casos de uso

O Agamotto é particularmente útil para:

- análise de bases de dados com múltiplas fontes;
- reconciliação de registos de pessoas, eventos ou entidades;
- correlação de dados de investigação histórica ou documental;
- gestão de fontes e vínculos em projetos analíticos;
- organização visual de informação dispersa em CSVs;
- exploração de dados em ambientes semi-estruturados.

## Tecnologias

- HTML5
- CSS3
- JavaScript vanilla
- navegador moderno

## Limitações e considerações

Como é uma aplicação estática e focada no navegador, a ferramenta é ideal para fluxos de análise local e interativa. Em cenários de grande escala ou com requisitos de colaboração multiutilizador, pode ser necessário evoluir para uma solução com backend e persistência centralizada.

## Contribuição

Este repositório admite evolução simples, pois a lógica principal está concentrada num único ficheiro HTML. Se quiser contribuir:

1. faça um fork do projeto;
2. crie uma branch para a funcionalidade;
3. implemente a melhoria;
4. teste a experiência no navegador;
5. abra um pull request com descrição clara.

## Licença

Até ao momento, não foi especificada uma licença formal no repositório. Caso pretenda usar o projeto em contexto profissional ou académico, recomenda-se verificar a política de uso antes de reutilizar o código.

## Resumo

O Agamotto é uma ferramenta visual de análise e correlação de CSVs, concebida para transformar dados tabulares em uma "mesa de investigação" rica em relações, contexto e rastreabilidade. A sua proposta central é facilitar a compreensão de grandes volumes de informação, permitindo que o utilizador organize, pesquise, relacione e exporte dados de forma intuitiva e prática.

---

Se quiser, posso também criar uma versão do README mais curta e mais "profissional de GitHub" ou uma versão com foco em demonstração de funcionalidades e screenshots estilizados.
