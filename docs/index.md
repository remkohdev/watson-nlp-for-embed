# Embeddable AI

## Pre-requisites

* Open landing page [DSCE](https://dsce.ibm.com/),
* Open [https://github.com/IBM/dsce-sample-apps/tree/main/entity-extraction](https://github.com/IBM/dsce-sample-apps/tree/main/entity-extraction),
* Open [Watson NLP for Embed Script](remkohdev.github.io/watson-nlp-for-embed),
* Open [http://localhost:8050/](http://localhost:8050/) for local demo,
* Open DSCE site,
* Open `Contact Us` in DSCE,
* Open [IBM Watson Natural Language Processing Library for Embed Trial](https://www.ibm.com/account/reg/us-en/signup?formid=urx-51726),
* Open [Watson NLP Hands-on Tutorial](https://github.com/ibm-build-lab/Watson-NLP/blob/main/hands-on-lab/use-model/ML-TZ.md),
* Open TechZone asset [Watson NLP Library Hands-on Lab](https://techzone.ibm.com/collection/watson-nlp-library-hands-on-lab/journey-use-model),
* Create Watson Studio sandbox in TechZone,
* Open to edit Jupyter Notebook `Emotion Classification - Custom Model`,
* Open [MyIBM Dashboard](https://myibm.ibm.com/dashboard/),

## Introduction

### About Me

...

### Objective

In this demo, I will show how to include advanced AI functionality from IBM Watson in your own applications and use the Watson NLP library for Entities Extraction as an example.

In the example I use a pre-trained model but I will also show how to customize a model to increase accuracy for your specific domain using IBM Watson Studio and re-build a custom image of the Watson NLP.

I use an online wizard (DSCE) to guide anyone through the steps.

### Terms Used

Some terms used:

1. [DSCE](https://dsce.ibm.com/) is `IBM Digital Self-Serve Co-Create Experience (DSCE)`, an IBM wizard that makes it easy to try IBM products like IBM Watson libraries.

2. [IBM TechZone](techzone.ibm.com) makes free POC environments or sandboxes of IBM products available to IBM partners. To access TechZone your IBM Id must be registered in your PartnerPlus account. You must have an IBM PartnerPlus account.

3. `IBM Build Lab` is part of the IBM Ecosystem Engineering organization that helps IBM partners with embedding IBM products in their own product (as part of an ESA agreement) for free.

4. `Embedded AI` refers to the use of AI directly in your own products or IBM products so that you can run your AI applications anywhere, including disconnected on-prem environments, Azure, or AWS.

Other [IBM products use embedded AI](https://dsce.ibm.com/wizard/try?page=build-product):

* Instana,
* Turbonomic,
* Watson Assistant,
* Watson Discovery,
* Maximo,
* Maximo Visual Inspection (MVI),
* etc.

### Agenda

1. Start with DSCE wizard,
1. Demo: Use a Pre-Trained Model,
1. 

## Start with DSCE

1. Go to [https://dsce.ibm.com/](https://dsce.ibm.com/) to use the DSCE Wizard,
1. Click `Get Started`,

  ![DSCE - Get Started](images/dsce-01-getstarted.png)

1. Select "Find and try AI", click Start,

  ![DSCE - Get Started](images/dsce-02-find-and-try-ai.png)

1. Click `Build with AI libraries`,
1. Click `Build with Watson NLP`,
1. Click `Entities extraction`,
1. Click `Library and container`,

So now you are familiar with DSCE, let's look at using a pre-trained model in a demo.

## Demo: Use a Pre-Trained Model

In this section, I will continue in DSCE and run sample Python code embedding Watson NLP with the pre-trained model in a demo.

1. Click `Use a pre-trained model`,
1. Click Next,

  ![DSCE - Get Started](images/dsce-03-infuse-with-ai.png)

1. Review he `Try` steps:

  ![DSCE - Get Started](images/dsce-04-try.png)

1. In Step 1, you can review a few use cases: 
    1. entity extraction can be `Voice of the Customer`, a technique used to gather and analyze feedback from customers to improve products, services, and the customer experience. Or,
    1. extract Personal Identifiable Information (PII) for Compliance or Verification,
1. Skip the live demo application in Step 2, because I am running the demo from the application code sample in Step 3,
1. In step 3, get the code for the Entity Extraction demo app at [https://github.com/IBM/dsce-sample-apps/tree/main/entity-extraction](https://github.com/IBM/dsce-sample-apps/tree/main/entity-extraction),

  ![DSCE - Get Started](images/dsce-05-sample-amps-entities.png)

1. Run the code for the client demo following the instructions in the Github README,
1. Open the UI at [http://0.0.0.0:8050](http://0.0.0.0:8050),

  ![DSCE - Get Started](images/dsce-04-entities-demo.png)

The demo uses a client that accesses the Watson NLP Runtime, which is packaged as a container image hosted on the IBM Entitled Registry. You will need an entitlement key to access it. The demo uses the Watson NLP Runtime deployed on IBM Code Engine, see the client code:

```python
# pre-defined URL for backend
SERVER_URL = 'https://8f96122371.dsceapp.buildlab.cloud'
# API end-points used
REQ_URL = SERVER_URL+'/v1/watson.runtime.nlp.v1/NlpService/EntityMentionsPredict'
```

Now you have seen how you can deploy the Watson NLP Runtime and embed it in your client code. Next, let's look at the required steps to get started using embedded AI in your own solutions.

## Embed AI in your own Solution

In the next section, we will step through the steps to start using the `IBM Watson NLP Library for Embed` in your own solutions.

### Get Entitlement Key

To deploy your own instance of IBM Watson NLP Library for Embed, you first need an Entitlement Key or license.

1. Click the Deploy tab,

  ![DSCE - Deploy](images/dsce-07-deploy.png)

To deploy Watson NLP Embed AI libraries you need to have an IBM account and an entitlement key to use as a license,

1. If you don't have an IBM Cloud account, [Create an IBM Cloud account](https://cloud.ibm.com/registration?cm_sp=cpp_120k&target=%2Fpartner-center%2Fregistration%3FcppAttr%3DcHJvZ3JhbT1TVEFSVFVQX1dJVEhfSUJN),
1. To get your entitlement key, log into your [MyIBM Dashboard](https://myibm.ibm.com/dashboard/)
1. Click the `Get trial license and access container` button,
1. Signup or login using your IBM Id,
1. In the `Container Software & Entitlement Keys` tile, click `View Library`,
1. You can view existing or create new entitlement keys,

  ![My IBM Dashboard - Entitlement Keys](images/myibm-10-entitlement-key.png)

### Signup for Trial of Watson Studio

1. You need to sign up for the `IBM Watson Natural Language Processing Library for Embed` Trial

You can apply to qualify for $3000 credits on IBM Cloud. Go to [https://dsce.ibm.com/wizard/try/results/embed-nlp-entities-container-pt#deploy](https://dsce.ibm.com/wizard/try/results/embed-nlp-entities-container-pt#deploy).

1. In your [MyIBM Dashboard](https://myibm.ibm.com/dashboard/), you can see your Trials

  ![My IBM Dashboard - NLP Overview](images/myibm-09-dashboard.png)

1. In the `IBM Watson Natural Language Processing Library for Embed` tile, click Manage,
1. Go back to [MyIBM Dashboard](https://myibm.ibm.com/dashboard/) and scroll down to the `Cloud Paks & container software` section,


## Access TechZone

To customize a model you can use an instance of Watson Studio on TechZone. [IBM TechZone](techzone.ibm.com) makes free POC environments or sandboxes of IBM products available to IBM partners.

1. Go to [https://techzone.ibm.com/dashboard](https://techzone.ibm.com/dashboard),
1. To reserve a Watson Studio environment, follow the instructions in this [TechZone Tutorial](https://github.com/ibm-build-lab/Watson-NLP/blob/main/hands-on-lab/use-model/ML-TZ.md),

## Use a Custom Model

1. Check your [Reservations in TechZone](https://techzone.ibm.com/my/reservations), to make sure the Watson Studio sandbox is Ready,

  ![TechZone - Reservations](images/20-techzone-reservations.png)

1. If the Environment Status is Ready, continue,
1. Login to [https://dataplatform.cloud.ibm.com/home2?context=cpdaas](https://dataplatform.cloud.ibm.com/home2?context=cpdaas)

  ![TechZone - Reservations](images/21-ws-dashboard.png)

1. In the top right, you should see an active account `2577353 - tsglwatson`, if not, switch the active account,
1. In the Projects tile, you should notice a project named `emotion-classification-[hash]`,
1. Click the emotion classification project to open it,

  ![TechZone - Reservations](images/22-ws-project.png)

1. You should see 3 assets: `Emotion Classification - Custom Model`, `Emotion Classification - Pre-Trained Model`, and `emotion-tweets.csv`,
1. If you don't see all 3 assets, click the `View all` link in the assets tile or go to the Assets tab,

  ![TechZone - Reservations](images/23-ws-project-assets.png)

1. Next, create an asset token,
1. Click on the Manage tab.
1. Switch to the Access control menu item on the left, then select Access tokens,
1. If no token exists yet, click New access token,
1. Enter a Name for the access token, and select Editor in the Access role. Then, click Create.
1. Click on the Assets tab, and find the notebook Emotion Classification - Custom Models. Click the three dots on the right to open a drop-down menu, select Edit,
1. Once your notebook loads, in the top right of the horizontal tool bar, click the 3 dots dropdown, and select Insert project token,

  ![Watson Studio - Jupyter Notebook - Insert project token](images/25-ws-insert-token.png)

1. You are now ready to customize your model,

## Build Custom Model Image

Instead of using the pre-trained model, you can also use the customized model and build the custom model image for deployment. Follow the instructions below.

1. Go back to the Deploy tab at [https://dsce.ibm.com/wizard/try/results/embed-nlp-entities-container-pt#deploy](https://dsce.ibm.com/wizard/try/results/embed-nlp-entities-container-pt#deploy),
1. In Step 2, click Package and deploy your application,

  ![DSCE - Deploy](images/dsce-11-deploy.png)

1. In the Infuse your product with AI from IBM page, select Watson NLP,
1. Select Build a model image,

  ![DSCE - Deploy - Build a model image](images/dsce-12-build-a-model-image.png)

1. Select Custom model,
1. Click Next,

  ![DSCE - Deploy - Build a model image](images/dsce-13-custom-next.png)

1. Review the Try steps,

  ![DSCE - Deploy - Build a model image](images/dsce-14-try.png)

1. To build the custom model container, review the [tutorial](https://developer.ibm.com/tutorials/serve-custom-models-using-standalone-containers/),

## Work with IBM Build Lab

## Learn More

To learn more about embeddable AI using Watson NLP see the Assets for Watson NLP by Build Lab at [https://github.com/ibm-build-lab/Watson-NLP](https://github.com/ibm-build-lab/Watson-NLP).