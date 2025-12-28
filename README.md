# Real-Time Text Analytics with Spark Streaming, Word Frequency and Co-occurrence Analysis

---

### Project Overview

This project implements real-time HDFS folder monitoring and text processing using Apache Spark Streaming with Scala, featuring a 3-second batch interval for immediate detection and ingestion of new files. It performs advanced word frequency analysis, applying character validation and filtering to ensure accurate tokenization and counting. Additionally, it incorporates stateful co-occurrence tracking by computing and continuously updating the frequencies of word bigrams, enabling insights into contextual relationships in the streaming text data.

---

## Access to Code 🔒

The source code for this project is **private** and available upon request.

If you're an **employer** or **recruiter** and would like to review the code, please **request access via email** at **ayanhashmi205@yahoo.com**.

---

## Installation 📦

#### Prerequisites
- Apache Spark 2.4+ with Streaming module
- Scala 2.12 or higher
- Hadoop HDFS cluster
- AWS EMR platform
- SBT (Scala Build Tool)

#### Clone this repo

```bash
git clone https://github.com/ayan9870/hdfs-monitoring-spark.git
cd hdfs-monitoring-spark
```

#### Setup Spark Environment
1. Install Apache Spark with Streaming support
2. Configure Hadoop HDFS cluster
3. Set up AWS EMR cluster with Spark and HDFS
4. Ensure proper HDFS permissions for input/output directories

#### Build JAR file

```bash
sbt clean compile package
```

#### Run on AWS EMR

```bash
spark-submit --class HDFSMonitoring hdfs-monitoring.jar <input_path> <output_path>
```

---

## Features 📋

### Core Functionality
* **Real-time HDFS Monitoring** - Continuous folder monitoring with 3-second batch intervals
* **Stream Processing** - Process new files automatically as they arrive
* **Word Frequency Analysis** - Count word occurrences with advanced filtering
* **Co-occurrence Calculation** - Analyze word relationships within text lines
* **Stateful Processing** - Maintain running totals across streaming batches
* **Sequential Output** - Organized output files with unique sequence numbering
* **Empty RDD Handling** - Skip processing when no data is available

### Text Processing Features
* **Character Filtering** - Retain only alphabetic characters in words
* **Length Validation** - Remove words shorter than 3 characters
* **Punctuation Removal** - Filter out numbers, punctuation, and special characters
* **Case Preservation** - Maintain original text casing
* **Line-based Processing** - Process each line independently for co-occurrence

### Advanced Stream Operations
* **updateStateByKey** - Continuous state management for cumulative results
* **Checkpoint Support** - Fault tolerance with automatic recovery
* **Parallel Module Execution** - Multiple processing Modules on same data stream
* **HDFS Integration** - Direct read/write operations with Hadoop filesystem

---

## Deployment Configuration 📤

### AWS EMR Setup
* **Cluster Configuration** - EMR cluster with Spark and HDFS enabled
* **JAR Deployment** - Upload compiled application to cluster
* **Path Configuration** - Input and output paths as command-line arguments
* **Resource Allocation** - Configure cluster resources for streaming workloads

### Command Line Execution
```bash
spark-submit \
  --class HDFSMonitoring \
  --master yarn \
  --deploy-mode client \
  hdfs-monitoring.jar \
  hdfs://input/folder \
  hdfs://output/folder
```

### Runtime Requirements
* **Input Path** - HDFS directory to monitor for new files
* **Output Path** - HDFS directory for storing processing results
* **Checkpoint Directory** - Current working directory for state management
* **Batch Interval** - Fixed 3-second processing intervals

---

## Author ✨

| <a href="https://github.com/ayan9870" target="_blank">**Muhammad Ayan Hashmi**</a> |
|:--:|
| ![Ayan Hashmi](https://github.com/ayan9870.png?size=100) |
| [`github.com/ayan9870`](https://github.com/ayan9870) |

---

## License
[![License](http://img.shields.io/:license-mit-blue.svg?style=flat-square)](http://badges.mit-license.org)

- **[MIT license](http://opensource.org/licenses/mit-license.php)**
