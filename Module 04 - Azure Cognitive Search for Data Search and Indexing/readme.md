<h1>Explore an Azure AI Search index (UI)</h1>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Let’s imagine you work for Fourth Coffee, a national coffee chain. You’re asked to help build a knowledge mining
    solution that makes it easy to search for insights about customer experiences. You decide to build an Azure AI
    Search index using data extracted from customer reviews.</p>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">In this lab you’ll:</p>
<ul>
    <li style="font-size: 16px;">Create Azure resources</li>
    <li style="font-size: 16px;">Extract data from a data source</li>
    <li style="font-size: 16px;">Enrich data with AI skills</li>
    <li style="font-size: 16px;">Use Azure’s indexer in the Azure portal</li>
    <li style="font-size: 16px;">Query your search index</li>
    <li style="font-size: 16px;">Review results saved to a Knowledge Store</li>
</ul>

<h2 style="padding-left: 15px; padding-right: 15px;">Azure resources needed</h2>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">The solution you’ll create for Fourth Coffee requires the following resources in your Azure subscription:</p>
<ul>
    <li style="font-size: 16px;">An <b>Azure AI Search</b> resource, which will manage indexing and querying.</li>
    <li style="font-size: 16px;">An <b>Azure AI services</b> resource, which provides AI services for skills that your search solution can use to enrich
        the data in the data source with AI-generated insights.</li>
    <li style="font-size: 16px;">A Storage account with blob containers, which will store raw documents and other collections of tables,
        objects, or files.</li>
</ul>

<h3 style="padding-left: 15px; padding-right: 15px;">Create an Azure AI Search resource</h3>
<ol>
    <li style="font-size: 16px;">Sign into the Azure portal.</li>
    <li style="font-size: 16px;">Click the <b>+ Create a resource</b> button, search for Azure AI Search, and create a <b>Azure AI Search</b> resource with
        the following settings:
        <ul>
            <li style="font-size: 16px;"><b>Subscription:</b> Your Azure subscription.</li>
            <li style="font-size: 16px;"><b>Resource group:</b> Select or create a resource group with a unique name.</li>
            <li style="font-size: 16px;"><b>Service name:</b> A unique name.</li>
            <li style="font-size: 16px;"><b>Location:</b> Choose any available region.</li>
            <li style="font-size: 16px;"><b>Pricing tier:</b> Basic</li>
        </ul>
    </li>
    <li style="font-size: 16px;"><b>Select Review + create</b>, and after you see the response <b>Validation Success</b>, select <b>Create</b>.</li>
    <li style="font-size: 16px;">After deployment completes, select <b>Go to resource</b>. On the Azure AI Search overview page, you can add indexes,
        import data, and search created indexes.</li>
</ol>

<h3 style="padding-left: 15px; padding-right: 15px;">Create an Azure AI services resource</h3>
<ol>
    <li style="font-size: 16px;">You’ll need to provision an <b>Azure AI services</b> resource that’s in the same location as your Azure AI Search
        resource. Your search solution will use this resource to enrich the data in the datastore with AI-generated
        insights.</li>
    <li style="font-size: 16px;">Return to the home page of the Azure portal. Click the <b>+ Create a resource</b> button and search for Azure AI
        services. Select <b>create</b> an <b>Azure AI services</b> plan. You will be taken to a page to create an Azure AI services
        resource. Configure it with the following settings:
        <ul>
            <li style="font-size: 16px;"><b>Subscription:</b> Your Azure subscription.</li>
            <li style="font-size: 16px;"><b>Resource group:</b> The same resource group as your Azure AI Search resource.</li>
            <li style="font-size: 16px;"><b>Region:</b> The same location as your Azure AI Search resource.</li>
            <li style="font-size: 16px;"><b>Name:</b> A unique name.</li>
            <li style="font-size: 16px;"><b>Pricing tier:</b> Standard S0</li>
            <li style="font-size: 16px;"><b>By checking this box I acknowledge that I have read and understood all the terms below:</b> Selected
            </li>
        </ul>
    </li>
    <li style="font-size: 16px;">Select <b>Review + create</b>. After you see the response <b>Validation Passed</b>, select <b>Create</b>.</li>
    <li style="font-size: 16px;">Wait for deployment to complete, then view the deployment details.</li>
