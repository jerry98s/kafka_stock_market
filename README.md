## 📈 Kafka Stock Market Data Streamer

A real-time data streaming project simulating stock market data using Kafka and storing batched JSON records in Amazon S3. Built for practicing ingestion pipelines, message brokers, and data lake integration.

---

### 🚀 Tech Stack
- **Python**
- **Kafka** (`kafka-python`)
- **Pandas**
- **s3fs** (for S3 access)
- **AWS S3 / MinIO**

---

### 🧠 Project Overview

This project simulates a live stock market feed from a CSV file, streams each row as a Kafka message, and uses a Kafka consumer to batch and store data in an S3 bucket.

#### ✔️ Producer:
- Reads a local CSV (`indexProcessed.csv`)
- Converts each row to JSON and sends to Kafka topic `demo_test`

#### ✔️ Consumer:
- Listens to `demo_test`
- Buffers messages into batches (default: 10)
- Writes batched data to S3 in `.json` format

---

### 📁 Folder Structure

```
kafka_stock_market/
├── producer.py        # Kafka producer sending CSV rows
├── consumer.py        # Kafka consumer storing batched data to S3
├── data/
│   └── indexProcessed.csv  # Simulated stock market data
├── requirements.txt   # Python dependencies
└── README.md
```

---

### ⚙️ How to Run

1. **Start Kafka & Zookeeper locally or via Docker**

```bash
docker-compose up -d
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Run the Producer**
```bash
python producer.py
```

4. **Run the Consumer**
```bash
python consumer.py
```

---

### 🔪 Features to Extend
- Switch from JSON to Parquet using `pyarrow`
- Integrate with Spark Structured Streaming for large-scale ingestion
- Implement schema validation using `pydantic`
- Add email or Slack alerts for consumer errors

---

### 📚 Learning Outcomes

- Kafka Producer/Consumer design
- Data pipeline buffering strategy
- S3 write optimization
- Streaming data architecture concepts
