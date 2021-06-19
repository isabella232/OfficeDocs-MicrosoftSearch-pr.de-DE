---
title: Dynamics 365-Verbundsuche (Vorschau)
ms.author: dawholl
author: dawholl
manager: kellis
ms.audience: Admin
ms.topic: article
ms.service: mssearch
localization_priority: Normal
description: Verwalten der Darstellung von Dynamics 365-Inhalten in Suchergebnissen
ms.openlocfilehash: 8818d2e6a412feb167c67f465f485b23e868a12a
ms.sourcegitcommit: be989950a7b63281c2348cfd9e6cc13e79b7c067
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53021840"
---
# <a name="dynamics-365-federation-search-preview"></a><span data-ttu-id="6c4d9-103">Dynamics 365-Verbundsuche (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="6c4d9-103">Dynamics 365 federation search (preview)</span></span>

## <a name="microsoft-search-federation-and-connectors"></a><span data-ttu-id="6c4d9-104">Microsoft Search Partnerverbund und Connectors</span><span class="sxs-lookup"><span data-stu-id="6c4d9-104">Microsoft Search Federation and connectors</span></span>

<span data-ttu-id="6c4d9-105">Um Microsoft Search nützlicher zu machen, führen wir Microsoft Search Partnerverbund ein.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-105">To help make Microsoft Search more useful, we're introducing Microsoft Search Federation.</span></span> <span data-ttu-id="6c4d9-106">Mit der Sammelsuche können Organisationen Daten in diesen Szenarien in Microsoft Search zugänglich machen:</span><span class="sxs-lookup"><span data-stu-id="6c4d9-106">With federated search, organizations can make data in these scenarios accessible in Microsoft Search:</span></span>

* <span data-ttu-id="6c4d9-107">Daten in Systemen, die strengen Complianceanforderungen unterliegen</span><span class="sxs-lookup"><span data-stu-id="6c4d9-107">Data in systems that are subject to strict compliance requirements</span></span>
* <span data-ttu-id="6c4d9-108">Daten, die keine Systemgrenzen überschreiten können</span><span class="sxs-lookup"><span data-stu-id="6c4d9-108">Data that can't leave system boundaries</span></span>
* <span data-ttu-id="6c4d9-109">Vertrauliche Daten, die lokal gespeichert werden und die Von Ihrer Organisation nicht in der Cloud indiziert werden sollen</span><span class="sxs-lookup"><span data-stu-id="6c4d9-109">Sensitive data stored on-prem that your organization doesn’t want indexed on the cloud</span></span>

