# SpeechToText

Watson Streaming Speech to Text Example
The following is an example of using Watson to real time transcribe from Speech to Text using the websockets streaming API.

Installation
This code is designed to run under python3 in a virtualenv. In order to get started you need to run the following:

virtualenv -p python3 .venv
source .venv/bin/activate
pip install -r requirements.txt
That will build you a clean environment and install the required pyaudio and websockets libraries for it's use.

Getting Started
This uses the pyaudio interface to abstract talking to audio interfaces. On the upside, this smooths over a lot of platform differences.

However, on Linux audio remains a "hard problem". The "default" audio device that is picked up by pyaudio by default is going to be what your sound mixer is set to. In Ubuntu, you will need to go to the Sound settings and set the input to what you want to record from there.

docs/images/input_audio.png

Credentials
You'll need to sign up for the Watson STT service. As of Sept 2018, IBM Cloud accounts get 100 minutes / month free.

In order to connect to the Watson streaming server you need an API Key, and to specify which region your speech to text service was provisioned in (there are different gateways per region). You can find these on your IBM Cloud console for the service you have added.

Copy speech.cfg.example to speech.cfg to ensure that's valid.

Expected Output
Once you run transcribe.py with a timeout value (-t) you'll get both incremental output as data comes back, as well as a final stitching of things together. The output will look something like this.

PS C:\xmamp\htdocs\html1> python transcrip.py -t 7 
* recording
hi 
hi 
hi how 
hi how are 
hi how are 
hi how are you 
hi how are you 
hi how are you 
hi how are you 
hi how are you 
hi how are you 
hi how are you 
* done recording
 hi how are you 
 ![Screenshot (41)](https://user-images.githubusercontent.com/85635520/127236770-5228839d-91fb-453e-ba71-7e37f707258f.png)

