# Otimização Computacional: Projeto de Tanque Cilíndrico

Este repositório contém a implementação computacional de um algoritmo numérico de otimização para resolver um problema clássico de engenharia: minimizar o custo de fabricação de um tanque de armazenamento cilíndrico, garantindo o respeito a uma restrição de desigualdade referente ao volume mínimo do reservatório.

##  Objetivo do Projeto
Determinar as dimensões ótimas de raio e altura que minimizem o custo total de construção do tanque (base, lateral e teto). O tanque deve obrigatoriamente armazenar um volume mínimo.

## Fundamentação Matemática
O algoritmo foi desenvolvido em Python estruturado, dispensando bibliotecas de otimização prontas para demonstrar o domínio sobre os métodos numéricos. A solução utiliza uma combinação das seguintes técnicas:

1. **Função de Penalização:** Transformação do problema restrito (limite de volume) em um problema irrestrito através da adição de uma multa $\mu$ ao custo caso o volume projetado seja inferior ao exigido.

2. **Derivadas Parciais Numéricas:** Cálculo da inclinação (gradiente) da função objetivo utilizando o método de *Diferenças Finitas Simples Adiantadas* (com um passo infinitesimal $\Delta$).
3. **Método do Gradiente (Gradient Descent):** Laço iterativo que atualiza progressivamente as dimensões do tanque na direção de descida máxima (contrária ao gradiente), regulado por uma taxa de aprendizado (passo $\alpha$).

## Resultados Obtidos
Após a sintonia dos parâmetros numéricos ($\alpha = 10^{-8}$ e $\mu = 10^6$), o algoritmo obteve convergência com as seguintes dimensões ótimas:
- **Raio Ótimo:** $3.9676\text{ m}$
- **Altura Ótima:** $10.6488\text{ m}$
- **Volume Final:** $526.64\text{ m}^3$ (Restrição de $500\text{ m}^3$ satisfeita)
- **Custo Mínimo Total:** **R\$ 43.856,11**

##  Estrutura do Repositório
- `otimizacao.ipynb`: Notebook Jupyter principal contendo toda a modelagem matemática, o motor do método do gradiente e as análises de sensibilidade.

- `convergence_alpha.png`: Gráfico gerado demonstrando a evolução da convergência para diferentes taxas de aprendizado ($\alpha$).

- `convergence_mu.png`: Gráfico gerado demonstrando a evolução da convergência sob diferentes constantes de penalidade ($\mu$).

- `.gitignore`: Arquivo de configuração de exclusão de pastas locais (como o ambiente virtual).


## Como Executar

Para rodar este projeto em um ambiente local isolado (recomendado para Linux Mint/Ubuntu):

1. **Clone o repositório:**

   ```bash
   git clone [https://github.com/napilots/tank-cost-optimization.git](https://github.com/napilots/tank-cost-optimization.git)
   cd tank-cost-optimization
    ```

2. **Crie o ambiente virtual:**
   ```bash
   python3 -m venv env_tanque
   source env_tanque/bin/activate
   ```
   
3. **Instale as dependências:**
   ```bash
   pip install notebook matplotlib
   ```

4. **Inicie o Jupyter Notebook:**

   ```bash
   jupyter notebook
   ```

# Autoras:
* Ana Clara Lima
* Alice de Souza Barbosa
