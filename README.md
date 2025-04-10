
# What Comes Next - Checkout AI Fun

Final project for the Building AI course

## Summary
A camera is capturing a conveyor belt at a store's checkout in real-time. The viewer sees more information about the products and also the AI's forecast, what's coming next. The viewer sees from the screen statistics how AI learns. 

The idea combines slow TV and AI. It is oddly relaxing just to watch products moving on the belt, as described here [Livelähetys Prisman kassahihnalta nousi hitiksi](https://www.is.fi/viihde/art-2000005268226.html). On the other hand, AI is a hot topic, but not many understand how it works. 

If developed further, viewers could make own suggestions for better forecast methods and also compete against AI with their own guesses. 

## Background



This is how you make a list, if you need one:
* problem 1
* problem 2
* etc.


## How is it used?

Solution is for fun. Users are people who have been interested in other similar shows (Prisma checkout, Norwegian train routes, fireplace videos) and would like to either just watch the screen or also play. The Checkout AI Fun would give many lively conversation topics at the parties and other gatherings.

The show needs funding. The best solution is to have a sponsor (perhaps the shop in question) in the beginning, and then later add costs for user in game purchases. 

Legal issues and especially GDPR is important aspect in game development. Shoppers' data cannot be used without their approval, so the cash station in question needs to have clear signs. Shoppers are not filmed, but it might possible recognize a person by combining the time, location and shopping cart content.


Describe the process of using the solution. In what kind situations is the solution needed (environment, time, etc.)? Who are the users, what kinds of needs should be taken into account?

Images will make your README look nice!
Once you upload an image to your repository, you can link link to it like this (replace the URL with file path, if you've uploaded an image to Github.)

![Checkout](https://github.com/tiinasip/AI_idea/blob/main/ConveyerBelt.jpg)
text
<img src="https://github.com/tiinasip/AI_idea/blob/main/ConveyerBelt.jpg" width="10">


![Cat](https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg)

If you need to resize images, you have to use an HTML tag, like this:
<img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg" width="300">

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

Stream live footage feeds frames to the AI model. The camera is capturing from above or the side. Then AI detects items and updates an item list. AI method is to use pre-trained models (probablyd YOLO (You Only Look Once, but also Detectron2, or OpenAI’s CLIP combined with image recognition are possible). When a new item appears, the AI guesses what comes next. For prediction a statistical model (e.g. Markov chains) or a small neural net (if more data is available).

* All runs on a livestream or recorded video (e.g. OBS + Python backend)

YOLO (You Only Look Once) is a fast and accurate real-time object detection, and it is used for live streams or low-latency apps. Models are YOLOv5, YOLOv8 and probably using Ultralytics version to be easier.


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

This could grow to a community, as groceries are interesting and everyone has some relation to them.

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
