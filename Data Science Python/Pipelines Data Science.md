# Pipelines Data Science

- Importação que faz a criação do Pipeline e as ferramentas de pré-processamento:
    
    ```python
    from sklearn.pipeline import Pipeline
    from sklearn.compose import ColumnTransformer
    from sklearn.impute import SimpleImputer
    from sklearn.preprocessing import OneHotEncoder
    ```
    
- Processamento de dados nulos:
    
    ```python
    numerical_transformer = SimpleImputer(strategy='constant')
    ```
    
- Processamento de dados categóricos:
    
    ```python
    categorical_transformer = Pipeline(steps=[
    	('imputer', SimpleImputer(strategy='most_frequent')),
    	('onehot', OneHotEncoder(handle_unknown='ignore'))
    ])
    ```
    
- Criação do Pipeline completo:
    
    ```python
    preprocessor = ColumnTransformer(
    	transformers=[
    		('num', numerical_transformer, numerical_cols),
    		('cat', categoriacal_transformer, categorical_cols)
    	]
    )
    ```
    
    - numerical_cols são os nomes das colunas que são numéricas
    - categorical_cols são os nomes das colunas que são strings (categóricas)
- Juntando o Pipeline com o modelo:
    
    ```python
    model = type_of_model(**params)
    
    clf = Pipeline(steps=[
    	('preprocessor', preprocessor).
    	('model', model)
    ])
    ```