---

copyright:
  years: 2015, 2017
lastupdated: "2017-10-16"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}
{:download: .download}

# Getting started with the tooling

In this short tutorial, we introduce the {{site.data.keyword.discoveryshort}} tooling and go through the process of creating a private data collection and searching it.
{: shortdesc}

## Before you begin
{: #before-you-begin}

You'll need a service instance to start.

<!-- Remove the text marked `download` after there's no g-s tab in the catalog dashboard -->

You created your service instance. Click **Manage**, then **Launch Tool**. Go to [Step 2](/docs/services/discovery/getting-started-tooling.html#create-a-collection).
{: download tip}

If you created a project with the {{site.data.keyword.discoveryshort}} service, you're all set with these prerequisites. Go to [Step 1](/docs/services/discovery/getting-started-tooling.html#launch-the-tooling).

1.  Go to the {{site.data.keyword.watson}} Developer Console [Services ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.{DomainName}/developer/watson/services){: new_window} page.
1.  Select {{site.data.keyword.discoveryshort}}, click **Add Services**, and either sign up for a free {{site.data.keyword.Bluemix_notm}} account or log in.
1.  Type `discovery-tutorial` as the project name and click **Create Project**.

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

If you use {{site.data.keyword.Bluemix_dedicated_notm}}, create your service instance from the [{{site.data.keyword.discoveryshort}} ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.{DomainName}/catalog/services/discovery/){: new_window} page in the Catalog.

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## Step 1: Launch the tooling
{: #launch-the-tooling}

After you create a project that includes the {{site.data.keyword.discoveryshort}} service, you'll land on the project details page. Launch the {{site.data.keyword.discoveryshort}} tooling from here.

Click **Launch Tool** for {{site.data.keyword.discoveryshort}} under **Services**.

<!-- To do: Add screenshot for developer console -->

If you're prompted to log into the tooling, provide your {{site.data.keyword.Bluemix_notm}} credentials.

If you're not at a project details page for the {{site.data.keyword.discoveryshort}} service, go to the {{site.data.keyword.watson}} Developer Console [Projects ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://console.{DomainName}/developer/watson/projects) page and select the project.
{: tip}

<!-- Remove this text after dedicated instances have the Developer Console: begin -->

{{site.data.keyword.Bluemix_dedicated_notm}}: Select your service instance from the Dashboard to launch the tooling.

<!-- Remove this text after dedicated instances have the Developer Console: end -->

## Step 2: Create a collection
{: #create-a-collection}

Your first step in the {{site.data.keyword.discoveryshort}} tooling is to create a data collection.

A collection is a set of your documents. *Why would I want more than one collection?* There are a few reasons:

- You might want multiple collections in order to separate results for different audiences.
- The data might be so different that it doesn't make sense for it all to be queried at the same time.

The public, pre-enriched {{site.data.keyword.discoverynewsshort}} data collection is also available for your use. It is ready-to-query and you can begin to create queries on it immediately. You cannot adjust its configuration or add documents to {{site.data.keyword.discoverynewsshort}}.

1.  Click ![Cog](images/icon_settings.png)<!-- {width="20" height="20" style="padding-left:5px;padding-right:5px;"} --> and choose **Create environment**.
1.  When your environment is ready, the **Name your new collection** dialog appears. Name your collection and choose **Default Configuration** from **Select a configuration to apply** (you can change the configuration later).

## Step 3: Create a custom configuration
{: create-custom-configuration}

After your collection is created, you could immediately start uploading content using the upload area, but we want to create and test a custom configuration.

1.  Click **Switch** next to the collection name and choose **Create a new configuration**. Name your configuration and click **Create**.
1.  After you create your configuration, you can customize it:
    1.  Download the <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/discovery/test-doc1.html" download>test-doc1.html <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a> sample document.
    1.  Use the **Upload Sample Documents** panel to upload the sample document. After it uploads, you can click the document name link to view the transformation.
1.  Now it's time to adjust the configuration. For this task, you change the enrichments that are applied to each document:
    1.  Click on the **Enrich** section of the configuration. Look at the generated JSON to the right of the screen. Scroll down to the *enriched_text* section and notice that it contains many *concepts*.
    1.  Next, remove the text enrichment named *concepts* by clicking the **X** next to it and then click **Apply & Save**.
    1.  Finally, look at the JSON again. Notice how the output has changed and no longer includes *concepts*.

## Step 4: Upload your documents
{: #upload-your-documents}

When you're happy with the custom conversion of your sample document it's time to ingest the real content into your collection.

1. Download these three sample documents: <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/discovery/test-doc2.html" download>test-doc2.html <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>, <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/discovery/test-doc3.html" download>test-doc3.html <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>, <a target="_blank" href="https://watson-developer-cloud.github.io/doc-tutorial-downloads/discovery/test-doc4.html" download>test-doc4.html <img src="../../icons/launch-glyph.svg" alt="External link icon" title="External link icon" class="style-scope doc-content"></a>.
1.  Click ![File icon](images/icon_yourData.png)<!-- {width="20" height="20" style="padding-left:5px;padding-right:5px;"} --> and select your collection.
1.  Make sure the custom configuration you created is listed under **Configuration**. If it isn't, click **Switch** next to the configuration name and select it.
1.  Click the **Upload documents** button and start uploading the four sample documents: test-doc1.html, test-doc2.html, test-doc3.html, test-doc4.html.
1.  Wait for the documents to upload. The status of your documents display in the **Overview** section.

## Step 5: Build a query
{: #build-a-query}

1.  Click ![Query icon](images/icon_queryBuilder.png)<!-- {width="20" height="20" style="padding-left:5px;padding-right:5px;"} --> to open the query page. Select your collection and click **Get started**.
1.  Build your query under **Search for Documents** in the **Build queries** screen:
    - To search for results with entities named "IBM":
        1.  Click **Field** and select `enriched_text.entities.text`. Select `contains` for **Operator** and `IBM` for **Value**. The query `enriched_text.entities.text:IBM` is displayed in **Visual Query Builder**.
        1.  Click **Run Query**. The query returns 4 results.
    - To search for results with entities named "Watson":
        1.  Click **Field** and select `enriched_text.entities.text`. Select `contains` for  **Operator** and `watson` for **Value**. The query `enriched_text.entities.text:watson` is displayed in **Visual Query Builder**.
        1.  Click **Run Query**. The query returns 2 results.
    - To search for results with both entities named "Watson" and "Slack":
        1.  Click **Field** and select `enriched_text.entities.text`. Select `contains` for **Operator** and `watson` for **Value**. Click **Add rule**, then repeat your selections, but choose the **Value** of `Slack`. The query `enriched_text.entities.text:watson,enriched_text.entities.text:Slack` is displayed in **Visual Query Builder**.
        1.  Click **Run Query**. The query returns 1 result.

    Click **Edit in query language** to build queries using the {{site.data.keyword.discoveryshort}} Query Language. To learn more about the {{site.data.keyword.discoveryshort}} Query Language, see [Query reference](/docs/services/discovery/query-reference.html) and [Query concepts](/docs/services/discovery/using.html).
1.  The results of your query are displayed in the **Results** section:
    - The **Summary** tab provides an overview of the query results,
    - The **JSON** tab displays the full JSON results.

    For the queries listed, the **Summary**  displays the document passages (in order of relevance) first, followed by the names of the documents found, then the results by enrichment. **Passages** are short, relevant excerpts extracted from the full documents returned by your query.

    The **Query URL** link provided under both the **JSON** and **Summary** tabs is ready-to-use in your application.

    You can also click **Use natural language** and write a natural language query, such as "IBM Watson partnerships". To learn more about natural language queries, see [Natural language query](/docs/services/discovery/query-parameters.html#nlq).

    Watson can be trained to improve the results of natural language queries, see [Improving result relevance with the tooling](/docs/services/discovery/train-tooling.html).

    Additional resources:
    - To learn more about the data schema of your documents, click the **View Data Schema** icon or click on the **JSON** tab. See [The Discovery data schema](/docs/services/discovery/using.html#discovery-schema) for details.
    - If editing in the {{site.data.keyword.discoveryshort}} Query Language, click on the **?** icons next to any of the **Enter query here** fields for more examples.

## Next steps
{: #next-steps}

Now you have a functioning and populated {{site.data.keyword.discoveryshort}} service instance. You can now begin customizing your collection by adding more documents and enrichments and customizing conversion settings.
