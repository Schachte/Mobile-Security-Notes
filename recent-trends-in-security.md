# Recent Trends in Mobile Security

<hr>

## Biometrics
    
    - Some forms of unchanging personal information
        . Fingerprints
        . Iris scan
        . Palm print
    - Pretty good form of security
    - Biometric sensors used for feature extraction to later identify

## Physiological Signals

    - Some forms of signals obtained from the human body in free living condition
    - How does it differ from biometrics?
        . No constant features
        . Highly random
        . No permanent feature
        . Time varying
    - Think about heart beat
    - To extract common similarity, you need to do signal processing

## Activity and Gestures

    - Depends on personal habits
    - Human computer interface 
    - Extremely random, same person could be doing the same thing in various ways
    - Need to do feature extraction and feed into machine learning system
    - Train the machine using a lot of past data and have the machine figure it out
    - Deep learning => You literally don't know shit about the data, it learns for you.

## Hacking Machine Learning Systems

    - Brute force feature engineering
        . Attacker randomly guesses data and gains yes answer (or no answer in his favor)
        . Attacker can learn the line, then input features to get a classification his/her favor
    - Poisoning Attack
        . Attacker doesn't have the training set, but the attacker can "influence" the machine by sending in some training data made by the hacker.
        . Think of dude jumping in front of uber car to fk up the learning process
        . You <b>CAN</b> see the training data
        . Think about SVM, you feed in enough data to shift the line of classification in order to rule in your favorable classification value
    - Evasion Attack
        . Monitoring heart + activity (validation)
        . Higher heart rate should imply higher activity levels
        . If you see a higher heart rate, but the person is sitting, then something sketchy is going on.
        . Do some verification to combat against false data injection
        . Doesn't change the entire machine like a poision. 
        . Can you GENERATE data that looks like data of a person, but isn't.

