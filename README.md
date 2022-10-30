# Performance usando de APIs do TensorFlow Estimator 

- TensorFlow v1.4

## Performance usando as APIs do TF

* projetos de ML, atualmente abrangendo:
  * Classificação
  * Regressão
  * Agrupamento (k-médias)
  * Análise de séries temporais (modelos AR)
  * Redução de Dimensionalidade (Autoencoding)
  * Modelos Sequenciais (RNN e LSTMs)
  * Análise de Imagens (CNN para Classificação de Imagens)
  * Análise de texto (classificação de texto com embeddings, CNN e RNN)
* Como usar **estimadores predefinidos** para treinar modelos de ML.
  
* Como implementar **estimadores personalizados** (model_fn e EstimatorSpec).

* Uma abordagem padrão **orientada por metadados** para criar o modelo **coluna_recurso**(s), incluindo:
  * **características numéricas**
  * Recursos **categóricos** com **vocabulário**,
  * **categórico** apresenta **hash bucket** e
  * Recursos **categóricos** com **identidade**

* Dados **pipelines de entrada** (input_fn) usando:
  * tf.estimator.inputs.**pandas_input_fn**,
  * tf.train.**string_input_producer** e
  * APIs tf.data.**Dataset** para ler arquivos de dados **.csv** e **.tfrecords** (tf.example)
  * tf.contrib.timeseries.**RandomWindowInputFn** e **WholeDatasetInputFn** para dados de série temporal
  * Recurso **pré-processamento** e **criação** como parte da leitura de dados (input_fn), por exemplo, sin, sqrt, expansão polinomial, transformada de Fourier, log, comparações booleanas, distância euclidiana, fórmulas personalizadas etc.

* Uma abordagem padrão para preparar feature_column(s) **wide** (esparse) e **deep** (dense) para wide and deep **DNN Liner Combined Models**

* O uso de **normalizer_fn** em numeric_column() para **escalar** os recursos numéricos usando estatísticas pré-computadas (para escala Mín-Máx ou Padrão)

* O uso de **weight_column** nos estimadores predefinidos e na métrica de perda nos estimadores personalizados.

* **Engenharia de recursos** implícita como parte da definição de feature_colum(s), incluindo:
  * cruzando,
  * recorte,
  * Incorporação,
  * indicadores (codificando recursos categóricos) e
  * bucketização
  * Como usar as APIs tf.contrib.learn.**experiment** para treinar, avaliar e exportar modelos

* Como usar a função tf.estimator.**train_and_evaluate** (junto com trainSpec e evalSpec) treinar, avaliar e exportar modelos

* Como usar a função **tf.train.exponential_decay** como um agendador de taxa de aprendizado

* Como **servir** o modelo exportado (export_savedmodel) usando entradas **csv** e **json**

## Em breve:
* Implementação de parada antecipada
* DynamicRnnEstimator e o uso de sequências de comprimento variável
* Filtragem Colaborativa para Modelos de Recomendação
* Análise de texto (Modelos de tópicos, incorporação de Word/Doc, etc.)
* tf.Transform para pré-processamento e engenharia de recursos
* exemplos de keras
