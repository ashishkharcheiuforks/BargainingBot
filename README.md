# BargainingBot
A Bot that bargains for the price of drinks with customers.

The Bargaining Bot was my final year engineering project. The front end is an **Android App** and the back end consists of the Natural Language Processing (NLP) platform - **Dialogflow**, a machine learning **Tensorflow** model, and couple of **Cloud Functions**, along with some Google Cloud Platform (GCP) services to make all the different elements work together. Login and Database is handled by **Firebase**.

### What I learned : 
* **Android**: 
  * Developing a reactive android app with the **Model-View-ViewModel (MVVM)** architecture pattern.
  * Using dependency injection with [kodein](https://github.com/Kodein-Framework/Kodein-DI).
  * Using the observable patterns with [LiveData](https://developer.android.com/reference/android/arch/lifecycle/LiveData) and [ViewModel](https://developer.android.com/reference/android/arch/lifecycle/ViewModel).
  * Using Sq-lite local database with the [Room Persistence Library](https://developer.android.com/topic/libraries/architecture/room)
* **Tensorflow**:
  * Building a basic Linear Regression model.
  * Serving the model on GCP ML Engine.
* **Cloud Functions**:
  * Building a serverless single purpose function with TypeScript.
  * Working with JSON.
* **Firebase**:
  * Implementing Google and Facebook login in android with Firebase Authentication.
  * Using & modelling a No-SQL database with Cloud Firestore.
  
  

### Following are the links to repositories of different elements of the system:
* #### [Android App](https://github.com/shounakmulay/BargainingBotAndroidApp)
* #### [Cloud Function as the webhook for Dialogflow](https://github.com/shounakmulay/BargainingBotDialogflowWebhook)
* #### [Tensorflow Linear Regression model](https://github.com/shounakmulay/BargainingBotTensorflowModel)
* #### [Cloud Function triggered on a Pub/Sub topic](https://github.com/shounakmulay/BargainingBotDatabasePubSub)
* #### [Dialogflow](https://dialogflow.com/docs/getting-started)

#### [Link to the Published Paper about this project](http://www.iaeme.com/MasterAdmin/UploadFolder/IJCET_10_01_021/IJCET_10_01_021.pdf).


## 

![System Architecture](https://github.com/shounakmulay/BargainingBot/blob/master/System%20Architecture%20New.png)

##

### Try it for yourself:
   If you want to try it out you will need a Dialogflow account, a Google Cloud Platform (GCP) account, and a Firebase account.
 Firebase and Dialogflow both work on GCP itself so make sure Firebase, Dialogflow and GCP are all working on the same project.
 
 1. [Use this dialogflow template](https://github.com/shounakmulay/BargainingBot/blob/master/BargainingAgent.zip). It has all the necessary intents, actions and parameters setup. You can upload this zip to dialogflow and then customize it to your liking.
 
 2. Next setup the [webhook](https://github.com/shounakmulay/BargainingBotDialogflowWebhook) on Firebase Cloud Functions. Add the url of the function to the dialogflow webhook section. 
 
 3. Build your [Tensorflow Model](https://github.com/shounakmulay/BargainingBotTensorflowModel) and upload the exported file to Cloud ML Engine on GCP. You will need to link to this model in the weebhook.
 
 3. Create the Cloud Firestore database on Firebase and setup as shown in the images : [1](https://github.com/shounakmulay/BargainingBot/blob/master/1.jpg), [2](https://github.com/shounakmulay/BargainingBot/blob/master/2.jpg). The collections that are not explored in the images are blank collections for now that will be filled by the android app.
 
 5. Next create a [Cloud Pub/Sub](https://cloud.google.com/pubsub/docs/) topic on GCP. Add your topic name to the code in the next step.
 
 6. Create another cloud function in similar way to the previous one [from this repo](https://github.com/shounakmulay/BargainingBotDatabasePubSub).
 
 7. Clone the [Android App](https://github.com/shounakmulay/BargainingBotAndroidApp) and follow the mentioned steps to link it to the firebase project.
 
 ##
 
 ### Resources I used: 
  * [https://github.com/ResoCoder/forecast-mvvm-android-kotlin](https://github.com/ResoCoder/forecast-mvvm-android-kotlin)
  * [https://proandroiddev.com/mvvm-architecture-viewmodel-and-livedata-part-1-604f50cda1](https://proandroiddev.com/mvvm-architecture-viewmodel-and-livedata-part-1-604f50cda1)
  * [https://www.tensorflow.org/tutorials/keras/basic_regression](https://www.tensorflow.org/tutorials/keras/basic_regression)