</ol>

<h3 style="padding-left: 15px; padding-right: 15px;">Create a storage account</h3>
<ol>
    <li style="font-size: 16px;">Return to the home page of the Azure portal, and then select the <b>+ Create a resource</b> button.</li>
    <li style="font-size: 16px;">Search for storage account, and create a <b>Storage account</b> resource with the following settings:
        <ul>
            <li style="font-size: 16px;"><b>Subscription:</b> Your Azure subscription.</li>
            <li style="font-size: 16px;"><b>Resource group:</b> The same resource group as your Azure AI Search and Azure AI services resources.</li>
            <li style="font-size: 16px;"><b>Storage account name:</b> A unique name.</li>
            <li style="font-size: 16px;"><b>Location:</b> Choose any available location.</li>
            <li style="font-size: 16px;"><b>Performance:</b> Standard</li>
            <li style="font-size: 16px;"><b>Redundancy:</b> Locally redundant storage (LRS)</li>
        </ul>
    </li>
    <li style="font-size: 16px;">Click <b>Review</b> and then click <b>Create</b>. Wait for deployment to complete, and then go to the deployed resource.</li>
    <li style="font-size: 16px;">In the Azure Storage account you created, in the left-hand menu pane, select <b>Configuration</b> (under <b>Settings</b>).
    </li>
    <li style="font-size: 16px;">Change the setting for Allow Blob anonymous access to <b>Enabled</b> and then select <b>Save</b>.</li>
</ol>

<h2 style="padding-left: 15px; padding-right: 15px;">Upload Documents to Azure Storage</h1>
<ol>
    <li style="font-size: 16px;">In the left-hand menu pane, select <b>Containers</b>.</li>
    <img style="margin-bottom: 10px; border-radius: 10px;" src="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/media/create-cognitive-search-solution/storage-blob-1.png" />
    <li style="font-size: 16px;">Select <b>+ Container</b>. A pane on your right-hand side opens.</li>
    <li style="font-size: 16px;">Enter the following settings, and click <b>Create</b>:</li>
    <ul>
        <li style="font-size: 16px;"><b>Name:</b> coffee-reviews</li>
        <li style="font-size: 16px;"><b>Public access level:</b> Container (anonymous read access for containers and blobs)</li>
        <li style="font-size: 16px;"><b>Advanced:</b> no changes.</li>
    </ul>
    <li style="font-size: 16px;">In a new browser tab, download the <a href="https://aka.ms/mslearn-coffee-reviews">zipped coffee reviews</a> from https://aka.ms/mslearn-coffee-reviews, and extract the files to the reviews folder.</li>
    <li style="font-size: 16px;">In the Azure portal, select your coffee-reviews container. In the container, select <b>Upload</b>.</li>
    <img style="margin-bottom: 10px; border-radius: 10px;" src="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/media/create-cognitive-search-solution/storage-blob-3.png" />
    <li style="font-size: 16px;">In the <b>Upload blob</b> pane, select <b>Select a file</b>.</li>
    <li style="font-size: 16px;">In the Explorer window, select <b>all</b> the files in the reviews folder, select <b>Open</b>, and then select <b>Upload</b>.</li>
    <img style="margin-bottom: 10px; border-radius: 10px;" src="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/media/create-cognitive-search-solution/6a-azure-container-upload-files.png" />
    <li style="font-size: 16px;">After the upload is complete, you can close the <b>Upload blob</b> pane. Your documents are now in your coffee-reviews storage container.</li>
</ol>

<h2 style="padding-left: 15px; padding-right: 15px;">Index the documents</h2>

<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">After you have the documents in storage, you can use Azure AI Search to extract insights from the documents. The
    Azure portal provides an Import data wizard. With this wizard, you can automatically create an index and
    indexer for supported data sources. You’ll use the wizard to create an index, and import your search documents
    from storage into the Azure AI Search index.</p>
<ol>
<li style="font-size: 16px;">In the Azure portal, browse to your Azure AI Search resource. On the <b>Overview page</b>, select Import data.</li>

