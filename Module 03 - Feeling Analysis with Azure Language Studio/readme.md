<h1 style="text-align: center;">Module 03 - Feeling Analysis with Azure Language Studio</h1>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">In the third module of the bootcamp, we learned about NLP models using NLP Azure Services and for what it can be used for. In this project we were introduced to the <a href="https://speech.microsoft.com/portal">Speech Studio</a> and the <a href="https://language.cognitive.azure.com/">Language Studio</a>, where there are a lot of Speech and Sentiment analysis model resources for a lot of use cases.</p>

<h2 style="padding-left: 15px; padding-right: 15px;">Speech Studio</h2>

<h3 style="padding-left: 15px; padding-right: 15px;">Creating a New Resource</h3>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Go to the <a href="https://speech.microsoft.com/portal">Speech Studio</a> and click at the <b>Settings button (Gear)</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/01.png" alt="Creating a new resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Click on <b>Create a new resource</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/02.png" alt="Creating a new resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Fill the spaces with your preferred information and click on <b>Create resource</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/03.png" alt="Creating a new resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Select the created source and click on <b>Use resource</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/04.png" alt="Creating a new resource" />

<h2 style="padding-left: 15px; padding-right: 15px;">Real-time Speech to Text</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <a href="https://speech.microsoft.com/portal">Speech Studio home page</a>, find the <b>Speech to text</b> section and click on the <b>Real-time speech to text</b> option.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/05.png" alt="Speech-to-text" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;"><b>Check the checkbox</b> highlighted on the image and <b>choose an audio file</b> to transcript by clicking or dragging and dropping on the highlighted area.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/06.png" alt="Speech-to-text" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">The audio was transcripted and the result is shown on the Text area. As it was a translated brazilian video, some words wasn't recognized by the model, but the overall performance was great.</p>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <b>JSON</b> tab we can see the response from the API. Informations like the response id, duration and the result text are contained on the response, as the duration of each word on the input audio.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/08.png" alt="Speech-to-text" />

<h2 style="padding-left: 15px; padding-right: 15px;">Language Studio</h2>

<h3 style="padding-left: 15px; padding-right: 15px;">Creating a New Resource</h3>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Go to the <a href="https://portal.azure.com/?azure-portal=true#home">Azure Portal</a> and click on <b>Create a resource</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/09.png" alt="Creating a Language Resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Go to the <b>AI + Machine Learning</b> category and select the <b>Language service</b> option.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/10.png" alt="Creating a Language Resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Click on the <b>Continue to create your resouce</b> button.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/11.png" alt="Creating a Language Resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Copy the following informations and click the <b>Review + create</b> button.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/12.png" alt="Creating a Language Resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Go to the <a href="https://language.cognitive.azure.com/">Language Studio</a>, <b>sign in</b> and the following screen will show up.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Fill the boxes with your information and click the <b>Done</b> button.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/13.png" alt="Language Studio" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Let's create a new project. On the <a href="https://language.cognitive.azure.com/">Language Studio home page</a> click on <b>Classify text</b> and select the <b>Analyze sentiment and mine opinions</b> option.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/14.png" alt="Creating project" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Choose the <b>desired language</b>, select the <b>created resource</b> and write or paste the input text on the <b>textbox</b>. You can also add and <b>text file</b> by dragging and dropping or clicking at the <b>highlighted area</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/15.png" alt="Creating project" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">The result will be shown on the <b>Result</b> area.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/16.png" alt="Creating project" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">In the <b>JSON</b> area we can see the response from the API, with informations like the sentiment rate of each sentence, confidence scores, etc.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 03 - Feeling Analysis with Azure Language Studio/17.png" alt="Creating project" />