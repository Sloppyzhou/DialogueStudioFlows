# Sentiment Analysis with Azure Text Analytics basic
### Anywhere365 Dialogue Studio
## Flow description
Using Azure Cognitive Services Text Analytics a basic flow. Good to test your Azure connectivity and secret. The two top nodes initialise flow level variables for your custom text to be analised and your Azure secret key. Below that are 4 different text analysis you can run on a custom text.
- language detection
- sentiment analysis
- key phrase extraction
- named entity recognition

Run each by manually pressing the button on left. See the result in debug area. For larger text copy the debug result to a JSON editer like VS Code. Or write to a file or database. Microsoft allows you to create local Docker container with Text Analytics so your custom texts do not have to travel to the cloud and can be analysed on premisses if you prefer. The analytics cost is the same. 

![transcript flow minimal](https://github.com/Anywhere365/DialogueStudioFlows/blob/master/SentimentAnalysisAzureBasic/resources/a365-ds-azure-sentiment-simple-screenshot.png)

Default custom text:
"In their latest publication, tech consultancy giant Gartner writes about the importance of optimizing Microsoft Teams with Cloud Contact Center Platforms. Even though Contact Center integration with Microsoft Teams is vital for almost any business, Teams lacks capabilities for key use cases. See Anywhere365 on https://anywhere365.io for a great solution!"

Sentiment Analysis exerpt
``` json
{
    "sentiment": "negative",
    "confidenceScores": {
        "positive": 0.0,
        "neutral": 0.03,
        "negative": 0.97
    },
    "offset": 155,
    "length": 137,
    "text": "Even though Contact Center integration with Microsoft Teams is vital for almost any business, Teams lacks capabilities for key use cases."
},
{
    "sentiment": "positive",
    "confidenceScores": {
        "positive": 0.99,
        "neutral": 0.01,
        "negative": 0.0
    },
    "offset": 293,
    "length": 63,
    "text": "See Anywhere365 on https://anywhere365.io for a great solution!"
}
```
Key Phrase extraction exerpt
``` json
{
    "id": "1",
    "keyPhrases": [
        "Microsoft Teams",
        "Contact Center integration",
        "Cloud Contact Center Platforms",
        "importance",
        "tech consultancy giant Gartner",
        "latest publication",
        "capabilities",
        "business",
        "key use cases",
        "Anywhere365",
        "great solution"
    ]
}
```


## How to download and import in Anywhere365 Dialogue Studio
- use green download [Code] button, top right from [repository home](https://github.com/Anywhere365/DialogueStudioFlows) or
- click on the .json file, click [raw] on top right, then ctl-A, ctl-C
- Goto hamburger menu, top right, in Dialogue Studio
- Choose Import, then ctl-V or select local file

## Requirements
- Microsoft Azure subscription
- Azure text analysis key and endpoints

## Todo after Import
- edit the custom text in the first change node on top
- edit the key in the second change node on top
- edit all 4 http request nodes, edit first part to your endpoint

## Notes
The UCC IVR call flow on top in this Dialogue Studio flow is just for generating the events. Edit to your needs. If you just want the standard Sharepoint based IVR flow you can change config.xml set identity is false for the nodered plugin. 

## Next steps
Happy with the result? Now create Transcript flow and use the text output for sentiment analysis. Change the debug node for a database write so you can see the result in PowerBI reports or Grafana realtime wallboard. To store all the JSON results and do trend reporting on sentiment or key phrases use free open source Elastic search and Kibana.