<img style="margin-bottom: 10px; border-radius: 10px;" src="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/media/create-cognitive-search-solution/azure-search-wizard-1.png" alt="Screenshot that shows the import data wizard." />

<li style="font-size: 16px;">On the <b>Connect to your data</b> page, in the <b>Data Source</b> list, select <b>Azure Blob Storage</b>. Complete the data store details with the following values:</li>

<ul>
    <li style="font-size: 16px;"><b>Data Source:</b> Azure Blob Storage</li>
    <li style="font-size: 16px;"><b>Data source name:</b> coffee-customer-data</li>
    <li style="font-size: 16px;"><b>Data to extract:</b> Content and metadata</li>
    <li style="font-size: 16px;"><b>Parsing mode:</b> Default</li>
    <li style="font-size: 16px;"><b>Connection string:</b> *Select <b>Choose an existing connection</b>. Select your storage account, select the <b>coffee-reviews</b> container, and then click <b>Select</b>.</li>
    <li style="font-size: 16px;"><b>Managed identity authentication:</b> None</li>
    <li style="font-size: 16px;"><b>Container name:</b> this setting is auto-populated after you choose an existing connection.</li>
    <li style="font-size: 16px;"><b>Blob folder:</b> Leave this blank.</li>
    <li style="font-size: 16px;"><b>Description:</b> Reviews for Fourth Coffee shops.</li>
</ul>

<li style="font-size: 16px;">Select <b>Next: Add cognitive skills (Optional)</b>.</li>

<li style="font-size: 16px;">In the <b>Attach Cognitive Services</b> section, select your Azure AI services resource.</li>

<li style="font-size: 16px;">In the <b>Add enrichments</b> section:</li>
<ul>
    <li style="font-size: 16px;">Change the <b>Skillset name</b> to <b>coffee-skillset</b>.</li>
    <li style="font-size: 16px;">Select the checkbox <b>Enable OCR and merge all text into merged_content field</b>.</li>
    <li style="font-size: 16px;">Ensure that the <b>Source data field</b> is set to <b>merged_content</b>.</li>
    <li style="font-size: 16px;">Change the <b>Enrichment granularity level</b> to <b>Pages (5000 character chunks)</b>.</li>
    <li style="font-size: 16px;">Don’t select Enable incremental enrichment</li><br>
<li style="font-size: 16px;">Select the following enriched fields:</li>
</ul>
<table>
    <tr>
        <th>Cognitive Skill</th>
        <th>Parameter</th>
        <th>Field name</th>
    </tr>
    <tr>
        <td>Extract location names</td>
        <td></td>
        <td>locations</td>
    </tr>
    <tr>
        <td>Extract key phrases</td>
        <td></td>
        <td>keyphrases</td>
    </tr>
    <tr>
        <td>Detect sentiment</td>
        <td></td>
        <td>sentiment</td>
    </tr>
    <tr>
        <td>Generate tags from images</td>
        <td></td>
        <td>imageTags</td>
    </tr>
    <tr>
        <td>Generate captions from images</td>
        <td></td>
        <td>imageCaption</td>
    </tr>
</table>

<li style="font-size: 16px;">Under Save enrichments to a knowledge store, select:</li>
<ul>
    <li style="font-size: 16px;">Image projections</li>
    <li style="font-size: 16px;">Documents</li>
    <li style="font-size: 16px;">Pages</li>
    <li style="font-size: 16px;">Key phrases</li>
    <li style="font-size: 16px;">Entities</li>
    <li style="font-size: 16px;">Image details</li>
    <li style="font-size: 16px;">Image references</li>
</ul>

<li style="font-size: 16px;">Select <b>Azure blob projections: Document</b>. A setting for Container name with the knowledge-store container auto-populated displays. Don’t change the container name.</li>

<li style="font-size: 16px;">Select <b>Next: Customize target index</b>. Change the <b>Index name</b> to <b>coffee-index</b>.</li>

<li style="font-size: 16px;">Ensure that the <b>Key</b> is set to <b>metadata_storage_path</b>. Leave <b>Suggester name</b> blank and <b>Search mode</b> autopopulated.</li>

<li style="font-size: 16px;">Review the index fields’ default settings. Select <b>filterable</b> for all the fields that are already selected by
    default.</li>

