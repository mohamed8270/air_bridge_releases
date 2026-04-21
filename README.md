# 📡 AirBridge - Seamless Windows-to-Windows File Sharing

**AirBridge** is a powerful and user-friendly desktop application built using Flutter that brings the magic of seamless file and data sharing—similar to Apple’s AirDrop—to Windows devices. Whether you're in an office, classroom, or just moving files between your own PCs, AirBridge eliminates the clutter of cables, USBs, or third-party cloud drives.

---

## 🚀 Features

- 🔄 **Instant File Transfer**: Effortlessly share files across nearby Windows machines over a local or remote network.
- 🔐 **Secure Sharing**: Each transfer is encrypted and authenticated—your files stay yours.
- ☁️ **Cloud Backup with AWS S3**: Optionally store files in the cloud for persistent access or backup.
- 📦 **Modern Tech Stack**: Flutter desktop frontend, blazing-fast Node.js backend, and reliable AWS deployment.
- 🧾 **Track & Manage Files**: See what you’ve sent and received—stored securely in MongoDB.

---

## 🛠 Tech Stack

| Layer            | Tech Used               |
|------------------|--------------------------|
| Frontend (UI)    | 🖥 Flutter (Desktop)     |
| Backend (API)    | ⚙️ Node.js + Express.js  |
| Database         | 📚 MongoDB               |
| Cloud Storage    | ☁️ AWS S3                |
| Deployment       | 🚀 AWS Elastic Beanstalk |
| Txt Summarization| 🗨️ Gemma 27B & GCP       |
| Containerization | 📦 Docker                |

---

## 📁 How It Works

1. **User selects files** from the AirBridge desktop UI.
2. Files are **transferred to nearby Windows devices** over the network.
3. Optionally, files are uploaded to **AWS S3** for storage.
4. All file metadata is **stored in MongoDB** for tracking and analytics.
5. The Node.js backend handles real-time sync and communication across clients.
6. **Gemma 27B parameter AI model has added** for advanced text summarization of files so that user don't need to worry about what consist in files.

---

## 🔧 Installation & Setup

Follow the steps below to get **AirBridge** up and running on your machine. This guide covers both desktop and web deployment, including Python scripts and GitHub Pages setup.

### 1. Clone the repository

First, clone the GitHub repository:

```bash
git clone git@github.com:mohamed8270/air_bridge.git
cd air_bridge
```

### 2. Install Flutter Dependencies

```bash
flutter --version
```

Then fetch all dependencies:

```bash
flutter pub get
```

### 3. Python Setup

The py folder contains scripts for:

- Generative model files (builder.py)
- Platform-specific icons (icon-builder.py)
- Splash screen builder (splash-builder.py)

Navigate to the py directory:

```bash
cd py
```

Run the scripts individually (optional, Makefile also runs them automatically):

```bash
python builder.py
python icon-builder.py
python splash-builder.py
```

⚠️ Ensure Python is installed and added to your system PATH.

### 4. Run the Flutter Desktop App

To run AirBridge on Windows:

```bash
flutter run -d windows
```

This will launch the desktop version of the app. For macOS or Linux, replace windows with macos or linux.

### 5. Build for Web

To build the web version of AirBridge:

```bash
flutter build web --base-href /air_bridge/ --release
```

This creates a production-ready web build inside build/web/.

### 6. Deploy Web Version Using Makefile

A Makefile is included to automate deployment:

```bash
make deploy-web
```

The Makefile does the following:

1. Cleans the Flutter project (flutter clean)
2. Runs Python scripts in the py folder
3. Builds the web app (flutter build web)
4. Pushes the build/web folder to GitHub

Important Notes:

- Install make: On Windows, use [Chocolatey](https://chocolatey.org/) or Git Bash.
- GitHub SSH keys must be set up for passwordless pushes:

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
ssh-add ~/.ssh/id_ed25519
ssh -T git@github.com
```

- Deployment can be done to a separate branch (e.g., gh-pages) or a /docs folder in main branch. Configure GitHub Pages to serve from the chosen location.
- The Makefile automatically uses BUILD_VERSION from pubspec.yaml for commit messages.

### 7. Access the Web App

Once deployed, the web version will be accessible at:

```bash
https://username.github.io/air_bridge/
```

### 8. Optional: Local Development Tips

- If you modify Python scripts in py, run them manually before building Flutter web.
- For debugging Flutter desktop apps, use:

```bash
flutter run -d windows --verbose
```

- To clean cached builds:

```bash
flutter clean
```

### Summary

- py/ → Python scripts for assets & splash screen generation
- flutter build web → Creates production-ready web version
- make deploy-web → Automates building & pushing to GitHub Pages
- Desktop apps → Run via flutter run -d windows
- Web apps → Served from build/web/ folder

This setup ensures both desktop and web builds are ready, and the deployment workflow is reproducible for future updates.

---

## 💡 Use Cases

- Office teams sharing documents without email or USB
- Students collaborating on projects
- Personal multi-device file syncing
- Developers transferring code or media quickly

---

## 📈 Project Status

- ✅ Project scaffolded and pushed to GitHub
- 🔄 Core feature development in progress
- 🚀 Beta version expected soon!

---

## 📬 Contributions & Feedback

We welcome your ideas, bug reports, and suggestions!  
Feel free to [open an issue](https://github.com/mohamed8270/azezun-server/issues) or submit a pull request.

---

## 📄 License

This project is licensed under the **MIT License** — feel free to use, modify, and distribute.
