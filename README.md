# MedCab Datascience Web API

___

## Introduction

MedCab 2020 is a web app that provides an API hook for MedCab, a [Lambda School](https://lambdaschool.com/) cross-discipline build week project.  Medcab is only one piece of a larger puzzle, providing a recommended strain for paitent use based on user input ailments.  The purpose of Medcab is to assist patients who are looking for a more natural treatment options for chronic illnesses.  Users can register at *[Insert Web Address Here]* and select ailments they wish to seek treatment for.  PotBot 2020 will use Natural Language Processing to evaluate their listed ailments, and find the strain of medical marijauana best suited for patient relief.  

____

## Project Links:

### Heroku Web App Link:  https://potbot2020.herokuapp.com

- The Medcab Bot 2020 web app is built on FastAPI, and utlizies a helper page allowing users to test queries from the above link to get strain recommendations.

### Med Cab Project Website: *[Insert Link Here]*

- The project website provides a Front End user experience for logging in and getting recommended strains of medical marijuana based on different ailments that the user selects. 

___

## Medcab API Instructions:

### Installation: 

You can setup this API to run on your local machine by executing the following commands and instructions - 

1: Clone the git repo on your local machine:

```
git clone https://github.com/build-week-ft-med-cabinet-3/datascience.git
```

2: Configure and install the environment ([Pipenv](https://pipenv.pypa.io/en/latest/install/) is required):

```
pipenv install
```

- Note: This may take several minutes as pipenv will install all of the packages required to run the WebApp server.

3: Activate the virtual environment:

```
pipenv shell
```

4: Run the API server:

```
uvicorn app.main:app --reload
```

5: Open the web page:

- Open a browser and navigate to the server's localhost page.  Default: `127.0.0.1/8000` 

---

## Available Ailments

The following ailments are available for use with the API for suggesting strains of medical marijuana:

```
{'cramps',
 'depression',
 'eye pressure',
 'fatigue',
 'headache',
 'headaches',
 'inflammation',
 'insomnia',
 'lack of appetite',
 'muscle spasms',
 'nan',
 'nausea',
 'pain',
 'seizures',
 'spasticity',
 'stress'}
```



---

## Getting predictions locally

Navigating to the WebApp in your browser, rather locally or deployed, the user will be presented with the FastAPI test page, allowing the user to modify the input string and retreive strain recommendations.

### ![](/images/API_1.png)

1: Click on `Try it out` to enable the ability to edit the Request Body.

- Modify the `symptoms` key to contain ailment terms for the model to match to.

  - ```
    {
      "symptoms": "pain, depression, insomnia"
    }
    ```

2: After modifying the input string, click on the `Exectue` button to send the request to the API, and see the response come back in the interface:

### ![](/images/API_2.png)

---

## Getting results in your own web interface

Users can also integrate this api into their own web projects.  Follow the instructions below.

1: Construct your API call to send a POST request containing the following body, modifying the `symptoms` key to contain the appropriate ailment terms.

```
{
  "symptoms": "pain, depression, insomnia"
}
```

2: The Web App API will return a JSON dictionary object structured like below:

```
{
  "ID": 1307,
  "Name": "Tangelo Kush",
  "Rating": 2.73,
  "Type": "hybrid",
  "Ailments": "['depression', 'insomnia', 'pain']",
  "Positive_Effects": "Relaxed, Talkative, Uplifted, Sleepy, Giggly",
  "Negative_Effects": "Not Available",
  "Description": "A tangelo is a hybrid fruit that crosses the sweetness of a tangerine with the size and tartness of a pomelo (or grapefruit). So, it makes sense that Tangelo Kush, a tangy citrus hybrid, would be the cannabis equivalent. Chemdawg and Bermese Kush combine their unique and flavorful properties to turn Tangelo Kush into a delicious mixture of skunky, sour citrus zest that emphasizes flavor over potency. When ground into shake the diesel lemon musk is intensified and produces a smoke that is a sweet mix of sour and earthy notes when exhaled. The effects of Tangelo Kush go straight to your head and provide a relaxing solution to anxiety, depression, and can be a great way to stimulate your appetite.",
  "Effects": "Relaxed,Sleepy,Giggly,Talkative,Uplifted",
  "Flavors": "Lemon, Sweet, Citrus"
}
```









