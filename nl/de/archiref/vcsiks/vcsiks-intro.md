---

copyright:

  years:  2016, 2018

lastupdated: "2018-11-16"

---

# Einführung in vCenter Server und IBM Kubernetes Service

Dieses Dokument enthält eine Übersicht über den Prozess der Anwendungsmodernisierung auf {{site.data.keyword.cloud}}. Der Schwerpunkt liegt hier auf den Netzaspekten der folgenden Plattformen, damit eine integrierte Umgebung mit mehreren Clouds für die Anwendungsmodernisierung genutzt werden kann:

Dieses Dokument enthält eine Übersicht über den Prozess der Anwendungsmodernisierung auf {{site.data.keyword.cloud_notm}}. Dabei liegt der Fokus auf den Cloud-Management-Komponenten, damit eine integrierte Umgebung mit mehreren Clouds für die Anwendungsmodernisierung genutzt werden kann:

- **VMware vCenter Server on {{site.data.keyword.cloud_notm}}** - vCenter Server ist ein Angebot von {{site.data.keyword.vmwaresolutions_full}} und stellt eine VMware-basierte Plattform dar, die automatisch auf {{site.data.keyword.cloud_notm}} eingerichtet wird.
- **{{site.data.keyword.cloud_notm}} Private** - ICP ist eine Anwendungsplattform für die Entwicklung und Verwaltung von containerisierten Anwendungen, die auf virtualisierten Infrastrukturplattformen, wie z. B. VMware, bereitgestellt werden.
- **IBM Kubernetes Services** - IKS ist ein verwalteter Service auf {{site.data.keyword.cloud_notm}}, der Kubernetes als Orchestrierungsengine für die Automatisierung der Bereitstellung, die Skalierung und den Betrieb von Anwendungscontainern in einem Cluster mit einem Tenant verwendet.
- **IBM Multi-Cluster Manager** - MCM bietet Benutzertransparenz, anwendungsorientiertes Management (Richtlinien, Bereitstellungen, Vitalität, Betrieb) und die richtlinienbasierte Konformität über Clouds und Cluster hinweg. Mit MCM erhalten Sie die Kontrolle über Ihre Kubernetes-Cluster.
- **{{site.data.keyword.cloud_notm}} Automation Manager** - CAM ist eine Self-Service-Managementplattform für mehrere Clouds, die unter ICP ausgeführt wird und die Entwickler und Administratoren in die Lage versetzt, die Anforderungen des Unternehmens zu erfüllen.

## Anwendungsmodernisierung auf IBM Cloud
Der Begriff "Anwendungsmodernisierung" bezeichnet den Prozess, mit dem vorhandene Anwendungen zur Nutzung neuer Entwicklungs- und Bereitstellungsstrategien in der Cloud geändert werden. Kunden suchen heute nach innovativen und effizienten Methoden, die ihnen helfen, diesen Übergang unter Berücksichtigung der Geschäfts- und Anwendungskomplexität zu ermöglichen.

Unternehmen müssen ihre Produkte heute immer schneller auf den Markt bringen. Ihr Kapital sind dabei nicht nur die Anwendungen, sondern Daten, Prozesse, Geschäftslogik und Benutzerschnittstellen, die sämtlich angepasst werden müssen, um mit neuen Geschäftsanforderungen Schritt zu halten.

Die Anwendungsmodernisierung bietet u. a. folgende Vorteile:
- Verbesserte Entwicklerproduktivität
- Erhöhte betriebliche Effizienz
- Geringere Kosten für den Aufbau neuer Funktionalität
- Zeitnahe Bereitstellung von mehr Kapazität

IBM geht davon aus, dass 70% der eingesetzten privaten Clouds durch die Notwendigkeit der Modernisierung von Anwendungsumgebungen motiviert sind. Die meisten Unternehmen verfolgen bei der Anwendungsmodernisierung jedoch einen stufenweisen Ansatz, was Hybridumgebungen und Umgebungen mit mehreren Clouds erforderlich macht. Die Szenarien zeichnen sich durch folgende Merkmale aus:
- Komplexe und monolithische traditionelle Anwendungen, die in der Regel auf Mainframes oder UNIX-Systemen ausgeführt werden, werden weiterhin lokal betrieben.
- x86-Umgebungen, die für Systems of Record (SoR) verwendet werden, oder Anwendungen, die sicherheitskritische oder regulierte Workloads beinhalten, werden in eine virtualisierte Infrastruktur oder in eine private Cloud verlegt.
- Anwendungen wie SAP oder High-Performance Computing nutzen Bare-Metal-Ressourcen.
- Sicherheitskritische und einige regulierte Workloads, die in die öffentliche Cloud verlegt werden können, werden in dedizierte Umgebungen verlagert.
- Systems of Engagement (SoE) wie z. B. Web, Mobile, IoT, AI oder Video werden in öffentliche Clouds verlagert.

Ein gängiges Vorgehen ist beispielsweise, die Front-End-SOE-Anwendungen als Container mit Datenbanken bereitzustellen und traditionelle Middleware auf VMs in einer private Cloud bereitzustellen.

