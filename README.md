<a href= "https://prototypefund.de/project/voice-ql-datentabellen-mit-gesprochener-sprache-barrierefrei-erkunden/"><img src="./resources/assets/voice-ql-ring.png" width="40%" height="40%" align="right"></a>

# Snips NLU Server for Voice QL

## Notice

This project is an adapted fork of the Repository https://github.com/jovotech/snips-nlu-server. Some minor changes have been made to make it fit to the [Voice QL](https://github.com/fboerncke/voice-ql) project.

## Why Snips instead of NLP.js?

This docker image allows you to run an open source [Snips NLU](https://github.com/snipsco/snips-nlu) server in your development environment. Snips comes with a number of advantages compared to NLP.js which is the default engine for Jovo.

This is why Voice-QL comes preconfigured to run with Snips instead of NLPjs.

Voice-QL will automatically push changes in the languagew model to snips. To make this work it is important to keep ports as configured in this setting or adjust setting in Voice-QL and this Docker installation in sync.

## Quick Setup

    $ git clone https://github.com/fboerncke/voice-ql-snips-nlu-server.git
    $ cd voice-ql-snips-nlu-server

Add the following line to Dockerfile to support 'de' models.

    RUN snips-nlu download de

Now build and run the service:

    $ sudo docker build -t snips-nlu-server .
    $ sudo docker run -p 5000:5000 snips-nlu-server

On the console you should then see something like this:

    ```
    * Serving Flask app '/app/server/__init__.py' (lazy loading)
    * Environment: development
    * Debug mode: on
    * Running on all addresses.
    WARNING: This is a development server. Do not use it in a production deployment.
    * Running on http://172.17.0.2:5001/ (Press CTRL+C to quit)
    * Restarting with stat
    * Debugger is active!
    * Debugger PIN: 207-980-342
    ```

Alive check:

    http://172.17.0.2:5001/
    http://172.17.0.2:5001/engine/parse

## Troubleshooting

If for some reason the setup does not work for you then you might want to follow the much more detailled instructions which can be found here:
https://github.com/jovotech/snips-nlu-server

## Acknowledgements

This project receives funding from the [German Federal Ministry of Education and Research](https://www.bmbf.de/) (FKZ 01IS22S30)

[![Logo Bundesministerium für Bildung und Forschung](./resources/assets/logo-bmbf.svg)](https://www.bmbf.de/)
&nbsp; &nbsp;
[![Logo Open Knowledge Foundation](./resources/assets/logo-okfn.svg)](https://okfn.de)
&nbsp; &nbsp;
[![Logo Prototype Fund](./resources/assets/PrototypeFund_Logo_smallest.svg)](https://prototypefund.de/)

The Prototype Fund is a project of the Open Knowledge Foundation Germany, funded by the German Federal Ministry of Education and Research (BMBF).
