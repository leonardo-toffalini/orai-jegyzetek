### Scraping
Scrape the category `History` in Wikipedia, or something similar, for which Q&A is demonstrable

### Dataset
From the scraped data, create a syntethic Alpaca-style dataset by calling a stronger model API

### LoRA
Fine-tune a small model, like Llama 8B on the Alpaca dataset

### Quantization
Quantize the model to be able to call it from a laptop
Maybe it would be better to infer it on the a100 gpu

### WebUI
Create a simple webui for the model interface, could be from scratch