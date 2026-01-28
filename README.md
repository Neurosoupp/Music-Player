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

### Step 2: Install Python Dependencies

Make sure **Python 3** is installed on your system.  
Install Flask using the following command:

```bash
pip install flask


### Step 3: Run the Application

Start the Flask application using the following command:

```bash
python app.py

### Step 4: Access the Application

Open any web browser and enter the following URL:

http://localhost:5000


The music player web interface will load, and you can start using the application.

### Step 5: Upload and Play Songs

- Upload audio files using the upload option in the web interface  
- Uploaded songs are stored in the `static/music/` folder  
- Song names are automatically saved in `songs.txt`  
- Use the player controls to play, pause, search, and delete songs

### Step 6: Stop the Application

- To stop the Flask server, press **Ctrl + C** in the terminal  
- This will automatically terminate the C backend process  
- Make sure all processes are closed before restarting the application

### Step 7: Troubleshooting & Notes

- Ensure the C backend is compiled **before** running `app.py`
- Keep `songs.txt` in the same directory as `app.py`
- Do not delete the `static/music/` folder
- If the backend does not start, recompile the C file and restart Flask
- Use unique song filenames to avoid duplication issues

### Step 8: Restarting the Application

- Stop the application using **Ctrl + C**
- Make sure no Flask or C backend process is running
- Re-run the application using:

```bash
python app.py


### Step 9: System Requirements

- Operating System: Windows / Linux / macOS  
- Python Version: Python 3.x  
- C Compiler: GCC  
- Web Browser: Chrome, Firefox, Edge (any modern browser)  
- Minimum RAM: 2 GB  
- Disk Space: At least 100 MB free space

