<!-- 
NavPath: Custom Speech Service
LinkLabel: Get Started
Url: Custom-Speech-Service/GetStarted
Weight: 95
-->

# Get Started with Custom Speech Service

Explore the main features of the Custom Speech Service and learn how to build, deploy and use acoustic and language models for your application needs.

## Table of Contents
* 	[Prerequisites](#Subscription)
* 	[Step 1: Create an acoustic model](#Create)
* 	[Step 2: Create a language Model](#Create2)
* 	[Step 3: Create a custom speech endpoint](#Create3)
* 	[Step 4: Using a custom speech endpoint](#Using)   

## <a name="Subscription">Subscription</a>  
#### 
In order to be able to upload data, to train a model or to do a deployment you need to link your Custom Speech Service activities to an Azure subscription. This can either be a free-tier or paid tier subsription. For further information please visit the pricing page.
To get a subscription id please go to your Azure portal and search for cognitive services and Custom Speech Service and follow the instructions there.

The subscrition key is required later in this process.
 
#### Subscribe to Custom Speech Service and get a subscription key 
There is a nice sample that we provide to get you going which you can fine [here](https://github.com/Microsoft/Cognitive-Custom-Speech-Service) 

Before playing with the above the example, you must subscribe to Custom Speech Service and get a subscription key, see [Subscriptions](https://www.microsoft.com/cognitive-services/en-us/sign-up). Both the primary and secondary key can be used in this tutorial. Make sure to follow best practices for keeping your API key secret and secure. 

#### Get the client library and example
You may download a client library and example via [SDK](https://www.microsoft.com/cognitive-services/en-us/SDK-Sample?api=bing%20speech&category=sdk). The downloaded zip file needs to be extracted to a folder of your choice, many users choose the Visual Studio 2015 folder.

## <a name="Create">Step 1: Creating a custom acoustic model</a>
To customize the acoustic model to a particular domain, a collection of speech data is required. This collection consists of a set of audio files of speech data, and a text file of transcriptions of each audio file. The audio data should be representative of the scenario in which you would like to use the recognizer

For example: 
If you would like to better recognize speech in a noisy factory environment, the audio files should consist of people speaking in a noisy factory. 
If you are interested in optimizing performance for a single speaker, e.g. you would like to transcribe all of FDR’s Fireside Chats, then the audio files should consist of many examples of that speaker only. 

## <a name="Create2">Step 2: Creating a custom language model</a>  
The procedure for creating a custom language model is similar to creating an acoustic model except there is no audio data, only text. The text should consist of many examples of queries or utterances you expect users to say or have logged users saying (or typing) in your application.

## <a name="Create3">Step 3: Creating a custom speech-to-text endpoint</a>
When you have created custom acoustic models and/or language models, they can be deployed in a custom speech-to-text endpoint. To create a new custom endpoint, click “Deployments” from the “CRIS” menu on the top of the page. This takes you to a table called “Deployments” of current custom endpoints. If you have not yet created any endpoints, the table will be empty. The current locale is reflected in the table title. If you would like to create a deployment for a different language, click on “Change Locale”. Additional information on supported languages can be found in the section on Changing Locale.

## <a name="Using">Step 4: Using a custom speech endpoint</a>
Requests can be sent to a CRIS speech-to-text endpoint in a very similar manner as the default Microsoft Cognitive Services speech endpoint. Note that these endpoints are functionally identical to the default endpoints of the Speech API. Thus, the same functionality available via the client library or REST API for the Speech API is also the available for your custom endpoint.

Please note that the endpoints created via CRIS can process different numbers of concurrent requests depending on the tier the subscription is associated to. If more recognitions than that are requested, they will return the error code 429 (Too many requests). For more information please visit the pricing information. In addition, there is a monthly quota of requests for the free tier. In cases you access your endpoint in the free tier above your monthly quota the service returns the error code 403 Forbidden.

Note: We are assuming that data is transmitted in real-time. If it is sent faster, we will consider the request as running until its audio duration in real-time has passed.

 * [Link back to Overview](Home.md)
 * [Link back to FAQ](FAQ.md)
 * [Link back to Glossary](Glossary.md)
