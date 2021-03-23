---
title: Verwalten von Microsoft Graph Connectors für Microsoft Search
ms.author: monaray
author: monaray97
manager: mnirkhe
audience: Admin
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Verwalten von Microsoft Graph Connectors für Microsoft Search.
ms.openlocfilehash: cba50d8eb558b4d74ed46554dc155d4f275b1332
ms.sourcegitcommit: 5df252e6d0bd67bb1b4c59418aceca8369f5fe42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51031719"
---
<!-- markdownlint-disable no-inline-html -->

# <a name="monitor-your-connections"></a><span data-ttu-id="c625d-103">Ihre Verbindungen überwachen</span><span class="sxs-lookup"><span data-stu-id="c625d-103">Monitor your connections</span></span>

<span data-ttu-id="c625d-104">Um auf Ihre Connectors zugreifen und diese verwalten zu können, müssen Sie als Suchadministrator für Ihren Mandanten festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="c625d-104">To access and manage your connectors, you must be designated as a search administrator for your tenant.</span></span> <span data-ttu-id="c625d-105">Wenden Sie sich an Den Mandantenadministrator, um Sie für die Rolle des Suchadministrators zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c625d-105">Contact your tenant administrator to provision you for the search administrator role.</span></span>

## <a name="connection-operations"></a><span data-ttu-id="c625d-106">Verbindungsvorgänge</span><span class="sxs-lookup"><span data-stu-id="c625d-106">Connection Operations</span></span>

