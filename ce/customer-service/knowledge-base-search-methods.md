---
title: Knowledge base search options in Dynamics 365 Customer Service| MicrosoftDocs
description: Know how the knowledge base search methods work in Microsoft Dynamics 365 Customer Service.
ms.date: 03/14/2022
ms.topic: article
author: Soumyasd27
ms.author: sdas
manager: shujoshi
search.audienceType: 
  - admin
  - customizer
  - enduser
search.app: 
  - D365CE
  - D365CS
ms.custom: 
  - dyn365-customerservice
---

# Understand knowledge base search

Setting up a comprehensive knowledge base is the key to increased customer satisfaction and improved productivity. A knowledge base is created to help customer service reps with solutions to the most common issues, so they can assist customers quickly.

Use this topic to understand how various search methods work in a knowledge base, and how a customer service rep can view accurate search results based on the client, application, or keyword they use to search the knowledge base.

See the following section to learn the types of search mechanisms available.

## Search options

- **Full-text search**: Lets you run full-text queries against character-based data in SQL Server tables. 
 
   [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Full-text search](/sql/relational-databases/search/full-text-search)

- **Relevance search**:  Lets you search across multiple predefined entities and returns results sorted by relevance.  

   [!INCLUDE[proc_more_information](../includes/proc-more-information.md)] [Relevance search](/powerapps/user/relevance-search)
   <br> 

   See [Configure Relevance search](/power-platform/admin/configure-relevance-search-organization) to learn how to configure Relevance search to improve search results and performance.

   To better understand the various searches used in Dynamics 365 Customer Service and how they can be compared, see [Compare Dynamics 365 apps searches](/power-platform/admin/configure-relevance-search-organization).

## Search the knowledge base

You can search the knowledge base from the following areas in the Customer Service Hub app:

- **Knowledge base search control**: In the app, select a case by navigating to **Service** > **Cases**. In the **Related** section (also known as Reference panel), select **Knowledge Base Search** and search for knowledge articles using keywords in the search box. 
  
  ![Knowledge base search control.](media/kb-search-control.png)

   To explore more options in the knowledge base search given in the Related section, see [Search for knowledge articles](search-knowledge-articles-csh.md).

   > [!NOTE]
   > Knowledge base search control is available out of the box in a case entity. The previous procedure describes how the control can be accessed in the Customer Service Hub app.


- **Global search**: Select the **Search** icon on the navigation bar to do a global search for knowledge base articles. Global search lets you use **Categorized search** or **Relevance search**.

- **Quick find in Grids**: In the app, go to **Service** > **Knowledge Articles**, and select the search box to search the knowledge base using keywords. 

   ![Quick find search.](media/quick-find-search.png)


With each of the previous search areas, the search results might vary based on the underlying search option used:

**Version**: December 2016 Update for Dynamics 365 Customer Service and December 2016 Service Pack for Customer Engagement (on-premises) platform 
 - For KB search control and Quick find in Grids search areas, search mechanism used is Full-text search.
 - For Global search, search mechanism used is Categorized search.

**Version**: Dynamics 365 Customer Service apps version 9.0
  - For KB search control, search mechanism used is Relevance search or Full-text search (based on what you configure).
  - For Quick find in Grids, search mechanism used is Full-text search.
  - For Global search, search mechanism used is Relevance search or Categorized search (based on what you configure).

## Search the knowledge base on portals

You can use the following search options to search the knowledge base on the portal.

- **Lucene.Net search**: Lucene.Net searches within multiple tables and fields at once. More information: [Search](/powerapps/maker/portals/configure/search)
- **Dataverse search** **(preview)**: 

  > [!IMPORTANT]
  > This section is prerelease documentation and is subject to change.

Lets you search across multiple tables sorted by relevance. More information: [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro) To configure dataverse search on portals, see [Configure Dataverse search in portals (preview)](/powerapps/maker/portals/configure/dataverse-search).

You can further refine your search through Progressive search, which lets you search without any mismatch between the results count and the number of records returned in the search results. More information: [Configure progressive search counts](/powerapps/maker/portals/configure/progressive-search).

### Enable content access levels for knowledge articles from a portal

You can set the content access levels for users to control access to knowledge articles on a portal. More information: [Manage knowledge articles by using content access levels](/powerapps/maker/portals/customer-engagement-apps/manage-knowledge-articles-content-levels) 

For content access level to work with Relevance search, you must perform the following steps on the Dynamics 365 Portals app:
  1. In the Portal Management sitemap, in the **Website** area, select **Site Settings**.
  1. Select **New**.
  1. Enter **Name** as **Knowledge Management/ContentAccessLevel/Enabled**.
  1. Select your website record.
  1. Set the Value to **true**. By default, the value of the site setting is set to **false**.
  6. Select **Save**.
 
When performing a search on the portal, you might encounter an error while opening an article and also see the error message, "Update your origins allow list if any iframe in the article doesn't work or displays error." This could be because the link types used in the article aren't a part of the origins allow list. You must contact your administrator to update your origins allow list. More information: [Configure the origins allow list for knowledge articles](configure-knowledge-article-origin-allow-list.md)


### See also

[Add the Knowledge Base Search control to forms](add-knowledge-base-search-control-forms.md)

[Create and manage knowledge articles](customer-service-hub-user-guide-knowledge-article.md)

[Manage knowledge articles by using content access levels](/powerapps/maker/portals/customer-engagement-apps/manage-knowledge-articles-content-levels)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
