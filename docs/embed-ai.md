# Embeddable AI

## Pre-requisites

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

## Build to Win

In this demo, we use the Watson NLP library for Entities Extraction to show how easy it is to include advanced AI functionality from IBM Watson in your applications. In this example we use a pre-trained model but we will also show how easy it is to customize a model for greater accuracy in your domain with IBM Watson Studio and build the custom image for deployment.

Embedded AI Products:

* Instana,
* Turbonomic,
* Watson Virtual Assistance,
* Maximo Visual Inspection,

Before we begin:

1. [DSCE](https://dsce.ibm.com/) is `IBM Digital Self-Serve Co-Create Experience (DSCE)`, an IBM wizard that makes it easy to try IBM products like IBM Watson libraries.

2. [IBM TechZone](techzone.ibm.com) makes free POC environments or sandboxes of IBM products available to IBM partners. To access TechZone your IBM Id must be registered in your PartnerPlus account. You must have an IBM PartnerPlus account.

3. Build Lab is part of the IBM Ecosystem Engineering organization that helps IBM partners with embedding IBM products in their own product (as part of an ESA agreement) for free.

## Start with DSCE

1. Go to [https://dsce.ibm.com/](https://dsce.ibm.com/) to use the DSCE Wizard,
1. Click `Get Started`,

  ![DSCE - Get Started](../images/dsce-01-getstarted.png)

1. Select "Find and try AI", click Start,

  ![DSCE - Get Started](../images/dsce-02-find-and-try-ai.png)

1. Click `Build with AI libraries`,
1. Click `Build with Watson NLP`,
1. Click `Entities extraction`,
1. Click `Library and container`,

## Demo: Use a Pre-Trained Model

1. Click `Use a pre-trained model`,
1. Click Next,

  ![DSCE - Get Started](../images/dsce-03-infuse-with-ai.png)

1. Review he `Try` steps:

  ![DSCE - Get Started](../images/dsce-04-try.png)

1. Try steps:
    1. Step 1: Discover potential use cases; 
    1. Step 2: Try the interactive demo application; 
    1. Step 3: Get an application code sample; 
    1. Step 4: Start experimenting in our sandbox; and 
    1. Step 5: Learn more.

1. Some use cases under Step 1 for entity extraction can be `Voice of the Customer`, `Extract Personal Identifiable Information (PII) for Compliance or Verification`,
1. Let's run a demo by running the application code sample in Step 3,
1. Get the code for the Entity Extraction demo app at [https://github.com/IBM/dsce-sample-apps/tree/main/entity-extraction](https://github.com/IBM/dsce-sample-apps/tree/main/entity-extraction),

  ![DSCE - Get Started](../images/dsce-05-sample-amps-entities.png)

1. Run the code for the client demo following the instructions in the Github README,
1. Open the UI at [http://0.0.0.0:8050](http://0.0.0.0:8050),

  ![DSCE - Get Started](../images/dsce-04-entities-demo.png)

The demo uses a client that accesses the Watson NLP Runtime, which is packaged as a container image hosted on the IBM Entitled Registry. You will need an entitlement key to access it. The demo uses the Watson NLP Runtime deployed on IBM Code Engine, see the client code:

```python
# pre-defined URL for backend
SERVER_URL = 'https://8f96122371.dsceapp.buildlab.cloud'
# API end-points used
REQ_URL = SERVER_URL+'/v1/watson.runtime.nlp.v1/NlpService/EntityMentionsPredict'
```

## Deploy your own Solution

To deploy your own instance of IBM Watson Natural Language Processing Library for Embed, you need an Entitlement Key. You can use a free trial license for up to 180 days.

1. Click the Deploy tab,

  ![DSCE - Deploy](../images/dsce-07-deploy.png)

1. To get your entitlement key, click the `Get trial license and access container` button,
1. Signup or login using your IBM Id,
1. You need to sign up for the `IBM Watson Natural Language Processing Library for Embed` Trial

You can apply to qualify for $3000 credits on IBM Cloud. Go to [https://dsce.ibm.com/wizard/try/results/embed-nlp-entities-container-pt#deploy](https://dsce.ibm.com/wizard/try/results/embed-nlp-entities-container-pt#deploy).

1. In your [MyIBM Dashboard](https://myibm.ibm.com/dashboard/), you can see your Trials

  ![My IBM Dashboard - NLP Overview](../images/myibm-09-dashboard.png)

1. In the `IBM Watson Natural Language Processing Library for Embed` tile, click Manage,
1. Go back to [MyIBM Dashboard](https://myibm.ibm.com/dashboard/) and scroll down to the `Cloud Paks & container software` section,
1. In the `Container Software & Entitlement Keys` tile, click `View Library`,
1. You can view existing or create new entitlement keys,

  ![My IBM Dashboard - Entitlement Keys](../images/myibm-10-entitlement-key.png)

## Access TechZone

To customize a model you can use an instance of Watson Studio on TechZone. [IBM TechZone](techzone.ibm.com) makes free POC environments or sandboxes of IBM products available to IBM partners.

1. Go to [https://techzone.ibm.com/dashboard](https://techzone.ibm.com/dashboard),
1. To reserve a Watson Studio environment, follow the instructions in this [TechZone Tutorial](https://github.com/ibm-build-lab/Watson-NLP/blob/main/hands-on-lab/use-model/ML-TZ.md),

## Use a Custom Model

1. Check your [Reservations in TechZone](https://techzone.ibm.com/my/reservations), to make sure the Watson Studio sandbox is Ready,

  ![TechZone - Reservations](../images/20-techzone-reservations.png)

1. If the Environment Status is Ready, continue,
1. Login to [https://dataplatform.cloud.ibm.com/home2?context=cpdaas](https://dataplatform.cloud.ibm.com/home2?context=cpdaas)

  ![TechZone - Reservations](../images/21-ws-dashboard.png)

1. In the top right, you should see an active account `2577353 - tsglwatson`, if not, switch the active account,
1. In the Projects tile, you should notice a project named `emotion-classification-[hash]`,
1. Click the emotion classification project to open it,

  ![TechZone - Reservations](../images/22-ws-project.png)

1. You should see 3 assets: `Emotion Classification - Custom Model`, `Emotion Classification - Pre-Trained Model`, and `emotion-tweets.csv`,
1. If you don't see all 3 assets, click the `View all` link in the assets tile or go to the Assets tab,

  ![TechZone - Reservations](../images/23-ws-project-assets.png)

1. Next, create an asset token,
1. Click on the Manage tab.
1. Switch to the Access control menu item on the left, then select Access tokens,
1. If no token exists yet, click New access token,
1. Enter a Name for the access token, and select Editor in the Access role. Then, click Create.
1. Click on the Assets tab, and find the notebook Emotion Classification - Custom Models. Click the three dots on the right to open a drop-down menu, select Edit,
1. Once your notebook loads, in the top right of the horizontal tool bar, click the 3 dots dropdown, and select Insert project token,

  ![Watson Studio - Jupyter Notebook - Insert project token](../images/25-ws-insert-token.png)

1. You are now ready to customize your model,

## Build Custom Model Image

Instead of using the pre-trained model, you can also use the customized model and build the custom model image for deployment. Follow the instructions below.

1. Go back to the Deploy tab at [https://dsce.ibm.com/wizard/try/results/embed-nlp-entities-container-pt#deploy](https://dsce.ibm.com/wizard/try/results/embed-nlp-entities-container-pt#deploy),
1. In Step 2, click Package and deploy your application,

  ![DSCE - Deploy](../images/dsce-11-deploy.png)

1. In the Infuse your product with AI from IBM page, select Watson NLP,
1. Select Build a model image,

  ![DSCE - Deploy - Build a model image](../images/dsce-12-build-a-model-image.png)

1. Select Custom model,
1. Click Next,

  ![DSCE - Deploy - Build a model image](../images/dsce-13-custom-next.png)

1. Review the Try steps,

  ![DSCE - Deploy - Build a model image](../images/dsce-14-try.png)

1. To build the custom model container, review the [tutorial](https://developer.ibm.com/tutorials/serve-custom-models-using-standalone-containers/),

## Work with IBM Build Lab

## Learn More

To learn more about embeddable AI using Watson NLP see the Assets for Watson NLP by Build Lab at [https://github.com/ibm-build-lab/Watson-NLP](https://github.com/ibm-build-lab/Watson-NLP).