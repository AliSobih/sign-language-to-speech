
# Graduation Project
# Deaf and Normal Helper (Esm3ni)
Deaf people need us to hear and understand them. They feel that there is a gap between them and others because most people cannot understand sign language. They need to find something to make them communicate easier than sign language and to find something to help them to feel like there are no problems in their life. 
Most people have no desire or time to learn sign language because it is very difficult and differs from one language to another. The sign language in Arabic is different from the American sign language and the Indian sign language is different from both. No one can learn all of these different sign languages to communicate with different nationalities.

Millions of people across the world live with disabling hearing loss, 5 % of the population in the world suffers from hearing loss. In Egypt, 7 and a half million people are suffering from hearing loss.

Deaf suffer from some problems like
  1- Most people do not understand sign language.
  2- Deaf people cannot understand the normal ones.
  3- Deaf people suffer from a lot of problems in their educational life and      governmental entities
Because of all the previous points, we decided to make this project to help deaf people.
Therefore, we need to help them by making facilities to make communication as easy as we can. Usually, these facilities use English as the only language but as we know there is a high percentage of Egyptians who do not speak or read English, so we decided to make Arabic the main language in our project. We decided not to make only English because we want to help our society by improving the communication between all Egyptians.
Our project consists of two parts: one for deaf people and the other for normal ones.
First part (for the normal):
    This part is hardware consisting of A chip called raspberry pi. 
    Headphones. 
    Face shield.
    A very small camera settled on the face shield. 
      The camera captures the sign (static or dynamic) and then makes some         processing on it using deep learning to translate this sign as speech        (Arabic as the main language or English) then we can hear it on the          headphones. 
Second part (for the deaf):
  This part is a mobile application developed with flutter. It converts the    speech (Arabic or English) to text using then converts the text into sign    language and a video of the sign is displayed in the application. 
## System Requirements
  ### Functional Requirements:
  
  |REQ-1|Provides the feature of translating from Arabic and English languages to sign language and vice versa|
  |--------|---|
  |REQ-2 |Normal people will be able to understand the deaf by translating sign language to speech through a headset placed on a face shield|
  |REQ-3 |Deaf people will easily understand normal people by translating speech to text and then sign language through a mobile application|

  ### Non-functional requirements:
  |REQ-4|Performance: The system should provide the recognition of signs and their translation to speech and vice versa in an unnoticeable time for its users|
  |-----|---|
  |REQ-5|Accuracy: Signs should not be confused, and the system should recognize appropriate signs|
  |REQ-6|Environment: The system should provide real-time recognition with high accuracy in low light conditions as well|
  |REQ-7|Usability: The system should provide natural interaction to its users. The deaf person needs to worry about nothing else, just performing signs as it is extremely easy to use and operate|

## Our Work:
  ![image](https://github.com/AliSobih/sign-language-to-speech/assets/43109825/cbaf7b96-862b-4ddf-a181-14add48716c6)
  1. We used the MediaPipe library that uses machine learning to track the hands and detect 21 landmarks of a single hand from just a single frame, then draw these joints as      shown in Figure 12 Hand landmarks.
  2. Extract the coordinates(x,y,z) from these joints to calculate the distance between each finger with the landmark number[4, 8, 12, 16, 20] and the wrist that its              landmark is [0], the distance between each finger with the previous landmarks and the ear (the right hand from the right ear with landmark number[8] and the left hand        from the left ear with landmark number[7]) and the angles between each two neighbor fingers and the angle between the thumb and the pinky by drawing a straight line          from the finger to the wrist as shown in Figure 13.
  3. Create data by recording the landmark coordinates, distances, and angles for every 30 frames and loop it 30 times to make a one-sign language and save it as a NumPy          array. This operation takes at most 5 minutes to create the sign.
  4. Build a neural network deep learning model with one input layer, three hidden layers, and one output layer, then train the model after splitting the data into train and      test data, then split the train data into train and validation data.
  5. We have 5 models, a model for the Arabic alphabet with an accuracy of 98.30 of train data and 94.99 of test data, a model for Arabic words with an accuracy of 99.37 of       train data and 95.96 of test data, a model for Arabic numbers with accuracy 99.13 of train data and 93.75 of test data, a model for English alphabet with accuracy 99.82      of train data and 98.28 of test data, a model for English words with accuracy 98.30 of train data and 93.94 of test data
     ![image](https://github.com/AliSobih/sign-language-to-speech/assets/43109825/8a89f36e-9cf3-4048-b448-f6e56454f824)

## Accuracy Table
  |model |train accuracy | test accuracy |
  |------|------------|----------|
  |Arabic alphabet|98.30|94.99|
  |Arabic words|99.37|95.96|
  |Arabic numbers|99.13|93.75|
  |English alphabet|99.82|98.28|
  |English words|98.30|93.94|
## Used Libraries:
  - Open CV
  - Mediapipe
  - Tensorflow

# Team members
  1. Ali Fathy Abbas Mohamed (alifathyabbas@gmail.com)
  2. Esraa Abd-elhamed Abd-elbaky Mohamed
  3. Basma Tamer Omar Abd-elrahman
  4. Abeer Khaled Mohamed Hemdan
  5. Hady Mohamed Kamel Shams El-Din

