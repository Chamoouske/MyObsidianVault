- Importação das libs que calculam as métricas:
    
    ```python
    from sklearn.metrics import precision_score, recall_score, accuracy_score, roc_auc_score
    ```
    
- Função que printa as métricas:
    
    ```python
    def print_metrics(clf, X, y):
      y_pred = clf.predict(X)
      y_prob = clf.predict_proba(X).T[1]
    
      acuracia = accuracy_score(y, y_pred)
      sensibilidade = recall_score(y, y_pred)
      especificidade = recall_score(y, y_pred, pos_label=0)
      precisao = precision_score(y, y_pred)
      auc = roc_auc_score(y, y_prob)
    
      print(f'Acurácia: {acuracia:.2f}')
      print(f'Sensibilidade (recall): {sensibilidade:.2f}')
      print(f'Especificidade: {especificidade:.2f}')
      print(f'Precisão: {precisao:.2f}')
      print(f'AUC: {auc:.2f}')
    ```