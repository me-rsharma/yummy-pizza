Alexa Skill 

Frontend + Backend

Frontend/ VUI - Voice User Inteface (Alexa Interaction Model)
Backend/ Programming Logic (Alexa Lambda Function)


What is Alexa Skill Set?
These are the capabilities that aer given by the user to Alexa to perform accordingly or perform some tasks

Alexa enabled device (VUI)  -------> Alexa Skill Kit

```
Alexa, open/play/tell/ask yummy pizza to order large(slot) cheese(slot) pizza
Wake +     Launch +       Invocation + Utterances (Can have slot)
```
On asking Alexa to launch specific invocation, it will be further requesting specific  INTENT based on request
Each INTENT can have multiple utterances and based on these utterances the Alexa gonna train the model and respond

```
                    -----------------------
                    |                     |
                    | give me fact        |       
                    |    a fact           |   UTTERANCES
                    |     tell me fact    |    
                    -----------------------
                        GetNewFactIntent
                        ---- INTENT ----
```

We as a developer mostly focus on INTENT and alexa based on intent gonna route the request

Launching a skill
```
                                                                                                                                                    -Slot-
    Alexa,     ask       space facts      for a fact about    Mars
-wake word-  -launch-  -invocation name-   ------ utterances -----
                {planet : 'Mars'}
                slotType: slotValue

                GetFactByPlanetIntent
                ------- INTENT -------
```

```
                                                               -Slot-
    Alexa,     ask       space facts      for a fact about    {planet}
                                                                Mars
                                                                Earth
                                                                Saturn
                                                                Pluto
 -wake word-  -launch-  -invocation name-   ------ utterances -----

```

 We can have multiple intents in one Alexa Skill
 There are 2 types - Custom & Alexa Builtin Intents

 Before starting creating Alexa Skill we have to focus on 2 major stuff
 
 VOICE INTERACTION NODEL    +     PROGRAMMING LOGIC
    Amazon developer             AWS Lambda/Cloudwatch
  (developer.amazon.com)           (AWS.amazon.com)


  STUCTURE OF ALEXA SKILL
  /models(Interaction model)
    /en-US.json
  /lambda/custom(Programming logic)
    /index.js
  skill.json

  TALKING TO ALEXA
```
    |-------- Audio---------------|
    |                             |
    |                             |
  User                      Speech Recognition
    |                        Machine Learning   -----Request--->   |     BACKEND
    |                              NLU          <----Response ---  |(PROGRAMMING LOGIC)
    |                          Text to Speech
    |                              |  AMAZON ALEXA
    |-------- Visual---------------|

```