# NER and NEL
This assignment was developed for the Data Semantics course in the Master Degree in Data Science.

The request for this assignment was to apply a spacy Named Entity Recognition pipeline on a text assigned individually. We were then asked to evaluate the found spans by comparing them with the "gold standard" spans, using different matching criterias. Similar metrics were also computed taking into account the correctness of the entity's recognized type (person, location, organization, date, ecc.). Lastly, a qualitative analysis of the errors made in recognising spans and types was written.
In the second part of the assignment we were asked to link the found entities to their Wikipedia page using various strategies (a naive approach, a bi-encoder BLINK instance and a complete BLINK instance). After computing metrics to evaluate the linking correctness, a qualitative analysis of the found links was written.
The result show a general superior quality of the linking found by the two more complex approaches compared with the naive one.

Some result were particularly interesting. Linking the words "Foreign Ministry", for example, highlights the three approaches' ability to understand the entity of a link based on its context:

1. The first naive method links this entity only to the page related to the "Ministry of foreign affairs" in general.</li>
2. The second method tries to understand the state of the Ministry, but fails. Probably because of its vicinity with the word "Taiwan", the method misclassify it as "Ministry of Foreign Affairs (Taiwan)".
3. The third approach is by far the best one, classifying the entity as "Ministry of Foreign Affairs of the People's Republic of China", which is the correct classification.

A very interesting thing also happens when the three approaches try to link "Tang Shubei". While both the BLINK approaches link him to "Tang Fei" (a writer) the first naive approach links him to the "Qiandao Lake incident". While it is still to be considered an error, as the approach linked a person to an event, inside the linked wikipedia page Tang Shubei is cited as the vice president of the ARATS, who stressed that China authorities would deal with the problems created by the Quindao Lake incident. Therefore, while the two BLINK approaches tried to link him with another persone, the naive method found the only wikipedia page in which this person was cited, and linked the entity to this page.<br>
