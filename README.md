# 🎵 Aura Music Player
*A Hybrid Music Player using Python Flask & C Backend*

---

## 📌 Project Overview

Aura Music Player is a hybrid music player application that combines the efficiency of **C programming** with the flexibility of **Python Flask**.  
The C backend handles playlist management and playback logic, while Flask provides a web-based user interface and manages communication between the frontend and backend.

This project demonstrates inter-process communication, file handling, and dynamic memory management.

---

## 🛠️ Technologies Used

- **C Language** – Core backend logic
- **Python 3** – Middleware server
- **Flask** – Web framework
- **HTML, CSS, JavaScript** – Frontend
- **GCC Compiler** – C compilation

---

## 📁 Project Structure

- **app.py**  
  Main Flask application that manages routes, file uploads, and communication with the C backend.

- **music_player_backend.c**  
  C program implementing core music player features such as play, pause, next, previous, search, and delete.

- **music_player.exe / music_player**  
  Compiled C backend executable launched by Flask as a subprocess.

- **songs.txt**  
  Text-based database storing the list of uploaded songs.

- **static/**  
  Flask static directory.

  - **static/music/**  
    Stores uploaded music files.

- **templates/**  
  Contains frontend HTML templates.

  - **templates/index.html**  
    Main user interface of the music player.

- **README.md**  
  Project documentation.

---

## ⚙️ How the System Works

1. Flask application starts and launches the C backend as a subprocess.
2. User actions from the UI are sent to Flask.
3. Flask forwards commands to the C backend using stdin.
4. The C backend processes commands and sends output via stdout.
5. Flask reads output and updates the UI in real time.

---

## 🎮 Backend Command Mapping

| Command | Description |
|-------|------------|
| `1` | Play |
| `2` | Pause |
| `3` | Next Song |
| `4` | Previous Song |
| `5` | Shuffle ON/OFF |
| `6` | Repeat Mode |
| `8` | Reload Song Database |
| `10` | List Library |
| `11 <id>` | Play Song by ID |
| `12 <id>` | Delete Song by ID |
| `9` | Exit Backend |

---

## 🚀 Installation & Execution

### Step 1: Compile the C Backend

**Windows**
```bash
gcc music_player_backend.c -o music_player.exe


## Linux / macOS
gcc music_player_backend.c -o music_player
chmod +x music_player
