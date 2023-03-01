- Importação do optuna:
    
    ```python
    import optuna
    from sklearn import model_selection
    ```
    
- Criação da função que irá executar em loop n vezes:
    
    ```python
    def objective(trial):
        max_depth = trial.suggest_int('max_depth', 4, 10)
        min_samples_split = trial.suggest_int('min_samples_split', 300, 1000)
        min_samples_leaf = trial.suggest_int('min_samples_leaf', 30, 80)
        n_estimators = trial.suggest_int('n_estimators', 50, 1000)
        max_features = trial.suggest_categorical('max_features', [None, 'sqrt'])
        class_weight = trial.suggest_categorical('class_weight', ['balanced','balanced_subsample'])
        
        clf = RandomForestClassifier(
            random_state=100, 
            max_depth=max_depth, 
            min_samples_split=min_samples_split, 
            min_samples_leaf=min_samples_leaf, 
            max_features=max_features,
            n_estimators = n_estimators,
            class_weight=class_weight,
            n_jobs=-1)
        
        score = model_selection.cross_val_score(clf, X_train, y_train, cv=5, scoring='roc_auc')
        penalized_score = score.mean() - (score.std()*0.05) # penaliza o desvio padrão
    
        return penalized_score
    ```
    
- Usando optuna:
    
    ```python
    n_tentativas = 15
    study = optuna.create_study(direction='maximize')
    study.optimize(objective, n_trials=n_tentativas)
    ```
    
- Verificando a melhor métrica:
    
    ```python
    print(f'Melhor métrica: {study.best_value}')
    ```
    
- Verificando e usando os melhores parâmetros:
    
    ```python
    print(f"Melhores hiperparâmetros: {study.best_params}")
    
    model = type_of_model(**study.best_params)
    ```