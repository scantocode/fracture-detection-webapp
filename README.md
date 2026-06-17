# 🦴 Bone Fracture Detection System — Web App

A complete medical-AI web app: **log in → upload a DICOM or X-ray image → detect the fracture → download a professional PDF report.**

Built with the trained YOLO11 model from the **[Scan to Code](https://youtube.com/@scantocode)** series. Perfect as a portfolio piece or final-year project.

From medical scan to working AI code.

---

## ✨ Features

- 🔐 **Login page** (simple auth — swap for a real database in production)
- 📤 **Upload DICOM (.dcm) or JPG / PNG** — handles real medical scans and regular images
- 🎯 **One-click fracture detection** using a trained YOLO11 model
- 🖼️ **Input vs. AI detection** shown side by side, with the fracture boxed
- 📄 **Professional PDF report** — result, confidence, both images, branded template
- ⚠️ Clear "educational demo, not a medical device" disclaimer

---

## 🚀 Run it locally

```bash
git clone https://github.com/scantocode/fracture-detection-webapp
cd fracture-detection-webapp
pip install -r requirements.txt
```

**Get the model:** download `best.pt` from the
[**Releases page**](https://github.com/scantocode/fracture-detection-webapp/releases/tag/v1.0)
and place it in the project root, next to `app.py`.

> 💡 Want to train your own from scratch? Follow the free
> **[Episode 4 training tutorial](https://youtube.com/@scantocode)** — it walks you
> through the whole process step by step.

Then run:

```bash
streamlit run app.py
```

Then open **http://localhost:8501** in your browser.

**Demo login:**
| Username | Password |
|----------|----------|
| `admin`  | `scan2code` |
| `doctor` | `fracture123` |

---

## 📁 Files

| File | Description |
|------|-------------|
| `app.py` | The full Streamlit web app |
| `best.pt` | Trained YOLO11 model — [download from Releases](https://github.com/scantocode/fracture-detection-webapp/releases/tag/v1.0) (or train your own in [Episode 4](https://youtube.com/@scantocode)) |
| `requirements.txt` | Python dependencies |
| `.streamlit/config.toml` | Light-theme UI config |

---

## 🧠 How it works

1. **Login** gate (`st.session_state`)
2. **Upload** → DICOM is read with `pydicom` and normalized to an 8-bit image; JPG/PNG read with `Pillow`
3. **Predict** → the YOLO11 model (`best.pt`) draws bounding boxes on detected fractures
4. **Report** → `reportlab` builds a branded PDF with the result, confidence, and both images

Want to see it built step by step? Watch the tutorial on **[Scan to Code](https://youtube.com/@scantocode)**.

---

## ⚠️ Disclaimer

This is an **educational demonstration** trained on a public dataset. It is **NOT a medical device** and must not be used for clinical diagnosis. Always consult a qualified radiologist.

---

## 🔗 Links

- 📺 YouTube: [@scantocode](https://youtube.com/@scantocode)
- 📸 Instagram: [@scantocode](https://instagram.com/scantocode)
- 💼 LinkedIn: [Faiyyaz](https://linkedin.com/in/faiyyaz-hangad)

⭐ Star the repo and subscribe if this helped you build yours!
