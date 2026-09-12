\documentclass[12pt, a4paper]{article}
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[portuguese]{babel}
\usepackage{amsmath}
\usepackage{geometry}

\geometry{a4paper, margin=2cm}

\title{\textbf{RELATÓRIO DE ANÁLISE EXPERIMENTAL: MOVIMENTO RETILÍNEO UNIFORME}}
\author{Helisson Fabiano \and Matheus Fideles}
\date{}

\begin{document}

\maketitle

\section*{Fundamentação Teórica}

De acordo com o livro \textit{Fundamentos de Física, Volume 1: Mecânica} (10ª edição, de Halliday, Resnick e Walker):

"A física estuda como os objetos se movem, seja a sua rapidez ou a distância que percorrem. Para facilitar o estudo de objetos se movendo em linha reta, usa-se o \textbf{modelo de partícula}. Nele, imaginamos que todas as partes do objeto se movem na mesma direção e com a mesma velocidade, como se o objeto inteiro fosse um único ponto.

A posição de um objeto é definida usando um ponto de referência inicial. O \textbf{deslocamento} é a diferença entre onde o objeto começou e onde ele terminou o movimento. A partir disso, definimos a \textbf{velocidade média ($v_{\text{méd}}$)} como a razão entre o deslocamento ($\Delta x$) e o tempo que durou o movimento ($\Delta t$), calculada por:
\begin{equation}
v_{\text{méd}} = \frac{\Delta x}{\Delta t}
\end{equation}              "

\section*{Resolução das Questões 1 a 18}

O notebook utilizado para resolver os exercícios abaixo pode ser acessado pelo link
\\{https://github.com/HelissonFabiano/Experimento-Movimento-Uniforme-com-Python/blob/main/ExperimentoMU.ipynb}



\subsection*{1. Montagem e Procedimento Experimental (Passos 1 a 6)}

\textbf{Passos 1 a 3:} A montagem do experimento iniciou-se com o nivelamento da base de sustentação e a elevação do plano a 15º acima da horizontal. O roteiro orienta o registro da menor divisão da escala do plano inclinado (régua milimetrada, com precisão de 1 mm) e do cronômetro (0,01 s), grandezas que definem os limites de erro instrumental. 

\textbf{Passos 4 a 6:} A esfera foi posicionada na marca inicial $x = 0$ mm com auxílio de um ímã e liberada simultaneamente ao disparo do cronômetro. O tempo foi travado ao cruzar a marca de $x = 400$ mm. Esse procedimento foi repetido até a obtenção de 30 medidas, as quais foram registradas para análise.

\subsection*{2. Análise dos Dados de Tempo (Passos 7 a 15)}

O tratamento estatístico dos tempos medidos foi executado utilizando a biblioteca Pandas no Python, cujos resultados atendem aos passos do roteiro:

\textbf{Passo 7:} A média dos intervalos de tempo foi calculada somando-se os 30 valores e dividindo-se pelo total de amostras, resultando em $\overline{t} = 6,366\text{ s}$. 

\textbf{Passos 8 e 9:} As discrepâncias individuais e seus respectivos quadrados foram processadas em colunas dedicadas. A soma dos quadrados das discrepâncias resultou em $\sum d_{i}^{2} = 1,01552\text{ s}^{2}$. 

\textbf{Passo 10:} O desvio-padrão da distribuição amostral é de aproximadamente $\sigma_t = 0,187\text{ s}$. 

\textbf{Passo 11:} Aplicou-se o critério de rejeição de dados verificando se alguma discrepância absoluta ultrapassava 3$\sigma_t \text{ }$(aproximadamente $0,561\text{ s}$). O código Python retornou um dataframe vazio para esta condição (\texttt{dados[dados['Di'] > 3*desvpad]}), provando que nenhum dado precisou ser descartado. 

\textbf{Passos 12 e 13:} A incerteza padrão da média foi de aproximadamente $u_t = 0,034\text{ s}$. 

\textbf{Passo 14:} A média deve ser arredondada para ter o mesmo número de casas decimais que a sua incerteza. Como 0,034 possui três casas decimais, o valor 6,366 já está arredondado. 

\textbf{Passo 15:} O resultado final da medida de tempo é 
$\overline{t} = (6,366 \pm 0,034)\text{ s}$.

\subsection*{3. Cálculo da Velocidade Média (Passos 16 a 18)}

Com os dados de tempo processados e considerando (1):

\textbf{Passo 16:} A melhor estimativa para a velocidade média é de $v_m = 0,0628\text{ m/s}$. 

\textbf{Passo 17:} A propagação de erros relativos é de $u_{v_m} = 0,000335\text{ m/s}$. 

\textbf{Passo 18:} Aplicando a regra de arredondamento de incertezas (adotando 1 algarismo significativo) arredondamos o erro para $0,0003\text{ m/s}$ e ajustamos as casas decimais da velocidade. O resultado final para a velocidade média consolida-se em: $v_m = (0,0628 \pm 0,0003)\text{ m/s}$.

\end{document}
