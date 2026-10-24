# Image-generation API runtime

Use Python 3.11 or newer. The pinned requirements replace the vulnerable historical TensorFlow, Flask and Gunicorn versions. Flask-CORS is declared because the entry point imports it; it uses the existing MIT-licensed Flask-CORS integration and adds no new service.

Install in a dedicated environment with `python -m pip install -r requirements.txt`. The direct Python entry point explicitly disables the interactive debugger. Use an appropriately configured application server for production rather than Flask's development server.

The endpoint requires a compatible `generator.h5` model in its working directory. That model is absent from this repository's API directory. A real image-generation smoke test and model-weight compatibility check are required before deploying the upgraded TensorFlow/Keras runtime. Dependency resolution and a startup test with stubbed ML imports do not establish model compatibility.
