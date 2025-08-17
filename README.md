# 🎮 WebAR Riddle Game (HIRO Marker) — Step-by-Step Guide

Welcome! This repo helps secondary-school students build and play a **WebAR riddle game** using **A‑Frame** and **AR.js** with the **HIRO** marker.

---

## ✅ What students will learn
- How WebAR works in the browser (no apps to install).
- Basics of A‑Frame entities (text, boxes, camera, marker).
- How to edit questions and logic in JavaScript.
- Publishing a web project with **GitHub Pages**.

---

## 🧰 You need
- A laptop or phone with a camera (Chrome, Edge, or Firefox).
- A GitHub account.
- The **HIRO marker** printed (see below).

---

## 1) Fork and open this project
1. Click **Fork** on your teacher’s repository, or download and upload these files into your own repo.
2. Make sure the project contains:
   - `index.html` (the game)
   - `marker/hiro-marker.png` (marker image – replace with the real HIRO marker)
   - `README.md` (this guide)

---

## 2) Turn on GitHub Pages (so it runs over HTTPS)
1. Go to **Settings → Pages** in your repo.
2. **Source**: choose `Deploy from a branch`.
3. **Branch**: select `main` (or `master`) and **/ (root)**.
4. Click **Save**.  
   After 1–2 minutes you’ll get a public URL like:  
   `https://<your-username>.github.io/<repo-name>/`

> WebAR needs HTTPS to use your camera. GitHub Pages gives you that for free.

---

## 3) Print the HIRO Marker
- Download the official HIRO marker (PDF/PNG) from AR.js / ARToolKit resources and print it **high‑contrast** on A4/Letter.  
- Or display it full screen on another device.
- Place it flat on a table with **good lighting** and no glare.

> The placeholder image in `marker/hiro-marker.png` should be replaced with the official marker. (Search for “AR.js HIRO marker”.)

---

## 4) Try it on your phone
1. Open your **GitHub Pages URL**.
2. Tap **Allow** when the browser asks for **camera** permission.
3. Point your camera at the **HIRO** marker.
4. Read the question and **tap a colored box** to answer.

---

## 5) Edit the riddles (JavaScript)
Open `index.html` and find the **riddles** array:
```js
const riddles = [
  { q: "What does CPU stand for?", a: ["Central Process Unit", "Central Processing Unit", "Computer Personal Unit"], c: 1 },
  // Add more here...
];
```
- `q` = question  
- `a` = 3 answer options (A, B, C)  
- `c` = index of the correct answer (0, 1, or 2)

👉 Tips:
- Keep answers short (1–3 words) for readability.
- Use **computing‑themed** questions to match your lesson.
- You can add more than 10; the code takes a random 10 each run.

---

## 6) Customize the scene (A‑Frame)
In the `<a-marker preset="hiro">` you can change:
```html
<a-entity id="question" position="0 1 0" text="value: ..."></a-entity>
<a-box id="optA" position="-1 0 0" width="1.4" height="0.45"></a-box>
```
- Move things using `position="x y z"` (try small changes: ±0.1).
- Change colors: `color="#4CAF50"`.
- Make items bigger: edit `width`, `height`, `depth`.

---

## 7) Classroom workflow (teacher-friendly)
- **Warm‑up (5 min):** What is AR? Show a quick demo with the HIRO marker.
- **Pair programming (15–20 min):** Students fork repo and get Pages URL.
- **Edit (15–25 min):** Each pair adds 5–10 computing riddles.
- **Playtest (10 min):** Groups swap markers/phones and test.
- **Reflect (5 min):** What UI change would improve the game?

**Differentiation ideas**
- Beginners: only change the questions.
- Intermediate: adjust colors/positions, add sounds.
- Advanced: add a per‑question timer or score streak bonus.

---

## 8) Common problems & quick fixes
- **Camera denied** → Reload page and allow camera permission.
- **Nothing shows** → Ensure GitHub Pages URL uses **https** and lighting is good.
- **Marker not tracking** → Print a clean marker, avoid glare, fill the camera view.
- **Upside down / off screen** → Tweak `position` and `width`/`height`.
- **Audio doesn’t play** → Some phones require a user tap before audio can play.

---

## 9) Optional extensions (nice challenges)
- **Start button + 3‑second countdown** before first question.
- **10‑second timer** per question; skip/penalty on timeout.
- **Question images**: add an `<a-image>` per riddle.
- **Multiple sets / random bank**: load from a separate `riddles.json` file.
- **End screen** with rating (“Novice”, “Pro”, “Guru”).

---

## 10) How the code works (short tour)
- **A‑Frame** draws 3D entities.
- **AR.js** detects the **HIRO** marker and attaches entities to it.
- JavaScript functions:
  - `load(i)`: shows the i‑th question and options.
  - `answer(idx)`: checks your click, updates score & feedback.
  - `next()`: moves to the next question or shows Game Over.

---

## 📄 License
This project is for classroom/educational use. You may remix it for your lessons.

Happy hacking and have fun building AR! 🎉
