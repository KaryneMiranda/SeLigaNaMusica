# Se Liga na Música: Springfield x Shelbyville

Projeto da Sprint 2 em que comparo o comportamento de usuários de um serviço de streaming de música em duas cidades, Springfield e Shelbyville, a partir dos dados de reprodução.

## Objetivo

Testar a hipótese:

> A atividade dos usuários é diferente dependendo do dia da semana e da cidade.

## Dados

| Arquivo | Conteúdo |
|---|---|
| `music_project_en.csv` | 65.079 reproduções com ID do usuário, música, artista, gênero, cidade, horário e dia da semana |

## Etapas

### 1. Visão geral dos dados
Leitura e inspeção da tabela, com identificação de problemas nos cabeçalhos, valores ausentes e duplicados.

### 2. Pré-processamento
- **Cabeçalhos:** padronização para letras minúsculas, sem espaços e em `snake_case`
- **Valores ausentes:** as colunas `track`, `artist` e `genre` tinham valores ausentes, que foram preenchidos com `unknown`
- **Duplicados explícitos:** 3.826 linhas duplicadas removidas
- **Duplicados implícitos:** os gêneros `hip`, `hop` e `hip-hop` foram unificados em `hiphop` com a função `replace_wrong_genres()`

### 3. Teste da hipótese
Criação da função `number_tracks()`, que conta as músicas tocadas em um dia e cidade específicos, aplicada às segundas, quartas e sextas-feiras.

## Principais resultados

| Dia | Springfield | Shelbyville |
|---|---|---|
| Segunda | 16.715 | 5.982 |
| Quarta | 11.755 | 7.478 |
| Sexta | 16.890 | 6.259 |

- Springfield tem cerca de **2,3 vezes mais reproduções** que Shelbyville.
- Os padrões semanais são opostos. Em Springfield, a atividade **cai na quarta-feira** e é maior na segunda e na sexta. Em Shelbyville, a **quarta-feira é o dia de maior atividade**.
- **Conclusão:** a hipótese foi confirmada. A atividade dos usuários varia conforme a cidade e o dia da semana.

> Esta análise compara contagens. Um teste estatístico formal traria uma conclusão mais precisa.

## Tecnologias

- Python
- Pandas

## Como executar

1. Clone o repositório
2. Instale as dependências:
   ```bash
   pip install pandas jupyter
   ```
3. Abra o notebook:
   ```bash
   jupyter notebook projetosprint2.ipynb
   ```

> Observação: o notebook lê o arquivo em `/datasets/music_project_en.csv`. Ajuste o caminho se o CSV estiver em outra pasta.
