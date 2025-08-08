# 🧠 Face Detection & Recognition Application

An integrated Python project for real-time face detection and recognition using **Haar Cascade Classifier**, **LBPH Face Recognizer**, and services like **WhatsApp** and **Email alerts** for face intrusions.  

> Built with OpenCV, Python, Deep Learning concepts, and integrated system services.

---

## 📌 Features

-  **Face Detection** using Haar Cascade
-  **Face Recognition** using LBPH (Local Binary Patterns Histograms)
-  **Model Training with LBPH**
-  **Real-time Video Stream Processing**
-  **Text Overlays** using `cv2.putText()`
-  **Email Alert Service**
-  **File Handling** with `os` module
-  Highly tunable parameters (`scaleFactor`, `minNeighbors`) for best detection

---

## 🧰 Technologies Used

| Tech               | Description                            |
|--------------------|----------------------------------------|
| `Python 3.x`       | Main programming language               |
| `OpenCV`           | For image processing and face detection |
| `haarcascade`      | For face detection                     |
| `LBPH`             | For face recognition & model training  |
| `cv2.putText()`    | For placing text overlays on images    |
| `os` module        | File and path operations               |
| `smtplib`          | For sending email alerts               |
| `pywhatkit`        | For sending WhatsApp messages          |

---

## ⚙️ Working Explanation

### 🔍 Face Detection: `face_classifier.detectMultiScale(...)`

- Takes up to **6 arguments**, but mostly the following are essential:
  ```python
  faces = face_classifier.detectMultiScale(gray_frame, scaleFactor=1.4, minNeighbors=6)
  ```
- **`scaleFactor=1.4`** reduces face size by 40% to match trained image dimensions.
- **`minNeighbors=6`** ensures high precision — fewer false positives.
- A higher `minNeighbors` value increases accuracy but may miss true positives.

### 🧠 Face Recognition:
- Using **`cv2.face.LBPHFaceRecognizer_create()`** (from `opencv-contrib-python`)
- This recognizes the face from the trained model with high confidence.
- Training data is resized to a fixed size to standardize detection.

### 📝 Overlaying Text with `cv2.putText()`:
```python
cv2.putText(image, "Face Detected", (x, y), cv2.FONT_HERSHEY_SIMPLEX, 1, (255, 0, 0), 2)
```
- Customize **font**, **scale**, **color**, and **thickness**.

### 📩 Email and 📱 WhatsApp Alerts:
- If an unknown/intruder face is detected, alert messages are sent using:
  - **SMTP** for Email
  - **pywhatkit** for WhatsApp messaging

---

## 🗂️ Directory Structu```

---

## 🔧 Setup Instructions

1. **Clone the repo:**
   ```bash
   git clone https://github.com/yourusername/FaceDetectionApplication.git
   cd FaceDetectionApplication
   ```

2. **Install dependencies:**
   ```bash
   pip install opencv-contrib-python pywhatkit smtplib
   ```

3. **Run Face Detection:**
   ```bash
   python detect_face.py
   ```

4. **Train Model:**
   ```bash
   python train_model.py
   ```

---

## 🧪 Testing Parameters

| Parameter        | Value       | Description                                 |
|------------------|-------------|---------------------------------------------|
| `scaleFactor`    | `1.4`       | Reduces size of image for better matching   |
| `minNeighbors`   | `6`         | Higher value = fewer false positives        |

---

## 🛡️ Security Notes

- Ensure internet is available for sending WhatsApp and Email alerts.
- Do not expose API keys (if any) in public repositories.

---

## 🧠 Future Improvements

- Replace LBPH with **Deep Learning models** like FaceNet or VGGFace.
- Integrate **database logging** of intrusions.
- Add **GUI using Tkinter or PyQt** for user-friendly interface.
- Integrate **cloud-based alerting systems**.

---

## 🙋‍♂️ Author

**Shubham Ragade**  
Data Science | AI | Computer Vision  
📧 [Email Me](mailto:your.email@example.com)  
🔗 [LinkedIn](https://linkedin.com/in/shubhamragade2003) | [GitHub](https://github.com/yourusername)

---

## 🏁 License

This project is licensed under the MIT License.
