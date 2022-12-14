# streamlit-health-insurance-predict

#Streamlit
#Flask
#RandomForest
#hyperopt
#docker

# 1. Description
Datasets: https://www.kaggle.com/datasets/mirichoi0218/insurance    

***Purpose***: Predict health insurance costs.  

Content:

**age**: age of primary beneficiary

**sex**: insurance contractor gender, female, male

**bmi**: Body mass index, providing an understanding of body, weights that are relatively high or low relative to height,
objective index of body weight (kg / m ^ 2) using the ratio of height to weight, ideally 18.5 to 24.9

**children**: Number of children covered by health insurance / Number of dependents

**smoker**: Smoking

**region**: the beneficiary's residential area in the US, northeast, southeast, southwest, northwest.

**charges**: Individual medical costs billed by health insurance


# 2. How to Run

To do this, follow the steps below by running the given commands within a Git bash (Windows), or terminal (Mac/Linux):

2.1. **Installation**

Clone the repo

```bash
git clone https://github.com/spacenew/streamlit-health-insurance-predict.git
```
cd into the project root folder

```bash
cd streamlit-health-insurance-predict
```
2.2. **Create virtual environment**

*via python*

Install pipenv:

```bash
pip install pipenv
```

Install the dependencies from Pipfile:

```bash
pipenv install
```

Activate virtual env:

```bash
pipenv shell
```

2.3. **Serving predictions using Flask and gunicorn**  

if you want to retrain the model and resave the model you can do it by running:

```bash
python ./packages/train.py
```
To deploy the Flask app locally. 

*Run it directly via python file*
```bash
python predict.py
```
OR

*Run gunicorn*

```bash
gunicorn --bind 0.0.0.0:9696 predict:app
```
Project should be running locally at http://localhost:9696

*Run the script to make test prediction*

```bash
python test.py
```

 2.4. **Build and run the Streamlit Application Locally**.

 ```bash
 streamlit run app.py
 ```

 If the web server was able to initialise successfully, the following message should be displayed within your bash/terminal session:

```
  You can now view your Streamlit app in your browser.

    Local URL: http://localhost:8501
  Network URL: http://192.168.0.71:8501
```
![alt text](https://github.com/spacenew/streamlit-health-insurance-predict/blob/main/images/app.jpg?raw=true)

# 3. Docker  

Build a Docker image:  

```bash
docker build -t insurance-predict .
```
Run docker image:

```bash
docker run -it --rm -p 8501:8501 insurance-predict
```