<span data-ttu-id="6c4d9-110">Daten, auf die über eine Sammelsuche zugegriffen wird, werden nicht in Microsoft Search indiziert.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-110">Data accessed through a federated search connection isn't indexed in Microsoft Search.</span></span> <span data-ttu-id="6c4d9-111">Darüber hinaus ist es mithilfe integrierter Connectors von Microsoft einfach, Sammelsuchverbindungen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-111">Also, using built-in connectors from Microsoft, it's easy to set up federated search connections.</span></span> <span data-ttu-id="6c4d9-112">Unser Dynamics 365-Connector befindet sich derzeit in der Vorschau.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-112">Our Dynamics 365 connector is currently in preview.</span></span> <span data-ttu-id="6c4d9-113">Wenn Sie an der Vorschau teilnehmen möchten, teilen Sie uns dies unter [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview)mit.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-113">If you're interested in joining the preview, let us know at [aka.ms/D365FederationSearchPreview](https://aka.ms/D365FederationSearchPreview).</span></span>

## <a name="dynamics-365-federation-connector"></a><span data-ttu-id="6c4d9-114">Dynamics 365-Verbundconnector</span><span class="sxs-lookup"><span data-stu-id="6c4d9-114">Dynamics 365 federation connector</span></span>

<span data-ttu-id="6c4d9-115">Microsoft Dynamics 365 ist eine Reihe intelligenter Geschäftsanwendungen, die für die Planung von Unternehmensressourcen und die Verwaltung von Kundenbeziehungen entwickelt wurden.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-115">Microsoft Dynamics 365 is a line of intelligent business applications designed for enterprise resource planning and customer relationship management.</span></span> <span data-ttu-id="6c4d9-116">Mit dem Dynamics 365-Partnerverbund bietet Microsoft Search eine nahtlose Suchumgebung, sodass Benutzer auf einfache Weise die relevantesten Kunden- und Geschäftsdaten finden können, die in Dynamics 365 gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-116">With Dynamics 365 federation, Microsoft Search provides a seamless search experience, enabling users to easily find the most relevant customer and business data stored in Dynamics 365.</span></span> <span data-ttu-id="6c4d9-117">Der Dynamics 365-Verbundconnector bietet einige wichtige Vorteile:</span><span class="sxs-lookup"><span data-stu-id="6c4d9-117">The Dynamics 365 federation connector provides some key benefits:</span></span>

* <span data-ttu-id="6c4d9-118">**Einfache Verwaltung:** Optimierter Prozess zum Konfigurieren und Verwalten der Suchverbindung mit einer Dynamics 365-Instanz.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-118">**Easy to administer:** Streamlined process to configure and maintain the search connection to a Dynamics 365 instance.</span></span>
* <span data-ttu-id="6c4d9-119">**Einfach zu verwenden:** Benutzer können wichtige Informationen, die in Dynamics 365 gespeichert sind, ganz einfach und schnell finden, einschließlich Konten, Kontakten, offenen Möglichkeiten und mehr.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-119">**Easy to use:** Users can easily and quickly find key information stored in Dynamics 365, including accounts, contacts, open opportunities, and more.</span></span>
* <span data-ttu-id="6c4d9-120">**Umfangreichere Inhalte:** Um dynamics 365-Suchergebnisse nützlicher zu machen, enthalten sie wichtige Informationen wie Leads, Kontakte und Kontodetails.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-120">**Richer content:** To make Dynamics 365 search results more useful, they include key information like leads, contacts, and account details.</span></span>
* <span data-ttu-id="6c4d9-121">**Integrierter Datenschutz:** Dynamics 365-Ergebnisse werden nur für Benutzer angezeigt, die Zugriff auf die verbundene Instanz haben.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-121">**Built-in data protection:** Dynamics 365 results will only appear for users that have access to the connected instance.</span></span>
* <span data-ttu-id="6c4d9-122">**Einheitliche Suchumgebung:** Um eine einheitliche Benutzererfahrung zu gewährleisten, sind die Dynamics 365-Ergebnisse über alle Sucheinstiegspunkte hinweg konsistent.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-122">**Unified search experience:** To maintain a cohesive experience, Dynamics 365 results are consistent across all search entry points.</span></span> <span data-ttu-id="6c4d9-123">Überall dort, wo Sie suchen, erhalten Sie dieselben Ergebnisse mit demselben Aussehen und Verhalten.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-123">Wherever you search, you'll get the same results with the same look and feel.</span></span>

## <a name="what-users-experience"></a><span data-ttu-id="6c4d9-124">Benutzerfreundlichkeit</span><span class="sxs-lookup"><span data-stu-id="6c4d9-124">What users experience</span></span>

<span data-ttu-id="6c4d9-125">Dynamics 365-Antworten werden in suchergebnissen in allen Microsoft Search Canvases angezeigt, einschließlich SharePoint Online, Bing und Office.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-125">Dynamics 365 answers appear in search results across all Microsoft Search canvases, including SharePoint Online, Bing, and Office.</span></span>

:::image type="content" alt-text="Screenshot der Dynamics 365-Antworten auf SharePoint, Bing und Office" source="media/dynamics365/dynamics365-answer.png" lightbox="media/dynamics365/dynamics365-answer.png":::

<span data-ttu-id="6c4d9-127">Aus der Antwort ist es einfach, weitere Dynamics 365-Suchergebnisse mithilfe des Links **"Weitere Dynamics 365-Ergebnisse"** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-127">From the answer, it's easy to see more Dynamics 365 search results by using the **More Dynamics 365 results** link.</span></span> <span data-ttu-id="6c4d9-128">Sie führt Benutzer zu einer dedizierten Dynamics 365-Ergebnisseite mit weiteren Ergebnissen, die für ihre Abfrage relevant sind.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-128">It takes users to a dedicated Dynamics 365 results page with more results relevant to their query.</span></span>

:::image type="content" alt-text="Screenshot der vertikalen Dynamics 365-Branche und Ergebnisse zu SharePoint, Bing und Office" source="media/dynamics365/dynamics365-vertical.png" lightbox="media/dynamics365/dynamics365-vertical.png":::

<span data-ttu-id="6c4d9-130">Wenn Sie auf ein beliebiges Ergebnis klicken oder tippen, wird Dynamics 365 geöffnet und die detaillierten Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-130">Clicking or tapping any result opens Dynamics 365 and shows the detailed information.</span></span>

:::image type="content" alt-text="Screenshot der Detailseite in Dynamics 365" source="media/dynamics365/dynamics365-detail-page.png" lightbox="media/dynamics365/dynamics365-detail-page.png":::

<span data-ttu-id="6c4d9-132">Unabhängig davon, wo Ihre Benutzer mit der Suche beginnen, ist ihre Oberfläche konsistent und ermöglicht es ihnen, schnell die relevantesten Dynamics 365-Ergebnisse zu finden.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-132">No matter where your users start their search their experience will be consistent and enable them to quickly find the most relevant Dynamics 365 results.</span></span> <span data-ttu-id="6c4d9-133">Sehen Sie sich unser [Microsoft Build 2021-Video](https://youtu.be/TH9QUkQoEJM) für eine Demonstration an.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-133">Check out our [Microsoft Build 2021 video](https://youtu.be/TH9QUkQoEJM) for a demonstration.</span></span>

## <a name="supported-query-patterns"></a><span data-ttu-id="6c4d9-134">Unterstützte Abfragemuster</span><span class="sxs-lookup"><span data-stu-id="6c4d9-134">Supported query patterns</span></span>

<span data-ttu-id="6c4d9-135">Abfragen natürlicher Sprache und Produktnamen werden unterstützt, wenn sie Microsoft Search verwenden, um Dynamics 365-Ergebnisse zu finden.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-135">Both natural language and product name queries are supported when using Microsoft Search to find Dynamics 365 results.</span></span> <span data-ttu-id="6c4d9-136">Außerdem wird bei Dynamics 365-Abfragen die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-136">Also, Dynamics 365 queries aren't case sensitive.</span></span> <span data-ttu-id="6c4d9-137">Verwenden Sie natürliche Sprachmuster, um Kontakt-, Konto- und Geschäftsmöglichkeiten nach Kundennamen oder Standort und anderen häufig verwendeten Abfragen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-137">Use natural language patterns to find contact, account, and opportunities--by customer name or location--and other frequently used queries.</span></span> <span data-ttu-id="6c4d9-138">Hier ein paar Beispiele:</span><span class="sxs-lookup"><span data-stu-id="6c4d9-138">Here are a few examples:</span></span>

* <span data-ttu-id="6c4d9-139">Wer ist der Kontakt für Contoso.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-139">Who is the contact for Contoso</span></span>
* <span data-ttu-id="6c4d9-140">Offene Möglichkeiten für Contoso</span><span class="sxs-lookup"><span data-stu-id="6c4d9-140">Open opportunities for Contoso</span></span>
* <span data-ttu-id="6c4d9-141">Was sind offene Möglichkeiten in Seattle?</span><span class="sxs-lookup"><span data-stu-id="6c4d9-141">What are open opportunities in Seattle</span></span>
* <span data-ttu-id="6c4d9-142">Was sind die Konten in Seattle?</span><span class="sxs-lookup"><span data-stu-id="6c4d9-142">What are the accounts in Seattle</span></span>
* <span data-ttu-id="6c4d9-143">Was sind die Kontakte in Seattle?</span><span class="sxs-lookup"><span data-stu-id="6c4d9-143">What are the contacts in Seattle</span></span>
* <span data-ttu-id="6c4d9-144">Was sind meine Leads, die in diesem Monat geschlossen werden?</span><span class="sxs-lookup"><span data-stu-id="6c4d9-144">What are my leads closing this month</span></span>
* <span data-ttu-id="6c4d9-145">Telefonanruf mit hoher Priorität</span><span class="sxs-lookup"><span data-stu-id="6c4d9-145">High priority phone call</span></span>
* <span data-ttu-id="6c4d9-146">Kontakt fehlende E-Mails</span><span class="sxs-lookup"><span data-stu-id="6c4d9-146">Contact missing emails</span></span>

<span data-ttu-id="6c4d9-147">Produktnamenmuster unterstützen eine Reihe von Dynamics 365-Anwendungen und lösen Dynamics 365-Ergebnisse unabhängig davon aus, wo sie in einer Abfrage angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="6c4d9-147">Product name patterns support a range of Dynamics 365 applications and will trigger Dynamics 365 results regardless of where they appear in a query:</span></span>

* <span data-ttu-id="6c4d9-148">D365</span><span class="sxs-lookup"><span data-stu-id="6c4d9-148">D365</span></span>
* <span data-ttu-id="6c4d9-149">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="6c4d9-149">Dynamics 365</span></span>
* <span data-ttu-id="6c4d9-150">Dynamics365</span><span class="sxs-lookup"><span data-stu-id="6c4d9-150">Dynamics365</span></span>
* <span data-ttu-id="6c4d9-151">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="6c4d9-151">Dynamics CRM</span></span>
* <span data-ttu-id="6c4d9-152">Dynamics Sales</span><span class="sxs-lookup"><span data-stu-id="6c4d9-152">Dynamics Sales</span></span>
* <span data-ttu-id="6c4d9-153">Dynamics Customer Service</span><span class="sxs-lookup"><span data-stu-id="6c4d9-153">Dynamics Customer Service</span></span>
* <span data-ttu-id="6c4d9-154">Dynamics Service</span><span class="sxs-lookup"><span data-stu-id="6c4d9-154">Dynamics Service</span></span>
* <span data-ttu-id="6c4d9-155">Dynamics Field Service</span><span class="sxs-lookup"><span data-stu-id="6c4d9-155">Dynamics Field Service</span></span>

## <a name="configure-the-dynamics-365-connector"></a><span data-ttu-id="6c4d9-156">Konfigurieren des Dynamics 365-Connectors</span><span class="sxs-lookup"><span data-stu-id="6c4d9-156">Configure the Dynamics 365 connector</span></span>

<span data-ttu-id="6c4d9-157">Mit dieser einfachen Konfiguration können Sie die Dynamics 365-Verbundsuche für Personen in Ihrer Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-157">With this simple configuration, you can enable the Dynamics 365 federation search experience for people in your organization.</span></span>

1. <span data-ttu-id="6c4d9-158">Wechseln [Sie](https://admin.microsoft.com)im Microsoft 365 Admin Center zu [Datenquellen.](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors)</span><span class="sxs-lookup"><span data-stu-id="6c4d9-158">In the [Microsoft 365 admin center](https://admin.microsoft.com), go to [Data sources](https://admin.microsoft.com/Adminportal/Home#/MicrosoftSearch/connectors).</span></span>

2. <span data-ttu-id="6c4d9-159">Wählen Sie im Abschnitt "Microsoft-Apps und -Dienste" unter Microsoft Dynamics 365 die Option **"Verwalten"** aus, um den Bereich Microsoft Dynamics 365 zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-159">In the Microsoft apps and services section, under Microsoft Dynamics 365, select **Manage** to open the Microsoft Dynamics 365 panel.</span></span>

3. <span data-ttu-id="6c4d9-160">Aktivieren Sie den Connector für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-160">Enable the connector for your organization.</span></span>

4. <span data-ttu-id="6c4d9-161">Wählen Sie in der **Liste "Endpunkte"** Ihre Dynamics 365-Umgebung aus.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-161">In the **Endpoints** list, select your Dynamics 365 environment.</span></span>

5. <span data-ttu-id="6c4d9-162">Geben Sie in der **Verbindungs-ID** eine eindeutige ID für diese Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-162">In the **Connection ID**, enter a unique ID for this connection.</span></span>

6. <span data-ttu-id="6c4d9-163">Überprüfen Sie das Kontrollkästchen "Zustimmung", und aktivieren Sie es.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-163">Review and select the consent check box.</span></span>

7. <span data-ttu-id="6c4d9-164">Wählen Sie **"Speichern"** aus, um die Verbindungseinrichtung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-164">Select **Save** to finish the connection setup.</span></span>

:::image type="content" alt-text="Screenshot des Dynamics 365-Einrichtungsbereichs im Microsoft 365 Admin Center" source="media/dynamics365/dynamic365-connection-setup.png" lightbox="media/dynamics365/dynamic365-connection-setup.png":::

<span data-ttu-id="6c4d9-166">Wenn die Einrichtung abgeschlossen ist, werden Dynamics 365-Antworten und -Vertikalen nur für Benutzer mit einer gültigen Dynamics 365-Lizenz und Zugriff auf die verbundene Dynamics 365-Umgebung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-166">When the setup is complete, Dynamics 365 answers and vertical will only appear for users with a valid Dynamics 365 license and access to the connected Dynamics 365 environment.</span></span> <span data-ttu-id="6c4d9-167">Sie können jederzeit zu diesen Einstellungen zurückkehren und die Verbindungsendpunktumgebung ändern oder die Verbindung deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6c4d9-167">At any time, you can return to these settings and change the connection endpoint environment or deactivate the connection.</span></span>
