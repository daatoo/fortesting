### Getting Started

<Callout attributes='{"isFitToPage":true,"dataType":"success","style":{"width":"100%","minWidth":"100%"}}'>
<span style="color:var(--dark-notification-success-box-content)">You need a valid API key to authenticate your requests. If you don't have one yet, follow the instructions in the </span>
<a href="https://docs.similarweb.com/api-v5/getting-started/authentication" target="_blank"><span style="color:var(--dark-notification-success-box-content)">Authentication</span></a>
<span style="color:var(--dark-notification-success-box-content)"> section to obtain yours.</span>
</Callout>

To make your first API request, follow these steps:

<Steps attributes='{"style":{"width":"100%","minWidth":"100%"}}'>
<Step stepNumber="1" title="">
<p>Authentication</p><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">Acquire your API key by following the instructions in the Authentication section</span><p></p>
</Step>
<Step stepNumber="2" title="">
<p>Construct the Endpoint Request</p><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">All API requests start with a base URL followed by the specific endpoint you want to access. Refer to the relevant API endpoint in the </span><a href="https://docs.similarweb.com/api-v5/similarweb-api/website-analysis-api" target="_blank"><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">API Reference </span></a><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">for the correct URL structure.</span><p></p>
</Step>
<Step stepNumber="3" title="">
<p>Send the request</p><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">Use your preferred programming language or tool to send an HTTP GET or POST request to the constructed endpoint. Don't forget to include your API key in the request headers.</span><p></p>
</Step>
<Step stepNumber="4" title="">
<p>Receive the Response</p><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">The API will respond with data in JSON format. You can parse this data to extract the insights you need for your analysis</span><p></p>
</Step>
</Steps><Divider />

### Request Example

<CodeBlock attributes='{"isFitToPage":true,"style":{},"lang":"plainText","label":"Plain text"}'>
  <CodeLine>curl -X GET "https://api.similarweb.com/v5/website-analysis/websites/traffic-and-engagement" \</CodeLine>
  <CodeLine>  -H "api-key: YOUR_API_KEY" \</CodeLine>
  <CodeLine>  -G \</CodeLine>
  <CodeLine>  -d "domain=nike.com" \</CodeLine>
  <CodeLine>  -d "metrics=visits,bounce_rate,pages_per_visit" \</CodeLine>
  <CodeLine>  -d "granularity=monthly" \</CodeLine>
  <CodeLine>  -d "start_date=2024-10-01" \</CodeLine>
  <CodeLine>  -d "end_date=2024-12-31" </CodeLine>
</CodeBlock>

### Response Example

<CodeBlock attributes='{"isFitToPage":true,"style":{},"lang":"json","label":"JSON"}'>
  <CodeLine>{
  "meta": {
    "request": {
      "domain": "nike.com",
      "metrics": ["visits", "bounce_rate", "pages_per_visit"],
      "granularity": "monthly",
      "start_date": "2024-10-01",
      "end_date": "2024-12-31",
      "country": "WW"
    },
    "status": "Success",
    "last_updated": "2025-01-15"
  },
  "data": [
    {
      "date": "2024-10-01",
      "visits": 89234567,
      "bounce_rate": 0.2891,
      "pages_per_visit": 4.32
    },
    {
      "date": "2024-11-01",
      "visits": 94123456,
      "bounce_rate": 0.2734,
      "pages_per_visit": 4.67
    },
    {
      "date": "2024-12-01",
      "visits": 102345678,
      "bounce_rate": 0.2645,
      "pages_per_visit": 4.89
    }
  ]
}</CodeLine>
  <CodeLine>{
  "meta": {
    "request": {
      "domain": "nike.com",
      "metrics": ["visits", "bounce_rate", "pages_per_visit"],
      "granularity": "monthly",
      "start_date": "2024-10-01",
      "end_date": "2024-12-31",
      "country": "WW"
    },
    "status": "Success",
    "last_updated": "2025-01-15"
  },
  "data": [
    {
      "date": "2024-10-01",
      "visits": 89234567,
      "bounce_rate": 0.2891,
      "pages_per_visit": 4.32
    },
    {
      "date": "2024-11-01",
      "visits": 94123456,
      "bounce_rate": 0.2734,
      "pages_per_visit": 4.67
    },
    {
      "date": "2024-12-01",
      "visits": 102345678,
      "bounce_rate": 0.2645,
      "pages_per_visit": 4.89
    }
  ]
}</CodeLine>
</CodeBlock>
<Divider />

### API Options: Choose the API that best suits your needs

#### REST API

This is what we used in the example above. REST API is perfect for:

*   **Real-time dashboards** requiring up-to-date data
    
*   **Application integration** with on-demand queries
    
*   **Quick analysis** of specific domains or time periods
    
*   **Small to medium data volumes** (single/few domains)
    

#### Batch API

If you're looking for large-scale analysis, this is the API for you. It's ideal for:

*   **Historical analysis** requiring months/years of data
    
*   **Bulk domain research** (hundreds to millions of domains)
    
*   **Data warehouse loading** with direct S3/Snowflake delivery
    
*   **Automated reporting** with scheduled data updates
    

### Example Batch Request

<CodeBlock attributes='{"isFitToPage":true,"style":{},"lang":"plainText","label":"Plain text"}'>
  <CodeLine>curl -X POST "https://api.similarweb.com/batch/v4/request-report" \</CodeLine>
  <CodeLine>  -H "api-key: YOUR_BATCH_API_KEY" \</CodeLine>
  <CodeLine>  -H "Content-Type: application/json" \</CodeLine>
  <CodeLine>  -d '{</CodeLine>
  <CodeLine>    "report_query": {</CodeLine>
  <CodeLine>      "tables": [{</CodeLine>
  <CodeLine>        "vtable": "traffic_and_engagement",</CodeLine>
  <CodeLine>        "granularity": "monthly",</CodeLine>
  <CodeLine>        "filters": {</CodeLine>
  <CodeLine>          "domains": ["nike.com", "adidas.com", "underarmour.com"],</CodeLine>
  <CodeLine>          "countries": ["US", "GB", "DE"]</CodeLine>
  <CodeLine>        },</CodeLine>
  <CodeLine>        "metrics": ["visits", "bounce_rate", "pages_per_visit"],</CodeLine>
  <CodeLine>        "start_date": "2020-01-01",</CodeLine>
  <CodeLine>        "end_date": "2024-12-31"</CodeLine>
  <CodeLine>      }]</CodeLine>
  <CodeLine>    }</CodeLine>
  <CodeLine>  }' </CodeLine>
</CodeBlock>

Learn more about the differenes between Batch and REST APIs and how to use them by visiting this [guide](https://docs.similarweb.com/api-v5/guides/rest-api-vs-batch-api).

<Divider />

### Next Steps

Now that you've made your first successful request:

#### **Recommended Actions**

1.  [**Check your credit balance**](https://docs.similarweb.com/api-v5/guides/data-credits-calculations/check-credit-balance) - Monitor usage and costs
    
2.  [**Browse popular use cases**](https://docs.similarweb.com/api-v5/guides/popular-use-cases) - Learn about additional ways to leverage our data
    
3.  [**Understand error handling**](https://docs.similarweb.com/api-v5/guides/error-handling-and-troubleshooting) - Get familiar with the different erros
    

<Divider />

**Questions or Need Help?** Our [support team](https://www.similarweb.com/corp/contact-us/) is ready to help you build successful integrations and maximize the value of your API access.