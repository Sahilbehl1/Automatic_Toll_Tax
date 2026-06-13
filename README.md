# Automatic Toll Tax Deduction System

A computer vision based system that automates toll collection using real-time license plate detection, eliminating manual intervention at toll booths entirely.

## Overview
The system captures video at toll plazas, detects vehicles and extracts license plate text using YOLOv8 and EasyOCR, then automatically deducts the toll amount from the vehicle owner's Aadhar-linked bank account. No stopping, no manual payment required.

## How It Works
1. Camera records the toll lane in fixed intervals (10-15 seconds)
2. Each recording is processed frame by frame at 60fps using YOLOv8 to detect vehicles and license plates
3. EasyOCR extracts the license plate text, SORT algorithm tracks vehicles across frames to remove duplicates
4. Plate number is matched against vehicle RC records to fetch the linked Aadhar and bank account
5. Toll amount is deducted based on vehicle type (car, motorcycle, bus, truck etc.)

## Tech Stack
- YOLOv8 — vehicle and license plate detection
- EasyOCR — license plate text extraction
- SORT — multi-object tracking across video frames
- Python, Django — backend and API layer
- MySQL — vehicle records and transaction database
- Google Colab — model training

## Requirements
```
Python 3.12.2
MySQL 8.3.0
Django
easyocr, ultralytics, opencv-python
pandas, mysql.connector, filterpy, scikit-image, lap
pgadmin4, postman
```

## Setup
1. Clone the repository
```bash
git clone https://github.com/Sahilbehl1/Automatic_Toll_Tax
cd Automatic_Toll_Tax
```
2. Install dependencies
```bash
pip install -r requirements.txt
```
3. Configure MySQL credentials in `settings.py` and run migrations
```bash
python manage.py migrate
```
4. Start the server
```bash
python manage.py runserver
```

## Project Structure
```
├── Colab Files/                      # YOLOv8 model training notebooks
├── Django App/                       # Main backend application
├── Database Synthesis and Updates/   # DB schema and seed data
├── Output Files/                     # Sample detection outputs
└── Project Report.pdf                # Detailed project report
```

---

git add README.md
git commit -m "Update README with project details"
git push origin main