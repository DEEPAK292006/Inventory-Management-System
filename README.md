# Inventory-Management-System
Advanced Java Inventory Management System

A robust, multi-threaded command-line application designed for high-performance inventory tracking. This project demonstrates professional Java software engineering patterns, including concurrent data structures, scheduled background services, and automated data persistence.

🚀 Key Features

Thread-Safe Core: Utilizes ConcurrentHashMap and synchronized blocks to ensure data integrity in multi-threaded environments.

Automated Monitoring: A background ScheduledExecutorService audits stock levels every 15 seconds, alerting users to items below the threshold without interrupting the UI.

Intelligent Sorting: Implements both Comparable (natural SKU ordering) and custom Comparator strategies (Value, Price, Name).

Data Persistence: Automatic CSV serialization and a robust "Shutdown Hook" that ensures data is saved even during unexpected program termination.

Audit Trail: Every transaction is timestamped and recorded in a separate audit log for accountability.

Advanced Analytics: Uses a Min-Heap (PriorityQueue) to efficiently identify restocking priorities in $O(N \log K)$ time.

🛠️ Technical Stack

Language: Java 17+

Concurrency: java.util.concurrent (Executors, ConcurrentHashMap)

IO: java.io (BufferedReader, PrintWriter, File)

Collections: Stream API, TreeMap, LinkedList, PriorityQueue, ArrayDeque.

📋 System Requirements

Java Development Kit (JDK) 17 or higher.

Any terminal/command prompt.

🔧 Installation & Setup

Download/Clone: Ensure all .java files are in the same directory.

Compile the Project:

javac *.java


Run the Application:

java Main


(Optional) Pre-load Data: Place a file named inventory_db.csv in the root folder before starting to load existing data.

📂 Project Structure

Main.java: The interactive entry point and CLI controller.

InventoryManagementSystem.java: The core engine handling logic, threads, and I/O.

Product.java: The primary data model with thread-safe quantity management.

Transaction.java: Immutable records for the audit log.

InventoryUtils.java: Utility class for bulk calculations.

comparators/: Specialized logic for various sorting requirements.

DOCUMENTATION.md: Technical deep-dive and architectural diagrams.

⚠️ Important Notes

Concurrent Access: The background monitor prints to System.err. If it triggers while you are typing, simply finish your command.

Persistence: The file inventory_db.csv is updated automatically upon exit. Do not delete this file if you wish to retain your data between sessions.

Developed as a demonstration of Advanced Java Collections and Multithreading.
