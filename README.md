# embedding-server

A wrapper for Hugging Face sentence transformer models with an OpenAI-compatible API.

This is a wrapper for Hugging Face sentence transformer models.
[FastAPI](https://fastapi.tiangolo.com/) is used to implement an HTTP API.
The API is compatible with the OpenAI API for text embeddings.
A Dockerfile is included to build an image based on [Uvicorn](https://www.uvicorn.org/) with the CPU-only version of [PyTorch](https://pytorch.org/).

## Usage

The models are loaded based on the given `MODELS` environment variable.
Multiple models can be given in a comma-separated string.

### Docker

The Dockerfile loads the models during build time.
No persistence is required.

To build the image run:

```bash
docker build -t embedding-server .
```

And to spin up a local instance on port 8080:

```bash
docker run -it --rm -p 8080:80 embedding-server
```

Open [http://localhost:8080/docs](http://localhost:8080/docs) in your browser to open the UI to browser the API.
