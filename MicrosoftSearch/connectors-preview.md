---
title: Vorschau der Connectors
ms.author: monaray
author: monaray97
manager: shohara
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
search.appverid:
- BFB160
- MET150
- MOE150
description: Erfahren Sie mehr über die Microsoft Graph Connectors Preview für Microsoft Search.
ms.openlocfilehash: 81d169074a316b6ab07f47156e0f057e50c12e3e
ms.sourcegitcommit: 988c37610e71f9784b486660400aecaa7bed40b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47422892"
---
# <a name="microsoft-graph-connectors-preview"></a><span data-ttu-id="33c4b-103">Vorschau der Microsoft Graph-Konnektoren</span><span class="sxs-lookup"><span data-stu-id="33c4b-103">Microsoft Graph connectors preview</span></span>

<span data-ttu-id="33c4b-104">Microsoft Graph-Connectors und Microsoft Search-APIs (Abfrage und Index) befinden sich zurzeit im Vorschaustatus.</span><span class="sxs-lookup"><span data-stu-id="33c4b-104">Microsoft Graph connectors and Microsoft Search APIs (query and index) are currently in preview status.</span></span> <span data-ttu-id="33c4b-105">Um Zugriff auf Connectors-Funktionen zu erhalten, müssen Sie die Option "Targeted Release" in Ihrem Mandanten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="33c4b-105">To gain access to connectors functionality, you must turn on the Targeted release option in your tenant.</span></span> <span data-ttu-id="33c4b-106">Dies ist eine frühe Vorschau, und es gibt keine Garantie auf Service Level.</span><span class="sxs-lookup"><span data-stu-id="33c4b-106">This is an early preview, and there's no service level guarantee.</span></span> <span data-ttu-id="33c4b-107">Wir ermutigen Kunden, konnektorfunktionen zu testen und Feedback zu geben.</span><span class="sxs-lookup"><span data-stu-id="33c4b-107">We encourage customers to try connectors functionality and provide feedback.</span></span> <span data-ttu-id="33c4b-108">Es wird nicht empfohlen, Connectors für Produktionszwecke während des Vorschauzeitraums zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="33c4b-108">We don’t recommend using connectors for production purposes during the preview period.</span></span>

## <a name="set-up-targeted-release"></a><span data-ttu-id="33c4b-109">Einrichten der gezielten Version</span><span class="sxs-lookup"><span data-stu-id="33c4b-109">Set up Targeted release</span></span>

