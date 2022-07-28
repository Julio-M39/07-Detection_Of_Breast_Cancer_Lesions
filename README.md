# Detection_Of_Breast_Cancer_Lesions

## Detecção de Lesões de Câncer de Mama em Imagens Histopatológicas

### Definição do Projeto

O câncer de mama é a forma mais comum de câncer em mulheres. Identificar e categorizar com precisão os subtipos de câncer de mama é uma tarefa clínica importante e métodos automatizados podem ser usados para economizar tempo e reduzir erros. O processo que é usado para detectar o câncer de mama é demorado e pequenas áreas malignas podem ser perdidas. Com isso podemos utilizar o aprendizado profundo para classificar os subtipos de câncer e otimizar o trabalho dos especialistas.

**Classificação de Câncer de Mama**

Para detectar o câncer, uma seção de tecido é colocada em uma lâmina de vidro. Um patologista então examina esta lâmina sob um microscópio. O patologista precisa escanear visualmente grandes regiões onde não há câncer, a fim de encontrar áreas malignas. Como essas lâminas de vidro agora podem ser digitalizadas, a visão computacional pode ser usada para acelerar o fluxo de trabalho de um patologista e fornecer suporte ao diagnóstico. Ao implantar uma solução de aprendizado de máquina ela pode ser disponibilizada para a equipe médica em qualquer lugar do mundo.

Abaixo temos algumas imagens histopatológicas para esse problema, onde 0 são imagens que não possuem Carcinoma Ductal Invasivo (IDC), enquanto em 1, são as imagens positivas.

<div>
<img src="https://user-images.githubusercontent.com/54995990/181391611-feb8597d-d20a-4a47-890b-77a1b47b3075.png" width="500px" />
</div>

O Carcinoma Ductal Invasivo (IDC) é o subtipo mais comum de todos os cânceres de mama. Para atribuir um grau de agressividade a uma amostra, os patologistas geralmente se concentram nas regiões que contêm o IDC. Como resultado, uma das etapas comuns de pré-processamento para classificação automática de agressividade é delinear as regiões exatas do IDC dentro de um slide de montagem inteiro.

Referências:

<a href="https://pubmed.ncbi.nlm.nih.gov/27563488/">Deep learning for digital pathology image analysis: A comprehensive tutorial with selected use cases</a>

<a href="http://www.oncoguia.org.br/conteudo/cancer-de-mama-invasivo/1387/34/">Câncer de Mama Invasivo</a>

<a href="https://www.researchgate.net/publication/263052166_Automatic_detection_of_invasive_ductal_carcinoma_in_whole_slide_images_with_Convolutional_Neural_Networks">Automatic detection of invasive ductal carcinoma in whole slide images with Convolutional Neural Networks</a>

**Base de Imagens**

As imagens consistem em slides inteiros de espécimes de câncer de mama escaneados a 40x. A partir daí, 277.524 patches de tamanho 50 x 50 foram extraídos (198.738 IDC negativos e 78.786 IDC positivos). 

O nome de arquivo de cada patch está no formato: uxXyYclassC.png -> exemplo 10253idx5x1351y1101class0.png. Onde u é a ID do paciente (10253idx5), X é a coordenada x de onde este patch foi cortado, Y é a coordenada y de onde este patch foi cortado e C indica a classe sendo 0 é não-IDC e 1 é IDC.

Fonte de Dados:

https://lhncbc.nlm.nih.gov/publication/pub9931

### Etapas do Projeto

**Primeira Etapa:**

- Extração de informação dos datasets
- Ajustes e organização
- Divisão em treinamento, validação e teste
- Criação de diretórios para armazenar as imagens
- Pré-processamento
- Armazenamento das imagens 

**Segunda Etapa:**

- Criação do modelo
- Definição dos hiperparâmetros
- Criação da arquitetura
- Compilação
- Definição do checkpoint
- Definição do Reduce on Plateau
- Treinamento do modelo
- Curvas do aprendizado

**Terceira Etapa:**

- Carregamento do modelo
- Previsões nos dados de teste
- Matriz de confusão
- Relatório de classificação

### **Resultados**

Para os resultados, plotamos uma matriz e um relatório de classificação que podem ser visto na imagem abaixo:

<div>
<img src="https://user-images.githubusercontent.com/54995990/181393361-370044e5-8acd-409c-9b6a-dfd1d5ac71d8.png" width="600px" />
</div>

No geral, o modelo apresenta um bom equilíbrio, embora ainda tenhamos espaço para melhorias. O modelo pode ser melhorado com uma otimização dos parâmetros utilizados na rede, modificações na arquitetura da rede e aplicação de pré-processamento nas imagens. 
