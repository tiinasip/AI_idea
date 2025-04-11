# What Comes Next - Checkout AI Fun
Final project for the Building AI course

## Summary
A camera is capturing a conveyor belt at a store's checkout in real-time. The viewer sees more information about the products and AI-prediction, what's coming next. The viewer sees from the screen statistics, how AI learns. At the same time, the store and different brands can promote their products and services.

## Background
Solution is for fun and marketing & promotion. Users are people who have been interested in other similar shows (Prisma checkout, Norwegian train routes, fireplace videos) and would like to either just watch the screen or participate. The Checkout AI Fun would give many lively conversation topics at the parties and other gatherings.

The idea combines slow TV and AI. It is oddly relaxing just to watch products moving on the belt, as described here [Livelähetys Prisman kassahihnalta nousi hitiksi](https://www.is.fi/viihde/art-2000005268226.html). On the other hand, AI is a hot topic, but not many understand how it works. This is an opportunity to bring it closer to mass audience and visualize, how the products we buy things from us.

As a marketing tool, it can provide information, show discount codes and suggest recipes. It makes the store's brand modern, playful and fun. If that is the objective of the marketing strategy, Checkout AI Fun is a good investment.

## How is it used?
Checkout AI Fun is abailable for user in internet and perhaps also in the store's app. There is a chat environment, where the viewers can participate. Statistics of made predictions roll on the screen and visualize, how successful AI has been. Based on experiences other live shows (Lintulautalive, Norppalive), many users start the live and have it on during the day on the screen even when they are working.

The creation of Checkout AI Fun needs funding. The best solution is to have a sponsor (perhaps the shop in question) in the beginning, and then later add costs for user in game purchases. 

Legal issues and especially GDPR is important aspect in the solution development. Shoppers' data cannot be used without their approval, so the cash station in question needs to have clear signs. Shoppers are not filmed, but it might possible recognize a person by combining the time, location and shopping cart content.

![Checkout](https://github.com/tiinasip/AI_idea/blob/main/ConveyerBelt.jpg)
text
<img src="https://github.com/tiinasip/AI_idea/blob/main/ConveyerBelt.jpg" width="200">

## Data sources and AI methods
### Description of the process
Stream live footage feeds frames to the AI model. The webcam is capturing products from above or the side. Then AI detects items and updates an item list. AI method to be used in detecting is pre-trained models (probably YOLO, but also Detectron2, or OpenAI’s CLIP combined with image recognition are possible). When a new item appears, the AI predicts what comes next. For the prediction a small neural net is used. All runs on a livestream (frontend display is Streamlit, Flask or OBS + Python backend).

### Selected techniques
YOLO (You Only Look Once) is a fast and accurate real-time object detection, and it is used for live streams or low-latency apps. Models are YOLOv5 and YOLOv8. I would use Ultralytics version to enable easier implentation.

The selected method for prediction is a small neural network. LSTM is a type of Recurrent Neural Network (RNN) designed to remember information over longer sequences and it solves the short memory problem of regular RNNs. In other words, it is predicting the next item depending on a sequence and learns from real data. However, it requires a lot of training data and more computational resources than easier models.

Another prediction model considered was a Markov chain, as it would be easy to implement and very lightweight. However, it looks only one step back and is not able to model long-term context (eg. butter -> ham -> cheese). 

## Code examples
### YOLO ultralytics
A simple code example for detecting objects in an image in Yolo ultralytics:
```
from ultralytics import YOLO

# Load a pretrained model
model = YOLO("yolov8n.pt")  # 'n' = nano, super fast

# Run detection on an image
results = model("checkout.jpg")

# Show results
results[0].show()
````
### LSTM
A simple code example of predefined item associations:
```
import random

next_items = {
    "coffee": ["milk", "sugar", "pastry"],
    "banana": ["yogurt", "cereal", "peanut butter"],
    "beer": ["chips", "sausages", "dip"],
    # etc...
}

def guess_next(previous_item):
    return random.choice(next_items.get(previous_item, ["a surprise!"]))
```



## Challenges
* GDPR and AI legislation need to be checked before implementation. Privacy may become an issue.
* Chat needs to be moderated and prevent insults etc. 
* Technically, the project is possible to implement.
* Financially, it requires an investor, preferably a store, which would use their marketing budget for this.
* Although one idea is to spread AI knowledge, most users would not really learn much from Checkout AI Fun. 

## What next?
It is easy to develope the idea furhter. Bonus features could be:
* Price estimation (“This belt looks like it’ll cost about €32.50”)
* Shopper profiling (“This looks like a cabin weekend stock-up”)
* Combinations ("Those items will end up to apple pie!")
* A commentator voice or chatbot (“Next up… yogurt? Suspense builds!”)
* More than prediction models competing against each other ("AI Alice is winning AI Joe today, and you viewers have lost to both of them!")
* Add self-checkout machines or other cashout conveyer belts and compare
* Viewers could make own suggestions for better forecast methods and also compete against AI with their own guesses.

Checkout viewer could become a community, as groceries and other everyday products are interesting and everyone has some emotions to them or brands. For instance
* "Who buys beer in the morning?"
* "You have money to buy a mango but then you buy the cheapest non-delphine friendly tuna!"
* "There is only meat products!"
* "There is only veggies, absolutely nothing to eat!"
* "Why do you buy 5 different sorts of cat food?"
* "Someone is going to bake, I guess it will be a chocolate cake!"

Items could be also something else than just groceries - maybe a big second-hand-store, a technical store, train traffic etc. Also Optional 3D/AR view	Unity + TensorFlow Lite. Scalability is very good.

If I start the project, I'd need technical and legal advice. There is a risk that no store would start to co-operate. If I had an agreement with the store, I am sure the funding can be found. 
My technical skills are not on the required level, but finding a technical partner is possible. I would need help for marketing as well. 

## Acknowledgments
* ChatGPT 
* [Livelähetys Prisman kassahihnalta nousi hitiksi](https://www.is.fi/viihde/art-2000005268226.html)
* My family - thanks for testing the idea with me

Inspiration came also from
* [Lintulautalive]([https://areena.yle.fi/1-73770995](https://yle.fi/a/74-20146706)
* [Norppalive](https://wwf.fi/luontolive/norppalive/)
* [Slow tv](https://en.wikipedia.org/wiki/Slow_television)
* [An Interpretive Study on the Public's Preference for the Fireplace Videos](https://www.researchgate.net/publication/371228429_An_Interpretive_Study_on_the_Public's_Preference_for_the_Fireplace_Videos)
