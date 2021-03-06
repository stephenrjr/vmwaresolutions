---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-04"

subcollection: vmwaresolutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Updates auf vCenter Server-Instanzen anwenden
{: #vc_applyingupdates}

Der Prozess zur Anwendung von Patches und Updates für vCenter Server-Instanzen wurde nur für Managementkomponenten automatisiert. Die VMware-Updates müssen hingegen manuell angewendet werden.

## Vorbereitende Schritte
{: #vc_applyingupdates-prereq}

Wenn Sie ein Upgrade einer vCenter Server-Instanz auf eine vCenter Server with Hybridity Bundle-Instanz durchführen möchten, müssen Sie zunächst mindestens das Basis-Software-Update für vCenter Server V2.3 anwenden. Dies müssen Sie tun, bevor Sie das Upgrade auf Hybridity Bundle durchführen können.
{:important}

Business Partner-Benutzer haben nicht die Option, für eine vorhandene vCenter Server-Instanz ein Upgrade auf eine vCenter Server with Hybridity Bundle-Instanz durchzuführen.

Ab Version 2.5 werden IBM CloudDriver-Updates nicht mehr aufgelistet, da automatische Aktualisierungsfunktionalität aktiviert ist. Durch Aktionen wie das Hinzufügen eines Hosts, Hinzufügen eines Clusters und Bestellen eines Service wird die Instanz automatisch auf die aktuelle Version aktualisiert. Weitere Informationen zu automatischen Aktualisierungen finden Sie im Abschnitt zur *IBM CloudDriver-Ausfallsicherheit* in den [Releaseinformationen für Version 2.5](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-relnotes_v25).
{:note}

Bevor Sie versuchen, ein Update anzuwenden, erweitern Sie den Update-Eintrag, indem Sie auf den Abwärtspfeil klicken und die folgenden Informationen überprüfen:
* Überprüfen Sie die Version des Updates. Sie müssen die Updates in chronologischer Reihenfolge anwenden, also zuerst das älteste Update und zuletzt das neueste Update. Stellen Sie sicher, dass Sie alle vorherigen Updates angewendet haben, bevor Sie das aktuelle Update anwenden. Beispielsweise müssen Sie das Update für V2.3 anwenden, bevor Sie versuchen, das Update für V2.4 anzuwenden.
* Ermitteln Sie, ob eine Ausfallzeit erforderlich ist.
* Prüfen Sie die geschätzte Gesamtzeit für die Ausführung des Updates.
* Stellen Sie fest, wie sich das Update auf die virtuelle VMware-Umgebung auswirkt. Tabelle 1 zeigt, wie sich die verschiedenen Aktualisierungsstufen auf das System auswirken.
* Lesen Sie die Details über das Update.

Tabelle 1. Aktualisierungsstufen und Auswirkungen

<table>
  <tr>
    <th>Aktualisierungsstufe</th>
    <th>Auswirkung</th>
  </tr>
  <tr>
    <td>Niedrig</td>
    <td>Dieses Update hat keine Auswirkungen auf Systeme. Sie müssen es nicht während einer geplante Ausfallzeit anwenden.</td>
  </tr>
  <tr>
    <td>Mittel</td>
  <td>Dieses Update kann sich auf einige Systeme auswirken. Es empfiehlt sich, es während einer geplanten Ausfallzeit anzuwenden.</td>
  </tr>
    <tr>
    <td>Bedeutend</td>
  <td>Dieses Update wirkt sich auf einige oder alle Systeme aus. Sie müssen es während einer geplanten Ausfallzeit anwenden.</td>
  </tr>
</table>

## Verfahren zum Anwenden von Aktualisierungen und Patches auf vCenter Server-Instanzen (V2.1 oder höher)
{: #vc_applyingupdates-procedure}

Dieses Verfahren gilt für Instanzen, die in V2.1 oder höher bereitgestellt werden. Bei Instanzen, die in V2.0 und früheren Versionen bereitgestellt wurden, müssen Sie die VMware-Updates manuell anwenden.

1. Klicken Sie in der {{site.data.keyword.vmwaresolutions_full}}-Konsole im linken Navigationsfenster auf **Ressourcen**.
2. Klicken Sie in der Tabelle **vCenter Server-Instanzen** auf die Instanz, die Sie aktualisieren wollen.
3. Überprüfen Sie auf der Seite **Zusammenfassung**, ob alle Instanzdetails korrekt angezeigt werden. Klicken Sie dann im linken Navigationsfenster auf **Infrastruktur**, um die Details auf der Seite **Infrastruktur** zu prüfen.
   Wenn die Details nicht angezeigt werden, kann dies auf ein Konnektivitätsproblem mit der virtuellen Serverinstanz (VSI) von IBM CloudDriver hinweisen, das aufgrund eines Problems mit einer Firewallregel oder aufgrund eines anderen Netzproblems aufgetreten ist. Lösen Sie das Problem, bevor Sie mit dem nächsten Schritt fortfahren, da das Update andernfalls fehlschlagen könnte.
4. Klicken Sie im linken Navigationsfenster auf **Update und Patch**.

   Die Seite **Update und Patch** für eine Instanz enthält nur die Pakete für die Aktualisierung der IBM Managementkomponenten, nicht jedoch die VMware-Updates. VMware-Updates müssen manuell angewendet werden.   {{site.data.keyword.vmwaresolutions_short}} wendet VMware-Updates für die folgenden Operationen an:
   * Wenn eine neue vCenter Server-Instanz bereitgestellt wird.
   * Wenn neue ESXi-Server hinzugefügt werden, werden die neuen ESXi-Server mit VMware-Aktualisierungen bereitgestellt, die vorhandenen ESXi-Server werden jedoch nicht aktualisiert.
   * Wenn neue Cluster hinzugefügt werden, werden die neuen Cluster mit VMware-Aktualisierungen bereitgestellt, die vorhandenen Cluster werden jedoch nicht aktualisiert.
   {:note}

5. Klicken Sie für NSX-Lizenzaktualisierungen auf **Upgrade**. Wählen Sie im Fenster für das Upgrade von NSX-Lizenzeditionen ****die Edition aus, auf die das Upgrade durchgeführt werden soll, und klicken Sie dann auf **Upgrade**. Downgrades für Lizenzeditionen sind nicht verfügbar.

   Die Aktualisierung der Lizenz ersetzt alle vorhandenen NSX-Lizenzen in der Instanz. Zusätzliche Gebühren können bei einer Überschneidung von alten und neuen Lizenzen entstehen, wenn Sie ein Upgrade in der Mitte eines Abrechnungszyklus durchführen. Um zusätzliche Gebühren zu vermeiden, wird empfohlen, die Lizenz am Ende des Abrechnungszyklus zu aktualisieren.
   {:note}

6. Klicken Sie bei Software-Updates auf den Abwärtspfeil, um das Update zu erweitern, das Sie anwenden möchten, und führen Sie dann einen der folgenden Schritte aus:
   *  Um das Update sofort zu starten, klicken Sie auf das Überlaufmenüsymbol in der Spalte **Aktionen** des Update-Eintrags und anschließend auf **Update jetzt ausführen**.
   *  Um ein künftiges Update zu planen, klicken Sie auf das Überlaufmenüsymbol in der Spalte **Aktionen** des Update-Eintrags und anschließend auf **Update planen**. Wählen Sie das Datum, die Uhrzeit und die Zeitzone für den Start des Updates aus. Klicken Sie auf **OK**.
7. Falls Sie Updates auf vCenter Server-Instanzen in Bereitstellungskonfigurationen mit mehreren Standorten anwenden, wird ein Abschnitt namens **Für Update erforderliche Schritte** angezeigt. In diesem Abschnitt werden die Updateoperationen aufgelistet, die für alle Instanzen in der Bereitstellung mit mehreren Standorten erforderlich sind. Sie müssen die Schritte nacheinander ausführen, indem Sie für jeden Schritt auf **Update anwenden** klicken. Vor dem Starten des nächsten Schritts müssen Sie warten, bis der vorherige Schritt abgeschlossen wurde.   

## Vorgehensweise zum Durchführen eines Upgrades auf eine vCenter Server with Hybridity Bundle-Instanz
{: #vc_applyingupdates-procedure-upgrade-to-hybridity}

Während der Aktualisierung der Lizenz auf Hybridity Bundle wird für Sie automatisch ein Upgrade auf die VMware NSX Advanced Edition durchgeführt, wenn Ihre vCenter Server-Instanz momentan die VMware NSX Base Edition verwendet.

Wenn Sie ein Upgrade auf Hybridity Bundle durchführen und Ihre vCenter Server-Instanz bereits über NFS-Dateispeicher verfügt, entstehen keine Gebühren für den VMware vSAN-Speicher. Es entstehen Gebühren für die vSAN-Lizenz, da VMware vSAN in Hybridity Bundle enthalten ist.
{:note}

Führen Sie die folgenden Schritte aus, um für eine vCenter Server-Instanz ein Upgrade auf vCenter Server with Hybridity Bundle durchzuführen.

1. Klicken Sie in der {{site.data.keyword.vmwaresolutions_short}}-Konsole im linken Navigationsfenster auf **Ressourcen**.
2. Klicken Sie in der Tabelle **vCenter Server-Instanzen** auf die Instanz, für die Sie ein Upgrade durchführen wollen.
3. Überprüfen Sie auf der Seite **Zusammenfassung**, ob alle Instanzdetails korrekt angezeigt werden. Klicken Sie dann im linken Navigationsfenster auf **Infrastruktur**, um die Details auf der Seite **Infrastruktur** zu prüfen.
   Wenn die Details nicht angezeigt werden, kann dies auf ein Konnektivitätsproblem mit der IBM CloudDriver-VSI hinweisen, das aufgrund eines Problems mit einer Firewallregel oder aufgrund eines anderen Netzproblems aufgetreten ist. Lösen Sie das Problem, bevor Sie mit dem nächsten Schritt fortfahren, da das Update andernfalls fehlschlagen könnte.
4. Klicken Sie im linken Navigationsfenster auf **Update und Patch**.
5. Wenn Sie die Aktualisierung der Lizenz für Hybridity Bundle an. Klicken Sie in der Tabelle **Aktualisierungen der Lizenz** in der Spalte **Aktion** auf **Upgrade**, überprüfen Sie die geschätzten Kosten und klicken Sie dann auf **Upgrade**.
6. Stellen Sie optional den Service "VMware HCX on {{site.data.keyword.cloud_notm}}" bereit. Wenn Hybridity Bundle in der Tabelle **Aktualisierungen der Lizenz** aktiviert ist, führen Sie die folgenden Schritte aus:
  1. Klicken Sie in der Tabelle **Aktualisierungen der Lizenz** in der Spalte **Aktion** auf **HCX on {{site.data.keyword.cloud_notm}} bereitstellen**.
  2. Blättern Sie zur Karte **HCX on {{site.data.keyword.cloud_notm}}** und klicken Sie dann auf **Service auswählen**.
  3. Blättern Sie abwärts und geben Sie die erforderlichen Einstellungen für den Service an. Klicken Sie dann auf **Weiter**.
  4. Überprüfen Sie die Bedingungen, die für den Service gelten, überprüfen Sie die geschätzten Kosten und klicken Sie dann auf **Bestellung aufgeben**.

## Ergebnisse
{: #vc_applyingupdates-results}

1. Nachdem Sie ein Update angewendet haben, wird in der Statusliste der Software-Updates ein Eintrag angezeigt, der Aufschluss über den detaillierten Verarbeitungsfortschritt und den Status des Updates gibt. Sobald das Update erfolgreich abgeschlossen wurde, wird in der Liste der installierten Software-Updates ein Eintrag angezeigt.

  Klicken Sie zum Abrufen des aktuellen Status für einen Update-Job auf das Aktualisierungssymbol in der rechten oberen Ecke der Seite.
  {:tip}

2. Details zu den Statuswerten für Updates finden Sie in der folgenden Tabelle.

   Tabelle 2. Details zu den Statuswerten für Updates

    <table>
      <tr>
        <th>Status</th>
        <th>Details</th>
      </tr>
      <tr>
        <td>Verfügbar</td>
        <td>Das Update ist für eine Anwendung verfügbar. Sie können ein verfügbares Update erst dann auswählen, nachdem alle zugehörigen vorherigen Updates angewendet wurden.</td>
      </tr>
      <tr>
        <td>In Bearbeitung</td>
      <td>Der Update-Job wurde initialisiert, ist aber noch nicht beendet. Sie können keine anderen Updates anwenden, bis der aktuelle Update-Job abgeschlossen ist. </td>
      </tr>
        <tr>
        <td>Installiert</td>
      <td>Der Update-Job ist abgeschlossen. Die entsprechende Komponente der VMware-Plattform wurde aktualisiert.</td>
      </tr>
        <tr>
        <td>Fehlgeschlagen</td>
      <td>Der Update-Job ist fehlschlagen. In der Konsole wird ein Fehler für das Fehlschlagen des Updates gemeldet. Überprüfen Sie den Fehler und lösen Sie das gemeldete Problem, bevor Sie das Update erneut anwenden.</td>
      </tr>
          <tr>
        <td>Geplant</td>
      <td>Der Update-Job ist für einen späteren Zeitpunkt geplant. Er wird am geplanten Zeitpunkt automatisch gestartet.</td>
      </tr>
          <tr>
        <td>Unbekannt</td>
      <td>Der Status des Update-Jobs kann nicht abgerufen werden. Bitten Sie den IBM Support um Unterstützung.</td>
      </tr>
    </table>

3. Falls der Updateprozess bei einem bestimmten Schritt fehlschlägt, [wenden Sie sich an den IBM Support](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support), um Unterstützung zu erhalten. Sie erhalten Hilfe bei der Lösung des Problems und Anweisungen, wie Sie das Upgrade ab dem fehlgeschlagenen Schritt erneut versuchen.

## Zugehörige Links
{: #vc_applyingupdates-related}

* [Übersicht über vCenter Server](/docs/services/vmwaresolutions/vcenter?topic=vmware-solutions-vc_vcenterserveroverview)
* [Kontaktaufnahme mit dem IBM Support](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [Häufig gestellte Fragen](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
