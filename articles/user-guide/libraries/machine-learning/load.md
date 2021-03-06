---
title: Klassische Daten werden geladen
description: Erfahren Sie, wie Sie ein eigenes Dataset laden, um ein Klassifizierungs Modell mit dem Microsoft Quantum Development Kit (QDK) zu trainieren.
author: geduardo
ms.author: v-edsanc
ms.date: 02/16/2020
ms.topic: conceptual
uid: microsoft.quantum.libraries.machine-learning.load
no-loc:
- Q#
- $$v
ms.openlocfilehash: 7ebfe085e50d4647fdb1027250cf3134f8d8f8c2
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856454"
---
# <a name="load-and-classify-your-own-datasets"></a>Laden und klassifizieren ihrer eigenen Datasets

In diesem kurzen Tutorial erfahren Sie, wie Sie Ihr eigenes Dataset laden, um ein Klassifizierungs Modell mit dem Quantum Development Kit (QDK) zu trainieren.

Wir empfehlen Ihnen dringend die Verwendung eines standardisierten Serialisierungsformats, wie z. b. [JSON-Dateien](https://en.wikipedia.org/wiki/JSON) , um Ihre Daten zu speichern.
Solche Formate bieten eine hohe Kompatibilität mit verschiedenen Frameworks wie Python und dem .NET-Ökosystem.
Insbesondere wird empfohlen, die Vorlage zum Laden der Daten zu verwenden, damit Sie den Code direkt aus den Beispielen kopieren können.

## <a name="template-for-loading-your-datasets"></a>Vorlage zum Laden von Datasets

Angenommen, wir haben ein Trainings Dataset $ (x, y) $ der Größe $N = $2, wobei jede Instanz $x _I $ von $x $ drei Features hat: $x _ {I1} $, $x _ {I2} $ und $x _ {I3} $.
Das Validierungs DataSet hat die gleiche Struktur.
Diese Datensätze können durch eine Datei dargestellt werden `data.json` , die der folgenden ähnelt:

```json
{
    "TrainingData": {
        "Features": [
            [
                x_11,
                x_12,
                x_13
            ],
            [
                x_21,
                x_22,
                x_23
            ]
        ],
        "Labels": [
            y_1,
            y_2
        ]
    },
    "ValidationData": {
        "Features": [
            [
                xv_11,
                xv_12,
                xv_13
            ],
            [
                xv_11,
                xv_12,
                xv_13
            ]
        ],
        "Labels": [
            yv_1,
            yv_2
        ]
    }
}
```

### <a name="example-using-the-template"></a>Beispiel für die Verwendung der Vorlage

Angenommen, wir verfügen über ein kleines DataSet mit den Höhen und Gewichtungen von unterschiedlichen Katzen und Hunden. Dieses DataSet ist sehr klein, um ein Modell zu trainieren, reicht aber aus, um den Prozess des Ladens eines Datasets anzuzeigen.

| Höhe (m) | Weight (kg) | Tier |
|-----------|------------|--------|
| 0,54      | 30         | Hund    |
| 0,30      | 8          | Katze    |
| 0,91      | 44         | Hund    |
| 0.86      | 31          | Hund    |
| 0,32      | 5         | Katze    |
| 0,25      | 4          | Katze    |

Der Prozess lautet wie folgt:

- Zuerst müssen wir das Dataset in Schulungen und Validierung aufteilen. In diesem Fall können wir einfach die ersten drei Beispiele für das Training und die restlichen Beispiele für die Überprüfung verwenden. Im Allgemeinen empfiehlt es sich, das Trainings-und Validierungs Dataset nach dem Zufallsprinzip zu testen, um unerwünschte Bias in den Trainingsdaten zu vermeiden.
- Zweitens muss jeder Klasse eine numerische Bezeichnung zugewiesen werden. Beachten Sie, dass die QML-Bibliothek momentan nur binäre Klassifizierungs Probleme zulässt. Daher weisen wir die Bezeichnung 0 der `Dog` -Klasse und die Zahl 1 der-Klasse zu `Cat` .
- Zum Schluss füllen wir die Vorlage mithilfe der Daten aus dem DataSet aus. Beachten Sie, dass Sie für große Datasets ein kleines Skript erstellen sollten, um die Vorlage automatisch aus dem jeweiligen Dataset zu generieren. Dieses Skript hängt vom ursprünglichen Format des Datasets ab.

Für unser DataSet `data.json` lautet die Datei:

```json
{
    "TrainingData": {
        "Features": [
            [
                0.54,
                30
            ],
            [
                0.30,
                8
            ],
            [
                0.91,
                44
            ]
        ],
        "Labels": [
            0,
            1,
            0
        ]
    },
    "ValidationData": {
        "Features": [
            [
                0.86,
                31
            ],
            [
                0.32,
                5
            ]
            [
                0.25,
                4
            ]
        ],
        "Labels": [
            0,
            1,
            1
        ]
    }
}

```

## <a name="loading-the-data"></a>Laden der Daten

Nachdem Sie Ihre Daten als JSON-Datei serialisiert haben, können Sie Sie in mithilfe von JSON-Bibliotheken laden, die mit Ihrer bevorzugten Host Sprache bereitgestellt werden.

### <a name="python"></a>[Python](#tab/tabid-python)

Python stellt das [integrierte `json` Paket](https://docs.python.org/3.7/library/json.html) zum Arbeiten mit JSON-serialisierten Daten bereit:

:::code language="python" source="~/quantum/samples/machine-learning/half-moons/host.py" range="4-5,20-22":::

### <a name="c"></a>[C#](#tab/tabid-csharp)

Die .net Core-Plattform stellt das [ `System.Text.Json` Paket](https://www.nuget.org/packages/System.Text.Json) zum Arbeiten mit JSON-serialisierten Daten bereit:

:::code language="csharp" source="~/quantum/samples/machine-learning/half-moons/Host.cs" range="10,64-82":::

***

## <a name="next-steps"></a>Nächste Schritte

Nun können Sie Ihre eigenen Experimente mit ihren eigenen Datasets ausführen. Probieren Sie verschiedene Klassifizierungen und Datasets aus, und tragen Sie zur Community bei, die ihre Ergebnisse gemeinsam nutzen!
