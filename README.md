# 🧠 M2KR: Multimodal Retrieval with Wikipedia + FAISS

This project implements an end-to-end image retrieval pipeline using Wikipedia screenshots as queries and image scraping for passage/document indexing. It uses embeddings from ColQwen, FAISS for similarity search, and automated scraping from Wikipedia articles.

---

## 🚀 Features

- 🔍 Scrape images from Wikipedia articles based on query filenames
- 🖼️ Generate dense embeddings using a transformer-based vision model (`ColQwen2`)
- ⚡ Index passage images using FAISS (`IndexFlatL2`)
- 🎯 Retrieve top-k most relevant images per query
- 🧰 Modular code: easily extendable to other datasets or models

---

## 📁 Project Structure

```
m2kr/
├── src/
│   ├── model.py               # Embedding model using ColQwen2
│   ├── utils.py               # Image resizing, top-k utilities
│   ├── scrape.py              # Wikipedia image scraping logic
│   ├── main.py                # End-to-end pipeline: index + query
│   ├── config.py              # Config
├── data/
│   ├── passage_images/        # Indexed passage images
│   ├── query_images/          # Query images
│   ├── m2kr_data.parquet      # Query metadata
│   ├── faiss_index/           # Saved FAISS index
├── requirements.txt
├── run.sh                     # Shell script to run scrape + main
├── README.md
```

---


## 🔧 Usage

Run the entire pipeline:

```bash
python -m venv venv        
source venv/bin/activate    
bash run.sh
```


This will:
1. Install requirements
2. Scrape images from Wikipedia based on filenames in `data/passage_images/`
3. Build a FAISS index from those images
4. Embed and query the images from `data/query_images/`
5. Output the top-5 retrieved results per query to `data/final_results.csv`

---

## 📌 Requirements

- Python 3.10

---


## 📄 License

MIT License

---

## 🤝 Contributions

Pull requests are welcome. If you find a bug or want to improve something, feel free to open an issue or submit a PR.

---

## 👨‍💻 Author

**Bargav Jagatha**  
[github.com/bargav25](https://github.com/bargav25)


**Abhishek Varshney**  
[github.com/bargav25](https://github.com/avarshn)