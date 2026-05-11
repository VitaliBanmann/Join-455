# 📋 Join - Kanban Board mit Drag & Drop

> Ein professionelles Kanban-Board zur Verwaltung von Projekten und Tasks. Features: Authentifizierung, Drag & Drop, Firebase Backend, Echtzeit-Collaboration.

## 🎯 Features

- ✅ **Kanban Board** - Visuelles Task-Management
- ✅ **Drag & Drop** - Intuitive Task-Bewegung
- ✅ **Benutzer-Authentifizierung** - Sichere Anmeldung
- ✅ **Firebase Backend** - Cloud-Speicher & Echtzeit
- ✅ **Team Collaboration** - Gemeinsame Projekte
- ✅ **Responsive Design** - Optimiert für Mobile/Desktop
- ✅ **Kategorisierung** - Tasks nach Status sortieren
- ✅ **Echtzeit-Updates** - Live-Sync zwischen Benutzern

## 🔧 Tech Stack

- **Frontend:** Vanilla JavaScript, HTML5, CSS3
- **Drag & Drop:** Native Drag & Drop API
- **Backend:** Firebase/Firestore
- **Authentifizierung:** Firebase Auth
- **Cloud Storage:** Firebase Cloud Storage
- **Echtzeit:** Firebase Realtime Listener

## 🚀 Installation & Setup

```bash
# 1. Repository clonen oder öffnen
cd Join-455

# 2. Lokalen Server starten
# Option A: Node.js
npx serve .

# Option B: Python 3
python -m http.server 8000

# Option C: PHP
php -S localhost:8000

# 3. Browser öffnen
# http://localhost:8000
```

## 🔐 Firebase Konfiguration

1. Firebase Projekt erstellen
2. Firestore Database aktivieren
3. Authentication aktivieren (Email/Password)
4. Config in `js/firebase-config.js` eintragen:

```javascript
const firebaseConfig = {
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_AUTH_DOMAIN",
  projectId: "YOUR_PROJECT_ID",
  storageBucket: "YOUR_STORAGE_BUCKET",
  messagingSenderId: "YOUR_MESSAGING_ID",
  appId: "YOUR_APP_ID"
};
```

## 📖 Verwendung

### 1. Registrierung
- Klick auf "Registrieren"
- Email und Passwort eingeben
- Account bestätigen

### 2. Login
- Mit Email & Passwort anmelden
- Zu Board weitergeleitet

### 3. Tasks Erstellen
- "Add Task" Button klicken
- Titel, Beschreibung, Priorität eingeben
- Task speichern

### 4. Tasks Verwalten
- **Verschieben:** Task mit Maus ziehen zwischen Spalten
- **Bearbeiten:** Task klicken zum Editieren
- **Löschen:** Delete Button in Task-Details
- **Zuweisen:** Aufgaben Team-Mitgliedern zuordnen

### 5. Spalten
- 🆕 **To Do** - Neue Tasks
- ⏳ **In Progress** - Aktiv bearbeitete Tasks
- ✅ **Done** - Abgeschlossene Tasks
- 🔄 **Feedback** - Zur Überprüfung

## 📁 Projektstruktur

```
Join-455/
├── index.html              # Haupt-HTML
├── login.html             # Login-Seite
├── signup.html            # Registrierungs-Seite
├── styles.css             # Globale Styles
├── js/
│   ├── script.js          # Hauptlogik
│   ├── firebase-config.js # Firebase Setup
│   ├── auth.js            # Authentifizierung
│   ├── board.js           # Board-Logik
│   ├── drag-drop.js       # Drag & Drop
│   └── utils.js           # Hilfsfunktionen
├── assets/
│   ├── images/           # Icons & Logos
│   ├── icons/            # UI-Icons
│   └── avatars/          # Benutzer-Avatare
└── README.md             # Diese Datei
```

## 🔨 Wichtige Befehle

```bash
# Server starten
npx serve .

# Firebase emulator (optional)
firebase emulators:start

# Build für Production
npm run build

# Tests (falls vorhanden)
npm test
```

## 🎮 Drag & Drop Implementierung

```javascript
// Task Drag starten
element.addEventListener('dragstart', (e) => {
  e.dataTransfer.effectAllowed = 'move';
  e.dataTransfer.setData('taskId', taskId);
});

// Drop-Zone aktivieren
element.addEventListener('dragover', (e) => {
  e.preventDefault();
  e.dataTransfer.dropEffect = 'move';
});

// Task ablegen
element.addEventListener('drop', (e) => {
  e.preventDefault();
  const taskId = e.dataTransfer.getData('taskId');
  moveTask(taskId, newColumn);
});
```

## 💾 Datenspeicherung (Firestore)

### Collection Structure
```
tasks/
├── taskId: {
│   title: "Task Titel",
│   description: "Beschreibung",
│   status: "in_progress",
│   priority: "high",
│   assignedTo: ["userId1", "userId2"],
│   createdAt: Timestamp,
│   dueDate: Date
│ }
└── ...

users/
├── userId: {
│   email: "user@example.com",
│   displayName: "John Doe",
│   profilePicture: URL,
│   tasks: [taskIds]
│ }
└── ...
```

## 🌐 Live Demo & Deployment

```bash
# Build für Firebase Hosting
npm run build

# Deploy
firebase deploy
```

## 🆘 Troubleshooting

### Firebase Connection fehlgeschlagen
- Firebase Config überprüfen
- Internet-Verbindung testen
- Browser Console auf Fehler checken

### Drag & Drop funktioniert nicht
- Browser-Kompatibilität überprüfen
- JavaScript in Browser aktiviert?
- Console.log für Debugging nutzen

### Tasks werden nicht gespeichert
- Firestore Rules überprüfen
- Authentifizierung aktiv?
- Netzwerk-Verbindung OK?

## 📞 Support

- Issues: [GitHub Issues](https://github.com/VitaliBanmann/Join-Projektmanagment/issues)
- Diskussionen: [GitHub Discussions](https://github.com/VitaliBanmann/Join-Projektmanagment/discussions)

---

_Ein professionelles Kanban-Board für agiles Projektmanagement._