<span data-ttu-id="33c4b-110">Wenn Sie Connectors testen möchten, müssen Sie die Option **Targeted Release** für alle Benutzer in Ihrer Organisation festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="33c4b-110">To try connectors, you must have the **Targeted release** option set for all users in your organization.</span></span> <span data-ttu-id="33c4b-111">Weitere Informationen zur Option "Targeted Release" und dazu, wie Sie Sie festlegen, finden Sie unter [Einrichten der Standard-oder Targeted Release-Optionen in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="33c4b-111">To learn more about the Targeted release option and how to set it, see [Set up the Standard or Targeted release options in Office 365](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide).</span></span>

## <a name="choose-a-preview-environment"></a><span data-ttu-id="33c4b-112">Auswählen einer vorschauumgebung</span><span class="sxs-lookup"><span data-stu-id="33c4b-112">Choose a preview environment</span></span>

<span data-ttu-id="33c4b-113">Um Konnektoren, Indizierungs-APIs und Such-APIs zu testen, empfehlen wir diese beiden Methoden:</span><span class="sxs-lookup"><span data-stu-id="33c4b-113">To try connectors, indexing APIs, and search APIs, we recommend these two methods:</span></span>

1. <span data-ttu-id="33c4b-114">**Test Mandant**.</span><span class="sxs-lookup"><span data-stu-id="33c4b-114">**Test tenant**.</span></span>  <span data-ttu-id="33c4b-115">Wir empfehlen Ihnen, einen Testmandanten zu verwenden, um die Vorschau der Microsoft Graph-Konnektoren auszuprobieren.</span><span class="sxs-lookup"><span data-stu-id="33c4b-115">We encourage you to use a test tenant to try the Microsoft Graph connectors preview.</span></span>

2. <span data-ttu-id="33c4b-116">**Testen der Websitesammlung**.</span><span class="sxs-lookup"><span data-stu-id="33c4b-116">**Test site collection**.</span></span> <span data-ttu-id="33c4b-117">Wenn Sie keinen Testmandanten haben, können Sie eine TestWebsite Sammlung zum Ausprobieren von connectorfunktionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="33c4b-117">If you don't have a test tenant, you can create a test site collection to try out connectors functionality.</span></span> <span data-ttu-id="33c4b-118">Wenn Sie Ergebnisse aus Konnektoren anzeigen möchten, ohne dass sich dies auf die Suchseiten in Ihrer Organisation auswirkt, passen Sie die Suchumgebung nur für diese Websitesammlung an.</span><span class="sxs-lookup"><span data-stu-id="33c4b-118">To show results from connectors without impacting the search pages anywhere else in your organization, customize the search experience of only that site collection.</span></span>

## <a name="preview-limitations"></a><span data-ttu-id="33c4b-119">Vorschau Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="33c4b-119">Preview limitations</span></span>

<span data-ttu-id="33c4b-120">Die Vorschauversion weist die folgenden Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="33c4b-120">The preview release has the following limitations:</span></span>

* <span data-ttu-id="33c4b-121">Der Durchsatz für die Einnahme wird mit etwa vier Elementen pro Sekunde gedrosselt.</span><span class="sxs-lookup"><span data-stu-id="33c4b-121">Ingestion throughput is throttled at about four items per second.</span></span>

* <span data-ttu-id="33c4b-122">Es gibt keine Unterstützung für Schemaaktualisierungen.</span><span class="sxs-lookup"><span data-stu-id="33c4b-122">There's no support for schema updates.</span></span> <span data-ttu-id="33c4b-123">Nachdem Sie eine Verbindungseinrichtung erstellt haben, können Sie das Schema nicht aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="33c4b-123">After you create a connection setup, there's no way to update the schema.</span></span> <span data-ttu-id="33c4b-124">Sie können die Verbindung nur löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="33c4b-124">You can only delete and re-create the connection.</span></span>

* <span data-ttu-id="33c4b-125">Indizierte Inhalte werden nur auf der Suchergebnisseite unter einer benutzerdefinierten vertikalen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33c4b-125">Indexed content only shows up in the search results page under a custom vertical.</span></span> <span data-ttu-id="33c4b-126">Diese Einschränkung gilt für Inhalte mit benutzerdefinierten Typen.</span><span class="sxs-lookup"><span data-stu-id="33c4b-126">This restriction applies to content with custom types.</span></span>

* <span data-ttu-id="33c4b-127">Jede Verbindung, die Sie während des Vorschauzeitraums eingerichtet haben, muss möglicherweise gelöscht und neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="33c4b-127">Any connection you set up during the preview period might need to be deleted and re-created.</span></span> <span data-ttu-id="33c4b-128">Diese Verbindungen funktionieren nicht mehr, wenn Sie mit Änderungen, die zur Verbesserung des Produkts vorgenommen wurden, nicht kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="33c4b-128">Those connections won't work anymore if they're incompatible with changes made to improve the product.</span></span>

* <span data-ttu-id="33c4b-129">Es gibt einen Grenzwert für Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="33c4b-129">There's a connections limit.</span></span> <span data-ttu-id="33c4b-130">Jeder Mandant kann bis zu 10 Verbindungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="33c4b-130">Each tenant can create up to 10 connections.</span></span>

* <span data-ttu-id="33c4b-131">Größe des Quell-Repositorys.</span><span class="sxs-lookup"><span data-stu-id="33c4b-131">Source repository size.</span></span> <span data-ttu-id="33c4b-132">Es wird empfohlen, Connectors mit einem Quell-Repository mit etwa 200.000 Elementen in der Vorschau anzuzeigen, da dies unsere getestete Skalierungsgrenze für die Suche darstellt.</span><span class="sxs-lookup"><span data-stu-id="33c4b-132">We recommend that you preview connectors with a source repository of about 200,000 items as this is our tested search scale limit.</span></span> <span data-ttu-id="33c4b-133">Wir arbeiten daran, die Leistung der Suche zu verbessern, und wir erwarten, dass in naher Zukunft größere Repository-Größen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="33c4b-133">We are working on improving the performance of search, and we expect to support for larger repository sizes in the near future.</span></span>

* <span data-ttu-id="33c4b-134">Die Bearbeitungsunterstützung für die Verbindung ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="33c4b-134">Edit support for connection is not available.</span></span> <span data-ttu-id="33c4b-135">Nachdem die Verbindung erstellt wurde, können Sie Sie nicht bearbeiten oder ändern.</span><span class="sxs-lookup"><span data-stu-id="33c4b-135">Once the connection has been created, you cannot edit or change it.</span></span> <span data-ttu-id="33c4b-136">Wenn Sie Details ändern müssen, müssen Sie die Verbindung löschen und neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="33c4b-136">If you need to change any details, you must delete and recreate the connection.</span></span>

* <span data-ttu-id="33c4b-137">Connector-Inhalte können nur nach benutzerdefinierten vertikalen durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="33c4b-137">Connector content can only be searched on custom verticals.</span></span>

* <span data-ttu-id="33c4b-138">Connector-Inhalt aus nur einer Verbindung kann in jeder benutzerdefinierten vertikalen angezeigt werden und erfordert die Erstellung von Ergebnistypen.</span><span class="sxs-lookup"><span data-stu-id="33c4b-138">Connector content from only one connection can be displayed in each custom vertical and requires result type creation.</span></span>