<span data-ttu-id="c625d-107">Navigieren Sie zur [Registerkarte Connectors](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) im [Microsoft 365 Admin Center](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="c625d-107">Navigate to the [Connectors tab](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/Connectors) in the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

<span data-ttu-id="c625d-108">Für jeden Connectortyp unterstützt [das Microsoft 365 Admin Center](https://admin.microsoft.com) die in der folgenden Tabelle aufgeführten Vorgänge:</span><span class="sxs-lookup"><span data-stu-id="c625d-108">For each connector type, the [Microsoft 365 admin center](https://admin.microsoft.com) supports the operations shown in the following table:</span></span>

<span data-ttu-id="c625d-109">Vorgang</span><span class="sxs-lookup"><span data-stu-id="c625d-109">Operation</span></span> | <span data-ttu-id="c625d-110">Microsoft Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="c625d-110">Graph connectors by Microsoft</span></span> | <span data-ttu-id="c625d-111">Partner- oder Graph-Connectors</span><span class="sxs-lookup"><span data-stu-id="c625d-111">Partner or Graph connectors</span></span>
--- | --- | ---
<span data-ttu-id="c625d-112">Hinzufügen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="c625d-112">Add a connection</span></span> | :heavy_check_mark: <span data-ttu-id="c625d-113">(Siehe [Setupübersicht](configure-connector.md))</span><span class="sxs-lookup"><span data-stu-id="c625d-113">(See [Setup overview](configure-connector.md))</span></span> | :x: <span data-ttu-id="c625d-114">(Verweisen Sie auf Ihre Partner- oder benutzerdefinierte Connectoradministrator-UX)</span><span class="sxs-lookup"><span data-stu-id="c625d-114">(Refer to your partner or custom-built connector admin UX)</span></span>
<span data-ttu-id="c625d-115">Löschen einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="c625d-115">Delete a connection</span></span> | :heavy_check_mark: | :heavy_check_mark:
<span data-ttu-id="c625d-118">Bearbeiten einer veröffentlichten Verbindung</span><span class="sxs-lookup"><span data-stu-id="c625d-118">Edit a published connection</span></span> | :heavy_check_mark: <span data-ttu-id="c625d-119">Name und Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c625d-119">Name and Description</span></span><br></br> :heavy_check_mark: <span data-ttu-id="c625d-120">Verbindungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="c625d-120">Connection settings</span></span><br></br> :heavy_check_mark: <span data-ttu-id="c625d-121">Eigenschaftenbezeichnungen</span><span class="sxs-lookup"><span data-stu-id="c625d-121">Property labels</span></span><br></br> :heavy_check_mark: <span data-ttu-id="c625d-122">Schema</span><span class="sxs-lookup"><span data-stu-id="c625d-122">Schema</span></span><br></br> :heavy_check_mark: <span data-ttu-id="c625d-123">Aktualisierungszeitplan</span><span class="sxs-lookup"><span data-stu-id="c625d-123">Refresh schedule</span></span><br></br> | :heavy_check_mark: <span data-ttu-id="c625d-124">Name</span><span class="sxs-lookup"><span data-stu-id="c625d-124">Name</span></span><br></br> :heavy_check_mark: <span data-ttu-id="c625d-125">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c625d-125">Description</span></span>
<span data-ttu-id="c625d-126">Bearbeiten einer Entwurfsverbindung</span><span class="sxs-lookup"><span data-stu-id="c625d-126">Edit a draft connection</span></span> | :heavy_check_mark: | :x:

## <a name="monitor-your-connection-state"></a><span data-ttu-id="c625d-129">Überwachen des Verbindungsstatus</span><span class="sxs-lookup"><span data-stu-id="c625d-129">Monitor your connection state</span></span>

<span data-ttu-id="c625d-130">Nachdem Sie eine Verbindung erstellt haben, wird die Anzahl der verarbeiteten Elemente auf der Registerkarte **Connectors** auf der **Seite Microsoft Search** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c625d-130">After you create a connection, the number of processed items shows on the **Connectors** tab on the **Microsoft Search** page.</span></span> <span data-ttu-id="c625d-131">Nachdem die anfängliche vollständige Durchforstung erfolgreich abgeschlossen wurde, wird der Fortschritt für regelmäßige inkrementelle Durchforstungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c625d-131">After the initial full crawl completes successfully, the progress for periodic incremental crawls displays.</span></span> <span data-ttu-id="c625d-132">Diese Seite enthält Informationen zu den täglichen Vorgängen des Connectors sowie eine Übersicht über die Protokolle und den Fehlerverlauf.</span><span class="sxs-lookup"><span data-stu-id="c625d-132">This page provides information about the connector's day-to-day operations and an overview of the logs and error history.</span></span>

<span data-ttu-id="c625d-133">Vier Zustände werden in der **Spalte Status** für jede Verbindung angezeigt:</span><span class="sxs-lookup"><span data-stu-id="c625d-133">Four states show up in the **State** column against each connection:</span></span>

* <span data-ttu-id="c625d-134">**Synchronisieren**.</span><span class="sxs-lookup"><span data-stu-id="c625d-134">**Syncing**.</span></span> <span data-ttu-id="c625d-135">Der Connector durchforstet die Daten aus der Quelle, um die vorhandenen Elemente zu indizieren und Aktualisierungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c625d-135">The connector is crawling the data from the source to index the existing items and make any updates.</span></span>

* <span data-ttu-id="c625d-136">**Ready**: Die Verbindung ist bereit, und es wird keine aktive Durchforstung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c625d-136">**Ready**: The connection is ready, and there's no active crawl running against it.</span></span> <span data-ttu-id="c625d-137">**Die letzte Synchronisierungszeit** gibt an, wann die letzte erfolgreiche Durchforstung passiert ist.</span><span class="sxs-lookup"><span data-stu-id="c625d-137">**Last sync time** indicates when the last successful crawl happened.</span></span> <span data-ttu-id="c625d-138">Die Verbindung ist so neu wie die letzte Synchronisierungszeit.</span><span class="sxs-lookup"><span data-stu-id="c625d-138">The connection is as fresh as the last sync time.</span></span>

* <span data-ttu-id="c625d-139">**Angehalten**.</span><span class="sxs-lookup"><span data-stu-id="c625d-139">**Paused**.</span></span> <span data-ttu-id="c625d-140">Die Durchforstungen werden von den Administratoren über die Pause-Option angehalten.</span><span class="sxs-lookup"><span data-stu-id="c625d-140">The crawls are paused by the admins through the pause option.</span></span> <span data-ttu-id="c625d-141">Die nächste Durchforstung wird nur ausgeführt, wenn sie manuell fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="c625d-141">The next crawl runs only when it's manually resumed.</span></span> <span data-ttu-id="c625d-142">Die Daten aus dieser Verbindung sind jedoch weiterhin durchsuchbar.</span><span class="sxs-lookup"><span data-stu-id="c625d-142">However, the data from this connection continues to be searchable.</span></span>

* <span data-ttu-id="c625d-143">**Fehler**.</span><span class="sxs-lookup"><span data-stu-id="c625d-143">**Failed**.</span></span> <span data-ttu-id="c625d-144">Die Verbindung hatte einen kritischen Fehler.</span><span class="sxs-lookup"><span data-stu-id="c625d-144">The connection had a critical failure.</span></span> <span data-ttu-id="c625d-145">Dieser Fehler erfordert manuellen Eingriff.</span><span class="sxs-lookup"><span data-stu-id="c625d-145">This error requires manual intervention.</span></span> <span data-ttu-id="c625d-146">Der Administrator muss basierend auf der angezeigten Fehlermeldung entsprechende Maßnahmen ergreifen.</span><span class="sxs-lookup"><span data-stu-id="c625d-146">The admin needs to take appropriate action based on the error message shown.</span></span> <span data-ttu-id="c625d-147">Daten, die bis zum Fehler indiziert wurden, sind durchsuchbar.</span><span class="sxs-lookup"><span data-stu-id="c625d-147">Data that was indexed until the error occurred is searchable.</span></span>

## <a name="monitor-your-index-quota-utilization"></a><span data-ttu-id="c625d-148">Überwachen der Indexkontingentauslastung</span><span class="sxs-lookup"><span data-stu-id="c625d-148">Monitor your index quota utilization</span></span>

<span data-ttu-id="c625d-149">Das verfügbare Indexkontingent und der verfügbare Verbrauch werden auf der Angebotsseite der Connectors angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c625d-149">The available index quota and consumption is displayed on the connectors landing page.</span></span>

![Indexkontingentauslastungsleiste](media/quota_utilization.png)
 
>[!NOTE]
><span data-ttu-id="c625d-151">Während des Vorschauzeitraums wurde jeder Organisation, die Graph-Connectors ausprobieren, ein kostenloses festes Kontingent von bis zu 2 Millionen Elementen für alle Verbindungen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="c625d-151">During the preview period, every organization trying out Graph connectors was provided a free fixed quota of up to 2 million items across all connections.</span></span> <span data-ttu-id="c625d-152">Da Graph-Connectors allgemein verfügbar sind, läuft das kostenlose Kontingent am 1. April 2021 für organisationen ab, die Graph-Connectors in der Vorschau verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="c625d-152">With Graph connectors being generally available, the free quota will expire on April 1st, 2021 for those organizations who have been using Graph connectors in preview.</span></span>
><span data-ttu-id="c625d-153">Von Microsoft erstellten Graph-Connectors, die als ["Vorschau"](./connectors-overview.md) gekennzeichnet sind, werden nicht in das insgesamt berechnete Indexkontingent für Ihre Organisation einbezogen.</span><span class="sxs-lookup"><span data-stu-id="c625d-153">Microsoft-built Graph connectors labeled as ["Preview"](./connectors-overview.md) will not be included in the total charged index quota for your organization.</span></span> <span data-ttu-id="c625d-154">Es wird jedoch auf die maximale Anzahl von 10 Verbindungen angezählt, die Sie für Ihre Organisation konfigurieren können, und die maximale Anzahl von 7 Millionen Elementen, die Ihre Organisation über Verbindungen indizieren kann. Jede Verbindung ist auf 700.000 Elemente beschränkt.</span><span class="sxs-lookup"><span data-stu-id="c625d-154">However, it will count towards the max number of 10 connections you can configure for your organization and the max number of 7 million items your organization can index across connections; each connection is limited 700,000 items.</span></span> 

<span data-ttu-id="c625d-155">Die Kontingentauslastungsleiste gibt verschiedene Zustände basierend auf dem Verbrauch von Kontingenten durch Ihre Organisation an:</span><span class="sxs-lookup"><span data-stu-id="c625d-155">The quota utilization bar will indicate various states based on consumption of quota by your organization:</span></span>

<span data-ttu-id="c625d-156">Status</span><span class="sxs-lookup"><span data-stu-id="c625d-156">State</span></span> | <span data-ttu-id="c625d-157">Kontingentauslastungsstufen</span><span class="sxs-lookup"><span data-stu-id="c625d-157">Quota utilization levels</span></span>
--- | --- 
<span data-ttu-id="c625d-158">Standard</span><span class="sxs-lookup"><span data-stu-id="c625d-158">Normal</span></span> | <span data-ttu-id="c625d-159">0-79%</span><span class="sxs-lookup"><span data-stu-id="c625d-159">0-79%</span></span>
<span data-ttu-id="c625d-160">Hoch</span><span class="sxs-lookup"><span data-stu-id="c625d-160">High</span></span> | <span data-ttu-id="c625d-161">80-89%</span><span class="sxs-lookup"><span data-stu-id="c625d-161">80-89%</span></span>
<span data-ttu-id="c625d-162">Kritisch</span><span class="sxs-lookup"><span data-stu-id="c625d-162">Critical</span></span> | <span data-ttu-id="c625d-163">90%-99%</span><span class="sxs-lookup"><span data-stu-id="c625d-163">90%-99%</span></span>
<span data-ttu-id="c625d-164">Vollständig</span><span class="sxs-lookup"><span data-stu-id="c625d-164">Full</span></span> | <span data-ttu-id="c625d-165">100 %</span><span class="sxs-lookup"><span data-stu-id="c625d-165">100%</span></span>

<!-- 
![Quota utilization levels](media/connectors-quota-utilization-levels.png)
-->

<span data-ttu-id="c625d-166">Die Anzahl der indizierten Elemente wird auch bei jeder Verbindung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c625d-166">The number of items indexed will also be displayed with each connection.</span></span> <span data-ttu-id="c625d-167">Die Anzahl der von jeder Verbindung indizierten Elemente trägt zum Gesamtkontingent bei, das für Ihre Organisation verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="c625d-167">The number of items indexed by each connection contributes to the total quota available for your organization.</span></span>

<span data-ttu-id="c625d-168">Wenn das Indexkontingent für Ihre Organisation überschritten wird, werden alle aktiven Verbindungen betroffen sein, und diese Verbindungen werden im **Grenzwertüberschreitungsstatus** betrieben.</span><span class="sxs-lookup"><span data-stu-id="c625d-168">When index quota is exceeded for your organization, all active connections will be impacted, and those connections will operate in **limit exceeded** state.</span></span> <span data-ttu-id="c625d-169">In diesem Zustand werden Ihre aktiven Verbindungen</span><span class="sxs-lookup"><span data-stu-id="c625d-169">In this state, your active connections</span></span>  

* <span data-ttu-id="c625d-170">Neue Elemente können nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c625d-170">Will not be able to add new items.</span></span>

* <span data-ttu-id="c625d-171">Vorhandene Elemente können aktualisiert oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="c625d-171">Will be able to update or delete existing items.</span></span>

<span data-ttu-id="c625d-172">Um dies zu beheben, können Sie eine der folgenden Schritte tun:</span><span class="sxs-lookup"><span data-stu-id="c625d-172">To fix this, you can do any of the following:</span></span>

* <span data-ttu-id="c625d-173">Informationen zum Kauf von Indexkontingenten für Ihre Organisation finden Sie unter [Lizenzierungsanforderungen und Preise](licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c625d-173">Learn how to purchase index quota for your organization at [Licensing requirements and pricing](licensing.md).</span></span>

* <span data-ttu-id="c625d-174">Identifizieren Sie Verbindungen, bei denen zu viel Inhalt aufgenommen wird, und aktualisieren Sie sie, um weniger Elemente zu indizieren, um Platz für Kontingente zu machen.</span><span class="sxs-lookup"><span data-stu-id="c625d-174">Identify connections which have too much content being ingested and update them to index fewer items to make room for quota.</span></span> <span data-ttu-id="c625d-175">Um die Verbindung zu aktualisieren, müssen Sie eine neue Verbindung mit einem neuen Aufnahmefilter löschen und erstellen, der weniger Elemente einf?</span><span class="sxs-lookup"><span data-stu-id="c625d-175">To update the connection, you must delete and create a new connection with a new ingestion filter which brings in fewer items.</span></span>

* <span data-ttu-id="c625d-176">Dauerhaftes Löschen einer oder mehreren Verbindungen</span><span class="sxs-lookup"><span data-stu-id="c625d-176">Permanently delete one or more connections</span></span>