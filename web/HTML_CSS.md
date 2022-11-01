# HTML und CSS

[TOC]

Table of Contents
=================

* [Table of Contents](#table-of-contents)
  * [HTML](#html)
    * [Struktur](#struktur)
    * [Syntax](#syntax)
    * [Elemente](#elemente)
  * [CSS](#css)
    * [Darstellung](#darstellung)
  * [XML](#xml)
  * [Literatur](#literatur)


## HTML - Hypertext Markup Language

HTML beschreibt die Struktur eines HTML-Dokuments (z.B. Kapitel, Absatz, Überschrift, ...).

### Struktur

Grundgerüst eines HTML-Dokuments

```html
<!DOCTYPE html>
<html>
    <head>
        <title>Martin Stephan</title>
    <body>
        <h1>HTML</h1>
        <p>HTML beschreibt die Struktur eines HTML-Dokuments und 
           so weiter und so fort...</p>
    </body>
    </head>
</html>
```

HTML-Dokument beginnt immer mit der Angabe der verwendeten HTML-Version.

```html
<!DOCTYPE html> 
```

... für HTML5-Dokumente. 

Der **Header** enthält Informationen über das Dokument, die nicht zum eigentlichen Inhalt gehören.

Der **Body** enthält den eigentlichen Inhalt des Dokuments. 

Strukturelle Elemente des HTML-Dokuments werden jeweils von einem **Start-Tag** und einem **End-Tag** eingefasst.

Tags können in Form von **Attributen** zusätzliche Informationen enthalten. 

HTML-Elemente werden immer sequenziell angeordnet oder ineinander verschachtelt. Dadurch ergibt sich eine Baumstruktur, der sogenannte **HTML-Dokumentenbaum**. 

### Syntax 

- alle Tags schließen

- Leere Elemente schließen

  - z.B. Tag für einen Zeilenumbruch

  - ```html
    # leere Elemente schließen, .B. <br>-Tag für einen Zeilenumbruch
    <br />
    ```

- keine kreuzweise Verschachtelung

  - ```html
    <p><i>Kursiver Text</i></p>
    ```

- Einheitlich Kleinbuchstaben für Tag-Namen verwenden
- Einheitlich Kleinbuchstaben für Attributnamen
- Werte von Attributen in Anführungszeichen
- Keine Leerzeichen in Attributzuweisungen
- Keine unnötigen Leerzeichen und Leerzeilen
- Dateinamen
  - in Kleinbuchstaben mit Unterstrichen (html_syntax.html)
  - Dateiendung für HTML: *.html* oder *.htm*
  - Dateiendung für CSS: *.css*
  - Dateiendung für JavaScript: *.js*
- Leerzeichen statt Tabulatoren für die Einrückung verwenden (Beachte: Coding Convention only)

### Elemente

**Kopf (Header)** eines Dokuments enthält Informationen über das Dokument - Meta-Informationen. 

Header wird umschlossen von <header>...</header>

Folgende Tags können verwendet werden.

- *title*: Titel der Seite zur Anzeige in der Browser-Kopfleiste

- *base*: Basis-URL für alle URLs in der HTML-Datei

- *style*: Definition von CSS-Styles

- *link*: Einbettung externer Ressourcen, z.B. CSS-Dateien

- *script*: JavaScript für das Dokument oder Einbettung einer externen JavaScript-Datei

- *noscript*: alternativer Seiteninhalt für Browser, die kein JavaScript ausführen können

- *meta*: Metainformationen für das Dokument, z.B. 

- ```html
  <meta name="author" content="Martin Stephan">
  <meta name="keywords" content="HTML, CSS, ...">
  <meta charset="UTF-8">
  <meta http-equiv="refresh" content="10">
  ```

Der **Body** beinhaltet den eigentlichen Inhalt eines HTML-Dokuments. 

Body wird eingefasst von <body>...</body> - Tags.

Man unterscheidet zwischen 

- Block-Elementen - bestimmen Block-basierte Strukturen im Body des Dokuments
- Inline-Elementen - befinden sich im Fließtext

Mittels CSS kann für viele Elemente festgelegt werden, ob diese als Block- oder Inline-Elemente behandelt werden sollen. 

Die wichtigsten Text- Strukturelemente sind:

```html
<p> Paragraph, Absatz </p>
<div> Division, Abschnitt </div>
<h1> bis </h1> <h6> (Zwischen-)Überschriften absteigender Wichtigkeit</h6>
<span> Abschnitte in Fließtext </span>
<blockquote> Zitate </blockquote>
<i> italics, kursiv </i>
<b> bold, fettgedruckt </b>
# ohne schließenden End-Tag
<hr> horizontal rule, horizontale Linie
<br> break, Zeilenumbruch
```

Es gibt weiterer Strukturelemente - sogenannte semantische Elemente.

```html
<section></section>
<article></article>
<header></header>
<footer></footer>
<aside></aside>
<nav></nav>
#...
```

**Hyperlinks**

HTML kennt verschiedene Typen von Hyperlinks.

- Unsichtbare Links; werden im Hintergrund automatisch vom Browser bearbeitet - <link>
- Sichtbare Links; werden durch einen Mausklick des Nutzers aktiviert - <a>

Das <a>-Element kann für verschiedene Zwecke genutzt werden

- Markierungen (Ankerpunkte) - <a name="ziel"></a>
- Sprung zu einem Ankerpunkt - 
- Sprung zu einem externen Ziel - URL kann absolut oder relativ sein
- <a>-Tags kennt neben href auch weitere Attribute 
  - target

**Bilder**

Bilder haben einen eigenen Tag: <img> (ohne Endtag)

Wichtige Attribute:

- *src*: URL, bei der das Bild liegt
- *alt*: alternativer Text, der angezeigt wird, wenn das Bild nicht geladen oder angezeigt werden kann
- *height* / *width*: Höhe und Breite, in der das Bild angezeigt werden soll

```html
<a href="https://www.bilder.de" target="_blank">
    <img src="/img/lustig.png" alt="Das ist lustig" />
</a>
```

**Inhalte**

```html
# ungeordnete Listen mit Listenelement
<ul>
    <li></li>
</ul>
# geordnete Listen
<ol>
    <li></li>
</ol>

```

**Tabellen**

```html
# Tabellen
<table>
    <tr> neue Zeile in einer Tabelle </tr>
    <td> neue Zeile in einer Tabellenzeile </td>
    <th> Auszeichnung spezieller Zeilen für den Tabellenkopf </th>
</table>

<thead></thead>
<tbody></tbody>
<tfoot></tfoot>

# spezielle Attribute für <td></td>
# colspan
# rowspan

# Beschriftung
<caption>...</caption>
```

Formatierung der Tabelle erfolgt mittels CSS.

**Formulare**

Um Daten vom Browser zum Server senden zu können, gibt es die HTML Formulare. 

Formulare werden mit <form>-Tag erzeugt.

```html
<form action="/login" method="POST">
    # action: Gibt Ziel des Formulars an
    # method: Gibt HTTP-Methode an, mit der das Formular gesendet wird
</form>

# grundlegende Eingabefelder 
# <input type="text"> - Texteingabefeld
# <input type="password"> - Texteingabefeld für Passwörter, Eingabe wird nicht angezeigt 
# <input type="radio"> - Radio Button
# <input type="checkbox"> - Boxen mit Häkchen für Mehrfachauswahl

# Auswahlfeld zum Ausklappen
<select name="bestellung">
    <option>Hamburger</option>
    <option>Cheeseburger</option>
    <option>Veggieburger</option>
</select>

// Textfeld für mehrzeiligen Text
<textarea rows="5" cols="20"></textarea>

// Button zum Absenden des Formulars
<input type="submit" value="Senden" />

// Eingabefelder
// Zahlenbereiche können mit Slider ausgewählt werden
<input type="range" min="0" max="10">

// Vorschläge mit (Auto-)Vervollständigung
<input type="text" list="browsers">
<datalist name="browsers">
	<option>Firefox</option>
    <option>Internet Explorer</option>
</datalist>

// Eingabefelder für numerische Werte
<input type="number" value="100">

// Eingabefelder mit Eingabevalidierung
<input type="email">
<input type="url">

// Farbauswahl mit 'Color Picker'
<input type="color">

// Eingabefelder für Zeit und Datum
<input type="datetime-local">

// Attribute für Eingaberestriktionen
// max, min
// required
// Pattern

// Weitere Attribute
// placeholder
<input type="email" placeholder="Ihre E-Mail Adresse">

// Multimedia Inhalte
// Tags für <audio> und <video> erlauben es, Multimedia-Dateien direkt mit dem Browser abzuspielen
// Bedienelemente können mit CSS gestaltet werden
```

Betriebssysteme bzw. Browser benötigen für Wiedergabe Codecs. Für HTML5 sind vorgesehen:

- Audio: mp3, wma, AAC, Ogg Vorbis
- Video: H.264, Ogg Theora, WebM

Alternative Quellen, z.B. für unterschiedliche Codecs oder Bitraten können mit <source>-Tag angegeben werden. 

```html
<audio>
	<source src="/audio/track1.wma" type="audio/x-ms-wma">
    <source src="/aduio/track1.mp3" type="audio/mpeg">
</audio>
```

Browser spielt das erste <source->Element ab, über dessen Codec der Browser verfügt. 

Unbekannte Tags werden vom Browser ignoriert; deshalb entsprechenden Hinweis für ältere Browser hinzufügen. 

Eine Zeichenfläche für Bitmap-Grafiken bietet das <canvas>-Tag.  Auf Canvas kann mit JavaScript gezeichnet werden.

```html
<canvas id="example" width="250" height="250">
    Ihr Browser unterstützt HTML 5 Canvas nicht. 
</canvas>

<script type="text/javascript">
    // Zugriff auf Canvas-Element über Variablen
    const example = document.querySelector('#example');
    const context = example.getContext('2d');
    
    // Blau als Füllfarbe
    context.fillstyle = "rgb(0,0,255)";
    
    // Quadrat zeichnen
    context.fillRect(50,10,100,100);
</script>
```

Weitere Features sind z.B. Tags wie <time>, <meter> oder <progress>.

## CSS - Cascading Stylesheets

CSS beschreibt die Darstellung (Layout) eines HTML-Dokuments (z.B. Schriftarten, Schriftgrößen, ...)

### Darstellung





## XML - Extensible Markup Language 



## Literatur 

[1] openHPI, Zum Web-Profi in drei Schritten, https://open.hpi.de/courses/webtech-exam-2, abgerufen am 1.11.2022

[2] HTML Tag-Referenz, https://www.w3schools.com/tags/, abgerufen am 1.11.2022

[3] HTML elements reference, https://developer.mozilla.org/de/docs/Web/Html/Element, abgerufen am 1.11.2022

[4] Browser-Unterstützung, https://caniuse.com, abgerufen am 1.11.2022


