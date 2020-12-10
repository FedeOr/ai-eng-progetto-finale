# Progetto AI Engineering - Team 2

Il progetto consiste in un'applicazione Python che consente di visualizzare la base dati riguardante le informazioni registrate dai sensori del sistema domotico di RETI S.p.A. e grazie ad un modello di AI analizza i dati fornendo una stima delle **anomalie** presenti.

Il modello utilizzato per rilevare le eventuali anomalie all'interno del dataset è: [Isolation Forest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.IsolationForest.html#sklearn.ensemble.IsolationForest).

L'interfaccia è realizzata tramite la libreria Python `Streamlit` e le predizioni sono calcolate dal modello salvato tramite **Databricks** su Azure.

## Struttura folder del progetto

- **StreamlitCampus**

  | File | Description |
  | --- | --- |
  | app.py | script python contenente l'interfaccia creata con Streamlit |
  | load_setting.py | creato per recepire le informazioni salvate tramite formato .json |
  | requirements.txt | file contenente tutte le librerie necessarie per il funzionamento del progetto |
  
  - **images**
  
    _Folder contenente le immagini utilizzate per l'interfaccia finale_
  
  - **src**
  
    - **features**
      
      | File | Description |
      | --- | --- |
      | preprocess.py | utilizzato per le funzioni di trasformazione e preprocessing del dataset |
      | read_data.py | creato per connettersi al database e eseguire query d'estrazione |
    
    - **model**
    
      | File | Description |
      | --- | --- |
      | predict_model.py | richiama il modello per fare la predizione sui nuovi dati estratti dal database |
    
    - **prediction**
    
      | File | Description |
      | --- | --- |
      | save_prediction.py | contiene il metodo per salvare la predizione in formato .json su Azure Storage |

## Istruzioni

1. Scaricare lo zip contenente la folder di progetto

2. Da _Visual Studio Code_ aprire la folder di progetto tramite:
   - **File**
     - **Open Folder...**

3. Aprire un nuovo terminale e creare un **Virtual Environment(venv)** eseguendo il comando:

   ```python
    virtualenv venv
   ```
  
   - In caso non sia installata **Virtualenv**, è possibile installarla tramite il comando:
  
     ```python
     pip install virtualenv
     ```
     e dopo creare il Virtual Environment:
     
     ```python
     virtualenv venv
     ```

4. Attivare il Virtual Environment

   ```python
   .\venv\Scripts\activate
   ```
   
   e eseguire l'installazione delle librerie necessarie per il funzionamento del progetto:
   
   ```python
     pip install -r "StreamlitCampus/requirements.txt"
   ```
   
5. Navigare alla folder _StreamlitCampus_ contenente il file **app.py**

   ```shell
   cd .\StreamlitCampus\
   ```
   e lanciare il comando per far partire l'applicazione di Streamlit
   
   ```python
   streamlit run app.py
   ```
