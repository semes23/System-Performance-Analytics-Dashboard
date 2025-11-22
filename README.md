# Real-Time Computer Performance Dashboard

A comprehensive system performance monitoring solution that captures, stores, and visualizes real-time metrics through an integrated data pipeline. This project demonstrates end-to-end data engineering using Python, MySQL, SQL Server, and Power BI.

---

## Table of Contents

- [Overview](#overview)
- [Key Features](#key-features)
- [Technology Stack](#technology-stack)
- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [Running the Project](#running-the-project)
- [Architecture](#architecture)
- [Dashboard Preview](#dashboard-preview)
- [Credits](#credits)
- [Support](#support)

---

## Overview

Efficient system monitoring is essential for maintaining peak operational performance and identifying potential issues before they impact productivity. This project implements a data-driven approach to collect, process, and visualize real-time system performance metrics, enabling informed decision-making and proactive infrastructure management.

---

## Key Features

- **Real-Time Data Collection**: Captures live system performance metrics using Python's psutil library
- **Secure Data Storage**: Stores data reliably in MySQL database with automated backups
- **Data Pipeline**: Seamlessly transfers data from MySQL to SQL Server for enhanced processing
- **Interactive Dashboard**: Power BI integration provides dynamic visualizations and insights
- **Performance Tracking**: Monitors CPU usage, memory consumption, disk activity, and network traffic
- **Historical Analysis**: Maintains complete data history for trend analysis and performance comparison

---

## Technology Stack

- **Backend**: Python 3.x
- **Data Storage**: MySQL, SQL Server 2025 Express
- **Visualization**: Power BI Desktop
- **Libraries**: psutil, mysql-connector-python, pyodbc
- **Architecture**: ETL (Extract, Transform, Load) pipeline

---

## Getting Started

### Prerequisites

- Python 3.7 or higher
- MySQL Server 9.5+
- SQL Server 2025 Express
- Power BI Desktop
- Git

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/semes23/System-Performance-Analytics-Dashboard.git
   cd System-Performance-Analytics-Dashboard/Main
   ```

2. **Install Python dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up databases**:
   - Execute `database_Installation.sql` on your MySQL server
   - Execute `database_Installation.sql` on your SQL Server instance

---

## Configuration

### MySQL Configuration

Update your MySQL connection details in `main.py`:

```python
MYSQL_CONFIG = {
    'host': 'localhost',
    'user': 'root',
    'password': 'your_password',
    'database': 'system_Performance',
    'table_name': 'performance'
}
```

### SQL Server Configuration

Update your SQL Server connection details in `main.py`:

```python
SQL_SERVER_CONFIG = {
    'driver': '{SQL Server}',
    'server': 'localhost\\SQLEXPRESS',
    'database': 'System_Performance',
    'trusted_connection': 'yes'
}
```

### Power BI Setup

1. Open Power BI Desktop
2. Open the `system_performance.pbix` file
3. Update the data source connection to your SQL Server instance
4. Refresh the dashboard to load live data

---

## Running the Project

1. **Start the monitoring service**:
   ```bash
   python main.py
   ```

2. **View real-time data in MySQL**:
   ```sql
   SELECT * FROM system_Performance.performance ORDER BY time DESC LIMIT 10;
   ```

3. **Open Power BI dashboard**:
   - Launch Power BI Desktop
   - Open `system_performance.pbix`
   - The dashboard will automatically refresh with new data

The Python script runs continuously, collecting metrics every few seconds and pushing data through the pipeline.

---

## Architecture

The project follows a standard ETL pipeline:

```
System Metrics (CPU, Memory, Disk)
         ↓
    Python Script (Collection)
         ↓
    MySQL Database (Initial Storage)
         ↓
    Data Pipeline (ETL Process)
         ↓
    SQL Server Database (Processing)
         ↓
    Power BI Dashboard (Visualization)
```

---

## Dashboard Preview

The interactive Power BI dashboard displays:

- **CPU Usage**: Real-time processor utilization
- **Memory Metrics**: RAM consumption and availability
- **Disk Activity**: Storage usage and I/O performance
- **Network Metrics**: Data transmission rates
- **Historical Trends**: Performance patterns over time
- **System Interrupts**: CPU interrupt frequencies

![Real-time Performance Dashboard](/images/system_performance.png)

![Data Flow Architecture](/images/workFlow.png)

---

## Credits

This project leverages excellent open-source documentation and tools:

- **Python**: Official Python documentation and psutil library
- **MySQL**: Comprehensive MySQL documentation and best practices
- **SQL Server**: Microsoft SQL Server documentation and tutorials
- **Power BI**: Microsoft Power BI guides and visualization capabilities

---

## Support

For issues, questions, or suggestions:

1. Check the existing documentation in this repository
2. Review the setup instructions carefully
3. Ensure all prerequisites are installed correctly
4. Verify database connections are properly configured

---

## License

This project is open source and available for educational and professional use.

---

**Last Updated**: November 2025
**Version**: 1.0