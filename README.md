# THA con terra: Wetterapp

Versuch das THA zu lösen.

## Stand
Die API von ArcGIS konnte ich einbinden und auch ein FeatureLayer 
mit angepasstem Renderer und visualVariables erzeugen.
Ein eigenes Widget zur Anzeige der Koordinaten habe ich nicht schreiben können.

## Verbesserungen
### Koordinaten Widget
Es scheiterte am Ende vor allem daran, dass ich nicht genug Verständnis vom
vue-Framework habe, um ein Widget darin zu erzeugen. Ich wollte dem Tutorial
[Show Latitude and Longitude in Widget](https://developers.arcgis.com/experience-builder/guide/get-map-coordinates/) folgen,
darin wird das Widget jedoch über React eingebunden, während mein Server setup ja auf vue setzt. Ich habe nicht geschafft,
das zu übertragen.

Eine Idee von mir war auch alternativ das [Popup Widget](https://developers.arcgis.com/javascript/latest/api-reference/esri-widgets-Popup.html)
zu nutzen und auf ein Click-event zu warten, um dann die Koordinaten auszulesen. Ich war jedoch nicht sicher,
ob ich ein Popup an einer beliebigen Kartenstelle öffnen könnte oder nur für Features im FeatureLayer.

Eines dieser Widgets würde dann das Locate-Widget ersetzen.

### esriConfig.apiKey
Ich hatte Probleme mir ein Konto zu erstellen, um ein Developer Credential zu erzeugen.
Es scheint nicht möglich mit dem freien online-Account, da ich mir dort keine Admin-Rolle
zuweisen konnte. Ich habe mich dann für einen Trial-Account registriert und konnte ein developer Credential erzeugen.

Hierbei blieb jedoch ein Problem, dass ich nicht herausfinden konnte, wie ich die Verfallsdauer für das
Token anpassen könnte. Es hat aktuell eine Verfallsdauer von 2h - was es fast unsinnig macht,
dieses Paket zu deployen, da das Token 'hart' im Code steht.

### Projektstruktur
Ich hätte die Startseite gerne schöner gestaltet.

Außderdem liegen aktuell die Scriptbefehle innerhalb der basic-map.html. Es wäre schöner diese
in eine eigene javascript-Datei auszulagern und in der html-Datei aufzurufen.