Da Ihre IT-Infrastruktur und Ihre Geschäftsanforderungen individuell sind, benötigen Sie einen Modernisierungsansatz, der die Bereitstellung des geschäftlichen Nutzens beschleunigt, Ihre Risiken mindert und Ihre vorhandenen Investitionen schützt. IBM bietet genau diesen Ansatz, der angepasst werden kann, sodass er Ihren individuellen geschäftlichen und technologischen Anforderungen hinsichtlich der Anwendungsmodernisierung entspricht.

Dieses Dokument ist eine von fünf Veröffentlichungen, die die verschiedenen Technologien, die bei der Anwendungsmodernisierung hin zur {{site.data.keyword.cloud_notm}} verwendet werden, aus verschiedenen Blickwinkeln beleuchten:

* [vCenter Server und {{site.data.keyword.cloud_notm}} Private](../vcsicp/vcsicp-intro.html) - Referenzarchitektur für die Bereitstellung der folgenden Plattformen:
  - **VMware vCenter Server on {{site.data.keyword.cloud_notm}}** - Dies ist ein Angebot von {{site.data.keyword.vmwaresolutions_full}} und stellt eine VMware-basierte Plattform dar, die automatisch auf {{site.data.keyword.cloud_notm}} eingerichtet wird.
  - **{{site.data.keyword.cloud_notm}} Private** - Eine Anwendungsplattform für die Entwicklung und Verwaltung von containerisierten Anwendungen. Bei ICP handelt sich um eine integrierte Umgebung, die Kubernetes als Container-Orchestrator und ein privates Image-Repository, eine Managementkonsole, Überwachungsframeworks und eine grafische Benutzerschnittstelle enthält, von der aus Sie Ihre Anwendungen zentral bereitstellen, verwalten, überwachen und skalieren können.
  - **{{site.data.keyword.cloud_notm}} Automation Manager** - Eine auf Unternehmen abgestimmte IaC-Plattform (IaC = Infrastructure as Code), die eine zentrale Bereitstellung von VMware-basierten Workloads neben Kubernetes-basierten Workloads bietet und bei der Sie Vorlagen verwenden können, die in einem Repository gespeichert und versioniert werden.
* [vCenter Server und {{site.data.keyword.cloud_notm}} Private](../vcsiks/vcsiks-intro.html) - Referenzarchitektur für die Bereitstellung der folgenden Plattformen:
  - **VMware vCenter Server on {{site.data.keyword.cloud_notm}}** - Dies ist ein Angebot von {{site.data.keyword.vmwaresolutions_full}} und stellt eine VMware-basierte Plattform dar, die automatisch auf {{site.data.keyword.cloud_notm}} eingerichtet wird.
  - **{{site.data.keyword.cloud_notm}} Kubernetes Service** - Ein verwalteter Service auf {{site.data.keyword.cloud_notm}}, der Kubernetes als Orchestrierungsengine für die Automatisierung der Bereitstellung, die Skalierung und den Betrieb von Anwendungscontainern in einem Cluster mit einem Tenant verwendet.
* [vCenter Server-Netzbetrieb](../vcsnsxt/vcsnsxt-intro.html) - Ein Leitfaden, der sich auf die Netztechnologien konzentriert, die in vCenter Server, ICP und IKS eingesetzt werden (z. B. NSX-V, NSX-T und Calico).
* [VMware und Concept Car "Skate Advisor"](../vcscar/vcscar-intro.html) - Diese Referenzarchitektur ist ein so genanntes "Concept Car", also ein Mechanismus, der in einer Art Designstudie Technologien zur Lösung von realen Problemen herausstellt und demonstriert. Sie soll auf realistische Weise eine Interaktion zwischen Watson AI und maschinellem Lernen veranschaulichen. Anhand der Skateboarding-Szene werden Cloud-Services auf verständliche Weise erläutert. Die Implementierung der Designstudie erweitert die Anwendung "Acme Skateboard" durch das Tool "Skate Advisor". Mit dem Tool "Skate Advisor" können sich Benutzer durch eine Watson-gesteuerte Engine über Skateboard-Tricks austauschen. 
* [VMware: Modernisierung der Anwendung "Stock Trader"](../vcscontent/vcscontent-modjourney.html) - Dieser Referenzanwendungsfall beschreibt die Modernisierung einer klassischen WebSphere Application Server-Anwendung mit {{site.data.keyword.cloud_notm}} Private, IBM Middleware-Inhalten, {{site.data.keyword.cloud_notm}} Kubernetes Service und vCenter Server on {{site.data.keyword.cloud_notm}}. Alle sind auf dem Weg zur Cloud, aber jeder befindet sich an einer anderen Etappe dieser Strecke. Schritt für Schritt wird die bestehende Anwendung "Stock Trader" von der Anwendungsarchitektin Jane und dem Cloudinfrastrukturarchitekten Todd modernisiert. Die Referenz zeigt anhand von Beispielen, wie Sie die einzelnen Schritte im Prozess ausführen und welchen Wert jeder Schritt ungeachtet seiner Größe für Ihr Unternehmen hat. Der Fokus liegt auf vier Themen: Anwendungen, DevOps, Integration und Management. Diese Bereiche sind bei der Umsetzung Ihrer Ziele eng verzahnt und die Modernisierung lediglich eines einzigen Bereiches führt faktisch zu Problemen in allen Bereichen.

### Zugehörige Links

* [Übersicht über vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle](../vcs/vcs-hybridity-intro.html)