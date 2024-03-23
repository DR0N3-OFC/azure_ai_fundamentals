<h1 style="text-align: center;">Module 02 - Computer Vision Concepts 👀</h1>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">In the second module of the bootcamp, we were put on touch with the Computer Vision Azure services, which allows developers to add computer vision capabilities to their applications without requiring extensive machine learning expertise. It offers pre-trained models and APIs for tasks such as image analysis, object detection, image classification, and optical character recognition (OCR).</p>

<h2 style="padding-left: 15px; padding-right: 15px;">Creating a New Resource</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">On the <a href="https://portal.azure.com/?azure-portal=true#home">Azure Portal</a> click at <b>Create a resource</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/01.png" alt="Create a resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">After, in the <b>AI + Machine Learning</b> menu tab, select the <b>Azure AI Services</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/02.png" alt="Create a resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">You'll see the page below. Fill the spaces qith your information and choose the preferred configurations of name and region.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Click <b>Review + Create</b>.</p>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;"><i>* The Brazilian region has higher taxes.</i></p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/03.png" alt="Create a resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">After the conclusion, go to the <a href="https://portal.vision.cognitive.azure.com/">Azure Vision Studio</a> and <b>Sign in</b>.</p>

<h2 style="padding-left: 15px; padding-right: 15px;">Azure Vision Studio</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">For selecting an resource to work with, click at <b>View all resources</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/04.png" alt="Selecting a resource" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Select the desired resource and click <b>Select as default resource</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/05.png" alt="Selecting a resource" />

<h2 style="padding-left: 15px; padding-right: 15px;">Face Recognition</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Below on the <a href="https://portal.vision.cognitive.azure.com/">Vision Studio home page</a> select the <b>Face</b> menu and click in <b>Detect faces in an image</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/06.png" alt="Detecting faces in an image" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;"><b>Check the checkbox</b> highlighted on the image and <b>choose an file</b> by clicking or dragging and dropping on the highlighted area.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/07.png" alt="Detecting faces in an image" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">It automatically found my face at the image and highlited it.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/08.png" alt="Detecting faces in an image" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Clicking on the <b>JSON</b> tab, it shows the attributes (face landmarks, positions of the eyes, nose, etc.) gotten from the image after the face recognition.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/09.png" alt="Detecting faces in an image" />

<h2 style="padding-left: 15px; padding-right: 15px;">Character Recognition</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Again, in the <a href="https://portal.vision.cognitive.azure.com/">Vision Studio home page</a> select the <b>Optical character recognition</b> menu and click in <b>Extract text from images</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/10.png" alt="Detecting text in an image" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;"><b>Check the checkbox</b> highlighted on the image and <b>choose an file</b> by clicking or dragging and dropping on the highlighted area.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/11.png" alt="Detecting text in an image" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">It detected all information from the image and transcribed to an text document.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/12.png" alt="Detecting text in an image" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Clicking on the <b>JSON</b> tab, it shows the attributes (coordinates of every word in the image and the text associated to it) gotten from the image after the text recognition.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/13.png" alt="Detecting text in an image" />

<h2 style="padding-left: 15px; padding-right: 15px;">Image Analysis</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Once again, in the <a href="https://portal.vision.cognitive.azure.com/">Vision Studio home page</a> select the <b>Image analysis</b> menu and click in <b>Add captions to images</b>.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/14.png" alt="Adding captions to an image" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;"><b>Check the checkbox</b> highlighted on the image and <b>choose an file</b> by clicking or dragging and dropping on the highlighted area.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/15.png" alt="Adding captions to an image" />

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">It detected all information from the image and described what the model is seeing to text.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/16.png" alt="Adding captions to an image" />

```
> Cartoon of an egg with a yellow shirt and a gun
```

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Clicking on the <b>JSON</b> tab, it shows the results of the API request, as well as the confidence level of the result.</p>

<img style="margin-bottom: 10px; border-radius: 10px;" src="../images/Module 02 - Computer Vision Concepts/17.png" alt="Adding captions to an image" />