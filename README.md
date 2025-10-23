#  Reconnaissance de Plaques d’Immatriculation avec ESP32-CAM, FastAPI, ReactJS, YOLOv5 & EasyOCR
Ce projet permet de capturer une image via une **ESP32-CAM**, de détecter automatiquement les plaques d’immatriculation 
avec **YOLOv5**,d’en extraire le texte avec **EasyOCR**, puis d’afficher les résultats dans une interface **ReactJS**.

##  Fonctionnalité principal
-  L'utilisateur clique sur un bouton "Prendre une photo" dans l'interface React.
-  React envoie une requête HTTP à l'API FastAPI.
-  FastAPI contacte l’ESP32-CAM pour déclencher la capture.
-  L’ESP32-CAM prend la photo et l’envoie à FastAPI.
-  FastAPI exécute une détection avec **YOLOv5** pour localiser les plaques.
-  Utilisation de **EasyOCR** pour extraire le texte des plaques détectées.
-  L’API retourne l’image + le texte extrait + la confiance.
- React affiche le tout dans l’interface.

##  Technologies utilisées
- **ESP32-CAM** (Arduino)
- **FastAPI** (Python 3.10+)
- **ReactJS** (Frontend)
- **YOLOv5** (détection d’objets)
- **EasyOCR** (reconnaissance de texte)
- **OpenCV** (traitement d’image)

## Configuration de l’environnement
### 1. Backend Python (FastAPI)
#### a. Créer un environnement virtuel
python -m venv venv.
source venv/bin/activate . // Linux/macOS
venv\Scripts\activate .    // Windows
Puis exécute le serveur :
uvicorn app:app --host 0.0.0.0 --port 8000 --reload

### 2.  Frontend ReactJS
npm start
L'application ReactJS sera accessible sur :
 http://localhost:3000

 ### 3. ESP32-CAM
Configure l’ESP32-CAM dans l’IDE Arduino :

Sélectionne la carte : AI Thinker ESP32-CAM

Configure les pins caméra 

Utilise les librairies esp_camera + WiFi.h + HTTPClient.h+ webserver.h
                
