# PlayerDetection - FootballAI

Dieses Repository enthält die finale Konfiguration zur Objekterkennung im Rahmen der Masterarbeit *FootballAI*. Ziel ist die robuste Detektion der Objektklassen `player`, `referee` und `ball` auf visuellem Videomaterial aus dem Amateurfußballbereich.

## 📦 Inhalt

- `config.yaml` – Trainingskonfiguration für YOLOv12s (Ultralytics)
- `dataset/` – Pfadstruktur und Annotationen im YOLO-Format
- `train.py` – Trainingsskript (Ultralytics-kompatibel)
- `inference.py` – Beispiel für Inferenz auf neuen Videos
- `README.md` – Diese Beschreibung

## 🧠 Modell

Das verwendete Modell basiert auf `YOLOv12s` und wurde mittels Transfer Learning auf einem eigens erstellten Drohnen-Datensatz trainiert. Als Basismodell diente ein auf dem COCO-Datensatz vortrainiertes YOLO-Modell.

## 📊 Trainingsdaten

- 922 Bilder aus Drohnenvideo (schräge Aufsicht, 10 m Höhe)
- 38 manuell annotierte Elfmeterszenen
- 754 Bilder aus Broadcast-Set von Skalski et al.

Annotationen im standardisierten YOLO-Format.

Roboflow-Link zum vollständigen Datensatz: [Datensatz anzeigen](https://universe.roboflow.com/footballai-xndiy/masterthesis_dataset)

