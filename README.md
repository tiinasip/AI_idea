# Local government visible
Final project for the Building AI course

## Summary
Is the local school being shut? Where is a new housing development being zoned? Where will budget cuts hit? Which political party advocated for which policies in your neighborhood? Residents rarely have timely access to information about upcoming changes especially between elections. 

This application collects data from local government documents and generates summaries and predictions. An example of prediction: "The municipality is running a significant budget deficit. Most of its funds are allocated to education and early childhood services, and increasing class sizes has already been discussed. Raising class sizes now appears likely. Also the elementary school in Pikkupohja is probably going to be closed, as the number of pupils is already very low." 

## Background
Local government operations often remain hidden from public view, and residents typically only hear about them through occasional local media coverage. As a result, voters may not fully understand which responsibilities fall under municipal control and which do not.

The tool enables users to follow and better understand the workings of their municipal government. Users are able to gather the information and be able then question the local government and, on the other hand, local government learns to make decisions clearer when they know they will be closely followed.

The tool promotes local democracy and openness.

## How is it used?
The user visits a website and selects their municipality. Additional filters are available, such as environmental issues, financial situation, schools, daycare centers, and the compensation of elected officials. Upon requesting the current status, the user receives an overview of ongoing matters either related to their selected interests or a general municipal update. The user can ask AI to give analysis and predictions, and also ask it to compare the selected municipality to other relevant municipalities.

Anyone using public services is a potential user. 

The tool could also provide newsletter or enable setting alarm, if developed further.

## Data sources and AI methods
Local government documents are public and already available online (for instance [here](https://paatokset.hel.fi/fi/paattajat/kaupunginhallitus/asiakirjat)). The tool is trained to locate and retrieve these sources. It also gathers information on local political power structures and appointed officials (for instance [here](https://www.hel.fi/fi/paatoksenteko-ja-hallinto/kaupungin-organisaatio/kaupungin-organisaatiokaavio)).

The user interface has two parts: first, the user selects their municipality and areas of interest. Then, they can interact with the data through a chat interface powered by AI, similar to ChatGPT. 

AI techiniques used in the application:
* Natual Language Processing NLP 
* Named Entity Recognition (NER) for detecting people, organisation, locations - enable the sytem to recognize public officials, political parties, and local areas.
* Summarization: Automatically condenses lengthy government documents into clear, user-friendly summaries. Can use either abstractive (generative) or extractive (selection-based) summarization methods.
* Information retrieval (IR) finds relevant data from trusted sources (e.g., municipal meeting minutes and official bulletins).
* Dialogue Systems / Conversational AI enables ChatGPT-style interaction where users can ask follow-up questions or explore topics of interest. Includes intent recognition and natural language generation for responses.
* Fact-Checking & Source Attribution ensures responses are grounded in verifiable sources. Provides citations or links so users can check the original information themselves.
* Sentiment and Risk Analysis evaluates the tone and potential impact of decisions or topics. 

Frontend could be created with React. User interface could be created with Material UI. Data visualization is implemented with Recharts or Pltoly.js.

## Challenges
Government documents are complex and may be misinterpreted by both the AI and the user. The solution must provide clear source references so users can verify the information.

Additionally, the system may highlight individual officials. If this occurs in the context of misunderstood data, it could lead to inappropriate contacts and social media pressure.

Local media probably would not like the competitor, but this could also level up their articles from the current level.

## What next?
If I decide to start the project, I would need technical and legal advice. 

My technical skills are currently not at the required level, but finding a technical partner is feasible. I would also need assistance with promoting the idea and of course I need funding. 

## Acknowledgments
* ChatGPT
* [Kuntalaisten osallisuus](https://kansalaisyhteiskunta.fi/tietopankki/kuntalaisten-osallisuus-ja-kuuleminen-kunnan-paatoksenteossa/)
* [Kunnan verkkotiedottaminen](https://www.kuntaliitto.fi/yleiskirjeet/2017/kunnan-verkkotiedottaminen-seka-henkilotietojen-kasittely-ja-julkisuus-kuntalain)
