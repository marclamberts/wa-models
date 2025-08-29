Expected Shot Danger: a hybrid shot model that co-exists with expected goals

It’s about two years since I first started writing about data away from player or team insight. I started with the Corner Delivery-model and two years later I have designed 20+ metrics, scores, indexes and models. They all took a variety of work, effort and hours - but in the end they all worked and took some time to develop. Some need time to brew and cook up, effectively shelving them for another time.

There is one model that has come off the shelve and has been put up there repeatedly in my brain. But I think, now is the time for me to properly launch into the world. Not only because I think it’s a decent model after time of deliberation and changes, but also because I truly believe in the process. The process is where we learn, it’s where our creativity comes to the surface and converts into meaningful data engineering.

The model I’m talking about is the expected shot danger model. 

Introduction
There are always two reasons for me to publish models. First of all and this is rather selfish, but I’m really proud of myself for finishing a long project. Due to my mental disorder, limitations are often put on what I can produce, but with football this seems to be different. And, the second one - perhaps more relevant for you that are reading this - is that I think this provides meaningful content for you to read and use the model in your own endeavours.  

It’s a question you might have and also one I wanted to answer for myself: why do we need this model when there already exists a quite comprehensive and complex model that values shots in expected goals?

Excellent question, I might add. Expected goals look at the quality of a chance and calculate a probability or likelihood that a certain shot will be converted into a goal. This is based on historical data. This is something I really like, but it feels very focused on goalscoring and probability of that happening. I want to measure threat and/or danger based on location and I found that expected goals came short in how I wanted to approach it.

Threat? Is there not another model that deal with threat or expected threat? Yes, there is. Karun Singh has developed the expected threat model (xT) a few years back and it has been instrumental in how we approach bin count values with progression towards goal. He can explain it much better than I can, so go read his full article here:

https://karun.in/blog/expected-threat.html

These are excellent models that will help going forward, but there are some fundamental element missing in combing threat with shots, so that’s why I decided to create my own model.


Aim
So why do I do this and what’s my aim? My aim is to create a shot-based value model that is a hybrid between expected goals and expected threat that seeks to measure outcome danger whilst including blocked shots.


The Expected Danger model is designed to overcome a key limitation of existing football analytics models. It combines the strengths of two popular metrics:

Expected Goals (xG): This model calculates the probability of a shot resulting in a goal based on factors like shot location, body part used, and play type. Its primary focus is on the final outcome: a goal. However, it assigns a value of zero to shots that are blocked, even if the shot was taken from a high-danger location.

Expected Threat (xT): This model measures the change in a team's probability of scoring when the ball moves from one location to another. It values passes and carries that move the ball into more dangerous areas, but it doesn't directly value the shot itself.


>>> import lumache
>>> lumache.get_random_ingredients()
['shells', 'gorgonzola', 'parsley']