<img style="margin-bottom: 10px; border-radius: 10px;" src="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/media/create-cognitive-search-solution/6a-azure-cognitive-search-customize-index.png" alt="Screenshot that shows the customize index pane with the index name entered and 'Filterable' selected for a default index field."/>

<li style="font-size: 16px;">Select <b>Next: Create an indexer</b>.</li>

<li style="font-size: 16px;">Change the <b>Indexer name</b> to <b>coffee-indexer</b>.</li>

<li style="font-size: 16px;">Leave the <b>Schedule</b> set to <b>Once</b>.</li>

<li style="font-size: 16px;">Expand the <b>Advanced options</b>. Ensure that the <b>Base-64 Encode Keys</b> option is selected, as encoding keys can make the index more efficient.</li>

<li style="font-size: 16px;">Select <b>Submit</b> to create the data source, skillset, index, and indexer. The indexer is run automatically and runs the indexing pipeline, which:</li>
<ul>
    <li style="font-size: 16px;">Extracts the document metadata fields and content from the data source.</li>
    <li style="font-size: 16px;">Runs the skillset of cognitive skills to generate more enriched fields.</li>
    <li style="font-size: 16px;">Maps the extracted fields to the index.</li>
</ul>

<li style="font-size: 16px;">Return to your Azure AI Search resource page. On the left pane, under <b>Search Management</b>, select <b>Indexers</b>. Select the newly created <b>coffee-indexer</b>. Wait a minute, and select <b>&orarr; Refresh</b> until the <b>Status</b> indicates success.</li>

<li style="font-size: 16px;">Select the indexer name to see more details.</li>

<img style="margin-bottom: 10px; border-radius: 10px;" src="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/media/create-cognitive-search-solution/6a-search-indexer-success.png" alt="Screenshot that shows the coffee-indexer Indexer successfully created."/>
</ol>

<h2 style="padding-left: 15px; padding-right: 15px;">Query the index</h2>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">Use the Search explorer to write and test queries. Search explorer is a tool built into the Azure portal that
gives you an easy way to validate the quality of your search index. You can use Search explorer to write queries
and review results in JSON.</p>

<ol>
<li style="font-size: 16px;">In your Search service’s Overview page, select <b>Search explorer</b> at the top of the screen.</li>

<img style="margin-bottom: 10px; border-radius: 10px;" src="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/media/create-cognitive-search-solution/5-exercise-screenshot-7.png" alt="Screenshot of how to find Search explorer.">

<li style="font-size: 16px;">Notice how the index selected is the coffee-index you created. Below the index selected, change the view to <b>JSON view</b>.</li>

<img style="margin-bottom: 10px; border-radius: 10px;" src="https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/media/create-cognitive-search-solution/search-explorer-query.png" alt="Screenshot of the Search explorer.">
</ol>
<ol>
<p style="font-size: 16px; padding-left: 30px; padding-right: 30px;">In the <b>JSON query editor</b> field, copy and paste:</p>

<pre><code>{
"search": "*",
"count": true
}</code></pre>

<li style="font-size: 16px;">Select <b>Search</b>. The search query returns all the documents in the search index, including a count of all the documents in the <b>@odata.count</b> field. The search index should return a JSON document containing your search results.</li>

<li style="font-size: 16px;">Now let’s filter by location. In the <b>JSON query editor</b> field, copy and paste:</li>

<pre><code>{
"search": "locations:'Chicago'",
"count": true
}</code></pre>

<li style="font-size: 16px;">Select <b>Search</b>. The query searches all the documents in the index and filters for reviews with a Chicago location. You should see 3 in the @odata.count field.</li>

<li style="font-size: 16px;">Now let’s filter by sentiment. In the <b>JSON query editor</b> field, copy and paste:</li>

<pre><code>{
"search": "sentiment:'negative'",
"count": true
}</code></pre>

<li style="font-size: 16px;">Select <b>Search</b>. The query searches all the documents in the index and filters for reviews with a negative
    sentiment. You should see 1 in the @odata.count field.</li>

<li style="font-size: 16px;">One of the problems we might want to solve for is why there might be certain reviews. Let’s take a look at the
    key phrases associated with the negative review. What do you think might be the cause of the review?</li>
</ol>