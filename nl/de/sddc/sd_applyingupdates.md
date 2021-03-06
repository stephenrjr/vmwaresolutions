---

copyright:

  years:  2016, 2019

lastupdated: "2019-03-12"

subcollection: vmwaresolutions


---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Updates auf Cloud Foundation-Instanzen anwenden
{: #sd_applyingupdates}

Die {{site.data.keyword.vmwaresolutions_full}}-Konsole führt laufend Erkennungen durch und listet die verfügbaren Software-Updates auf, die Sie auf Ihre virtuelle VMware-Umgebung anwenden können.

Ein verfügbares Update ist ein Eintrag in der Liste der Software-Updates für die Instanz, das sofort angewendet oder für einen späteren Zeitpunkt geplant werden kann. Das Update ist ein Bundle, das eines oder mehrere Pakete für die Aktualisierung der IBM Managementkomponenten und der VMware-Komponenten enthält.

IBM CloudDriver-Updates werden nicht mehr aufgelistet, da automatisches Updates aktiviert sind. Durch Aktionen wie das Hinzufügen eines ESXi-Servers, das Hinzufügen eines Clusters und das Bestellen eines Service wird die Instanz automatisch auf die aktuelle Version aktualisiert. Weitere Informationen zu automatischen Aktualisierungen finden Sie im Abschnitt zur *IBM CloudDriver-Ausfallsicherheit* in den [Releaseinformationen für Version 2.5](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-relnotes_v25).
{:note}

## Vorbereitende Schritte
{: #sd_applyingupdates-prereq}

Bevor Sie versuchen, ein Update anzuwenden, erweitern Sie den Update-Eintrag, indem Sie auf den Abwärtspfeil klicken und die folgenden Informationen überprüfen:
* Überprüfen Sie die Version des Updates. Sie müssen die Updates in chronologischer Reihenfolge anwenden, also zuerst das älteste Update und zuletzt das neueste Update. Stellen Sie sicher, dass Sie alle vorherigen Updates angewendet haben, bevor Sie das aktuelle Update anwenden. Beispielsweise müssen Sie das Update für V2.4 anwenden, bevor Sie versuchen, das Update für V2.5 anzuwenden.
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

## Vorgehensweise zum Anwenden von Updates auf Cloud Foundation-Instanzen
{: #sd_applyingupdates-procedure}

1. Klicken Sie in der {{site.data.keyword.vmwaresolutions_short}}-Konsole im linken Navigationsfenster auf **Ressourcen**.
2. Klicken Sie in der Tabelle **Cloud Foundation-Instanzen** auf die Instanz, die Sie aktualisieren wollen.
3. Überprüfen Sie auf der Seite **Zusammenfassung**, ob alle Instanzdetails korrekt angezeigt werden. Klicken Sie dann im linken Navigationsfenster auf **Infrastruktur**, um die Details auf der Seite **Infrastruktur** zu prüfen.
   Wenn die Details nicht angezeigt werden, kann dies auf ein Konnektivitätsproblem mit der virtuellen Serverinstanz (VSI) von IBM CloudDriver hinweisen, das aufgrund eines Problems mit einer Firewallregel oder aufgrund eines anderen Netzproblems aufgetreten ist. Lösen Sie das Problem, bevor Sie mit dem nächsten Schritt fortfahren, da das Update andernfalls fehlschlagen könnte.
4. Klicken Sie im linken Navigationsfenster auf **Update und Patch**.
5. Klicken Sie auf den Abwärtspfeil, um das Update zu erweitern, das Sie anwenden möchten, und führen Sie dann einen der folgenden Schritte aus:
   *  Um das Update sofort zu starten, klicken Sie auf das Überlaufmenüsymbol in der Spalte **Aktionen** des Update-Eintrags und anschließend auf **Update jetzt ausführen**.
   *  Um ein künftiges Update zu planen, klicken Sie auf das Überlaufmenüsymbol in der Spalte **Aktionen** des Update-Eintrags und anschließend auf **Update planen**. Wählen Sie das Datum, die Uhrzeit und die Zeitzone für den Start des Updates aus. Klicken Sie auf **OK**.
6. Falls Sie Updates auf Cloud Foundation-Instanzen in Bereitstellungskonfigurationen mit mehreren Standorten anwenden, wird ein Abschnitt namens **Für Update erforderliche Schritte** angezeigt, in dem die Updateoperationen aufgelistet sind, die für alle Instanzen in der Bereitstellung mit mehreren Standorten erforderlich sind. Sie müssen die Schritte nacheinander ausführen, indem Sie für jeden Schritt auf **Update anwenden** klicken. Vor dem Starten des nächsten Schritts müssen Sie warten, bis der vorherige Schritt abgeschlossen wurde.

## Ergebnisse
{: #sd_applyingupdates-results}

1. Vor dem Start einer Updateoperation wird eine Zustandsprüfung für die Instanz ausgeführt. Wenn die Zustandsprüfung fehlschlägt, werden Sie benachrichtigt, damit Sie das Problem lösen können, bevor Sie das Update anwenden.
2. Während Updates, die auch VMware-Komponenten aktualisieren, müssen VMs möglicherweise aus ESXi-Servern migriert werden, damit sie in den Wartungsmodus versetzt werden. Die VM-Migration wird möglicherweise verhindert, wenn eine virtuelle Maschine einen lokalen Datenspeicher enthält oder eine CD-ROM angehängt ist.
3. Bei der Bereitstellung einer neuen Umgebung erstellt {{site.data.keyword.vmwaresolutions_short}} die ID **automationuser**, die für das Instanzmanagement verwendet wird, zu dem auch das Anwenden von Updates gehört. Ändern Sie das Kennwort für diese Benutzer-ID nicht. Das Ändern des Kennworts kann dazu führen, dass das Update fehlschlägt.

4. Nachdem Sie ein Update angewendet haben, wird in der Statusliste der Software-Updates ein Eintrag angezeigt, der Aufschluss über den detaillierten Verarbeitungsfortschritt und den Status des Updates gibt. Sobald das Update erfolgreich abgeschlossen wurde, wird in der Liste der installierten Software-Updates ein Eintrag angezeigt.

  Um den aktuellen Status für einen Update-Job abzufragen, klicken Sie in der rechten oberen Ecke der Seite auf das Aktualisierungssymbol.
  {:tip}

5. Weitere Informationen zu den Statuswerten für Updates finden Sie in der folgenden Tabelle.

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

6. Falls der Updateprozess bei einem bestimmten Schritt fehlschlägt, [wenden Sie sich an den IBM Support](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support), um Unterstützung zu erhalten. Sie erhalten Hilfe bei der Lösung des Problems und Anweisungen, wie Sie das Upgrade beim fehlgeschlagenen Schritt erneut starten.

## Zugehörige Links
{: #sd_applyingupdates-related}

* [Übersicht über Cloud Foundation](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_cloudfoundationoverview)
* [Veeam on {{site.data.keyword.cloud_notm}} - Übersicht](/docs/services/vmwaresolutions/services?topic=vmware-solutions-veeam_considerations)
* [Kontaktaufnahme mit dem IBM Support](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_support)
* [Häufig gestellte Fragen](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq)
