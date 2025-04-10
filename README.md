
# What Comes Next - Checkout AI Fun

Final project for the Building AI course

## Summary
A camera is capturing a conveyor belt at a store's checkout in real-time. The viewer sees more information about the products and also the AI's prediction, what's coming next. The viewer sees from the screen statistics how AI learns. 

The idea combines slow TV and AI. It is oddly relaxing just to watch products moving on the belt, as described here [Livelähetys Prisman kassahihnalta nousi hitiksi](https://www.is.fi/viihde/art-2000005268226.html). On the other hand, AI is a hot topic, but not many understand how it works. This is an opportunity to bring it closer to mass audience and visualize, how the products we buy reveal our attitudes and actions.


## Background
Solution is for fun. Users are people who have been interested in other similar shows (Prisma checkout, Norwegian train routes, fireplace videos) and would like to either just watch the screen or also play. The Checkout AI Fun would give many lively conversation topics at the parties and other gatherings.



This is how you make a list, if you need one:
* problem 1
* problem 2
* etc.


## How is it used?
Checkout AI Fun is abailable for user in internet. There is a chat environment, where the viewers can participate. Statistic roll on the screen and visualize, how successful AI has been. Based on experiences other live shows (Lintulautalive, Norppalive), many users start the live and have it on during the day on the screen even when they are working.

The creation of Checkout AI Fun needs funding. The best solution is to have a sponsor (perhaps the shop in question) in the beginning, and then later add costs for user in game purchases. 

Legal issues and especially GDPR is important aspect in the solution development. Shoppers' data cannot be used without their approval, so the cash station in question needs to have clear signs. Shoppers are not filmed, but it might possible recognize a person by combining the time, location and shopping cart content.


Describe the process of using the solution. In what kind situations is the solution needed (environment, time, etc.)? Who are the users, what kinds of needs should be taken into account?

Images will make your README look nice!
Once you upload an image to your repository, you can link link to it like this (replace the URL with file path, if you've uploaded an image to Github.)

![Checkout](https://github.com/tiinasip/AI_idea/blob/main/ConveyerBelt.jpg)
text
<img src="https://github.com/tiinasip/AI_idea/blob/main/ConveyerBelt.jpg" width="200">


![Cat](https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg)


## Code examples
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


## Data sources and AI methods

Stream live footage feeds frames to the AI model. The webcam is capturing products from above or the side. Then AI detects items and updates an item list. AI method to be used in detecting is pre-trained models (probably YOLO (You Only Look Once, but also Detectron2, or OpenAI’s CLIP combined with image recognition are possible). When a new item appears, the AI guesses what comes next. For prediction a statistical model (e.g. Markov chains) or a small neural net (if more data is available) is used. All runs on a livestream or recorded video (frontend dispaly is Streamlit, Flask or OBS + Python backend)

YOLO (You Only Look Once) is a fast and accurate real-time object detection, and it is used for live streams or low-latency apps. Models are YOLOv5, YOLOv8 and probably using Ultralytics version to be easier.

Prediction model Markov chain is easy to implement and very lightweight. However, it looks only one step back and is not able to model long-term context (eg. butter -> ham -> cheese). It works well, if the transitions are predictable.
LSTM is a type of Recurrent Neural Network (RNN) designed to remember information over longer sequences — it solves the “short memory” problem of regular RNNs.

Perfect when the prediction of the next item depends on a sequence, not just the last item.

"If there was yogurt, and earlier cereal, maybe banana is next."

LSTM can learn such patterns.

💡 How it works (super simplified)
Takes in a sequence of inputs (e.g., ["yogurt", "cereal", "coffee"])

Learns internal "memory" of what's important

Outputs a prediction of what’s next

✅ Pros
Understands deeper context and sequence trends

Learns from real data

Very flexible and powerful

❌ Cons
Requires training data (lots of carts!)

Heavier computationally than Markov

More complex to debug



Purpose	Tool/Framework
Video input	OpenCV / webcam / OBS
Object detection	YOLOv8 (Ultralytics)
Prediction model	Markov Chain or LSTM
Frontend display	Streamlit / Flask / OBS
Optional 3D/AR view	Unity + TensorFlow Lite

Where does your data come from? Do you collect it yourself or do you use data collected by someone else?
If you need to use links, here's an example:
[Twitter API](https://developer.twitter.com/en/docs)

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |



## Challenges

What does your project _not_ solve? Which limitations and ethical considerations should be taken into account when deploying a solution like this?

## What next?
Bonus features could be:
* Price estimation (“This belt looks like it’ll cost about €32.50”)
* Shopper profiling (“This looks like a cabin weekend stock-up”)
* A commentator voice or chatbot (“Next up… yogurt? Suspense builds!”)
* More than prediction models competing against each other ("Alice is winning Joe today!")
* Add self-checkout machines or other conveyer belts and compare
* Viewers could make own suggestions for better forecast methods and also compete against AI with their own guesses. 

Checkout viewer could become a community, as groceries and other everyday products are interesting and everyone has some emotions to them or brands. For instance
* "Who buys beer in the morning?"
* "You have money to buy a mango but then you buy the cheapest non-delphine friendly tuna!"
* "There is only meat products!"
* "There is only veggies, absolutely nothing to eat!"
* "Why do you buy 5 different sorts of cat food?"
* "Someone is going to bake!"

If I start the project, I'd need technical and legal advice. There is a risk that no store would start to co-operate. If I had an agreement with the store, I am sure the funding can be found. 
My technical skills are not on the required level, but finding a technical partner helps. I would need help for marketing as well.

How could your project grow and become something even more? What kind of skills, what kind of assistance would you  need to move on? 


## Acknowledgments

* ChatGPT - thanks for your help
* 
*
* list here the sources of inspiration 
* do not use code, images, data etc. from others without permission
* when you have permission to use other people's materials, always mention the original creator and the open source / Creative Commons licence they've used
  <br>For example: [Sleeping Cat on Her Back by Umberto Salvagnin](https://commons.wikimedia.org/wiki/File:Sleeping_cat_on_her_back.jpg#filelinks) / [CC BY 2.0](https://creativecommons.org/licenses/by/2.0)
* etc
