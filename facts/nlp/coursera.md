# [Natural Language Processing course resources](https://github.com/hse-aml/natural-language-processing/blob/master/README.md?plain=1)


Dieses Github enthält praktische Aufgaben für den Kurs Natural Language Processing der Higher School of Economics:
https://www.coursera.org/learn/language-processing.
In diesem Kurs werden Sie lernen, wie man gängige NLP-Probleme mit klassischen und Deep-Learning-Ansätzen löst.

Von praktischer Seite her erwarten wir, dass Sie mit Python vertraut sind, da wir es für alle Aufgaben im Kurs verwenden werden. Zwei der Aufgaben werden auch TensorFlow beinhalten. Sie werden mit vielen anderen Bibliotheken arbeiten, einschließlich NLTK, Scikit-learn und Gensim. Sie haben mehrere Optionen, wie Sie es einrichten können.

## 1. Ausführung auf Google Colab
Google hat seine eigene Jupyter-Variante namens Colab veröffentlicht, die über kostenlose GPUs verfügt!

Hier erfahren Sie, wie Sie es verwenden können:
1. Öffnen Sie https://colab.research.google.com, klicken Sie auf **Anmelden** in der oberen rechten Ecke und melden Sie sich mit Ihren Google-Anmeldedaten an.
2. Klicken Sie auf den Reiter **GITHUB**, fügen Sie https://github.com/hse-aml/natural-language-processing ein und drücken Sie die Eingabetaste.
3. Wählen Sie das Notebook aus, das Sie öffnen möchten, z. B. week1/week1-MultilabelClassification.ipynb
4. Klicken Sie auf **Datei -> Kopie in Drive speichern...**, um Ihren Fortschritt in Google Drive zu speichern.
5. Wenn Sie eine GPU benötigen, klicken Sie auf **Laufzeit -> Laufzeittyp ändern** und wählen Sie **GPU** im Feld Hardwarebeschleuniger
6. **Führen Sie** den folgenden Code in der ersten Zelle aus, die die Abhängigkeiten herunterlädt (ändern Sie ihn für Ihre Wochennummer):
```python
! wget https://raw.githubusercontent.com/hse-aml/natural-language-processing/master/setup_google_colab.py -O setup_google_colab.py
importiere setup_google_colab
# Bitte die Woche, an der Sie arbeiten, auskommentieren.
# setup_google_colab.setup_week1()  
# setup_google_colab.setup_week2()
# setup_google_colab.setup_week3()
# setup_google_colab.setup_week4()
# setup_google_colab.setup_project()
# setup_google_colab.setup_honor()
```
7. Wenn Sie viele Notebooks auf Colab laufen lassen, können diese weiterhin Speicher verbrauchen,
Sie können sie mit `! pkill -9 python3` beenden und mit `! nvidia-smi` überprüfen, ob der GPU-Speicher freigegeben wurde.

**Bekannte Probleme:**
* Keine Unterstützung für `ipywidgets`, daher können wir keine ausgefallenen `tqdm`-Fortschrittsbalken verwenden.
Für den Moment verwenden wir eine vereinfachte Version eines Fortschrittsbalkens, der für Colab geeignet ist.
* Blinkende Animation mit `IPython.display.clear_output()`.
Es ist brauchbar, aber wir suchen immer noch nach einem Workaround.
* Wenn Sie eine Fehlermeldung "No module named 'common'" sehen, stellen Sie sicher, dass Sie die zuweisungsspezifische Zeile in Schritt 6 auskommentiert haben, starten Sie Ihren Kernel neu und führen Sie alle Zellen erneut aus

## 2. Lokal ausführen

Hier gibt es zwei Möglichkeiten:

1. Verwenden Sie den Docker-Container aus unserem Kurs. Er enthält bereits alle Bibliotheken, die Sie benötigen. Die Einrichtung für Sie ist sehr einfach: Installieren Sie die Docker-Anwendung je nach Betriebssystem, laden Sie unser Container-Image herunter und führen Sie alles im Container aus. Bitte beachten Sie dieses [detaillierte Docker-Tutorial](Docker-tutorial.md).

2. Installieren Sie manuell alle Bibliotheken, die für Ihr Betriebssystem erforderlich sind (jede Aufgabe enthält ganz am Anfang eine Liste der benötigten Bibliotheken). Wenn Sie Windows/MacOS verwenden, finden Sie vielleicht die nützliche Anaconda-Distribution, mit der sich die meisten benötigten Bibliotheken leicht installieren lassen. Einige Tools, wie StarSpace für Woche 2, sind jedoch nicht mit Windows kompatibel, so dass Sie wahrscheinlich sowieso Docker verwenden müssen, wenn Sie sich für diese Aufgaben entscheiden.

Es könnte eine beträchtliche Menge an Zeit und Ressourcen benötigen, um den Code der Aufgaben auszuführen, aber wir gehen davon aus, dass ein durchschnittlicher Laptop ausreicht, um die Aufgaben zu bewältigen. Alle Aufgaben wurden in Docker auf einem Mac mit 8 GB RAM getestet. Wenn Sie Speicherfehler haben, könnte dies durch nicht getestete Konfigurationen oder ineffizienten Code verursacht werden. Erwägen Sie, diese Fälle zu melden oder Ihren Code doppelt zu überprüfen.

Wenn Sie den Code des Kurses auf einer AWS-Maschine ausführen möchten, haben wir das [AWS-Tutorial hier](AWS-tutorial.md) vorbereitet.
 
