Secure API Access with API Keys
-------------------------------

All Similarweb API requests require authentication using API keys. This guide covers everything you need to know about creating, managing, and using your API keys securely.

<Divider />

Before You Begin
----------------

<Callout attributes='{"isFitToPage":true,"dataType":"warning","style":{"width":"100%","minWidth":"100%"}}'>
<ul class="slate-ul "><li class="slate-li "><div style="position:relative">Active Similarweb account with API access (contact your Account Manager if you need access)</div></li><li class="slate-li "><div style="position:relative">Admin-level permissions (required for API key generation and management)</div></li></ul>
</Callout>

API Keys Creation
-----------------

<Steps attributes='{"style":{"width":"100%","minWidth":"100%"}}'>
<Step stepNumber="1" title="Access Your Account Settings">
<p></p><ol class="slate-ol "><li class="slate-li "><div style="position:relative"><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">Log in to your </span><a href="https://pro.similarweb.com/" target="_blank"><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">Similarweb platform</span></a></div></li><li class="slate-li "><div style="position:relative"><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">Navigate to </span><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)"><strong class="slate-bold">Settings</strong></span><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)"> → </span><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)"><strong class="slate-bold">Account</strong></span><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)"> from the left menu</span></div></li><li class="slate-li "><div style="position:relative"><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">Look for the </span><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)"><strong class="slate-bold">Data Tools</strong></span><span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)"> section</span></div></li></ol><p></p>
</Step>
<Step stepNumber="2" title="Generate Your API Key">
<p></p><ol class="slate-ol "><li class="slate-li "><div style="position:relative">Select either <strong class="slate-bold">REST API or Batch API</strong></div></li><li class="slate-li "><div style="position:relative">Scroll down and click <strong class="slate-bold">Generate a new API key</strong></div></li><li class="slate-li "><div style="position:relative">Give your API key a name</div></li><li class="slate-li "><div style="position:relative">Select the primary use for this key (your email or another user)</div></li><li class="slate-li "><div style="position:relative">Click <strong class="slate-bold">Create</strong></div></li><li class="slate-li "><div style="position:relative">Your new API key will appear in the <strong class="slate-bold">Generated Keys table</strong> under the user name you selected</div></li><li class="slate-li "><div style="position:relative">Make sure the <strong class="slate-bold">Activation</strong> toggle is enabled (switched on)</div></li></ol><Callout attributes='{"isFitToPage":true,"dataType":"warning","style":{"style":{"width":"100%","minWidth":"100%"},"width":"100%","minWidth":"100%"}}'>
<span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)"><strong class="slate-bold">Important</strong></span>
<span style="background-color:rgb(0, 6, 22);color:rgb(214, 215, 218)">: Only activated API keys can access data. If your key shows as inactive, you'll receive "Invalid API key" errors.</span>
</Callout>

<p></p>
</Step>
</Steps>

<Video url="https://d24lr4zqs1tgqh.cloudfront.net/d13fccb0-3ff2-48a6-a0df-5eacd16a0b14.jpg"/>

API Keys Management
-------------------

Admins can create and manage API keys for the entire account.

1.  Every user can have up to 3 active keys.
    
2.  There's no expiry date on active keys.
    
3.  When a user is removed from the account his API key is revoked, there’s also an option of specifically removing users API keys.
    
4.  Admins can set credit limits per user under each API, for example a user can have 10K on REST API and 10K on Batch API. Only Admins can control limits. The limits are per user and not per key.
    

<Image url="https://d24lr4zqs1tgqh.cloudfront.net/f56e1522-2b1b-4673-aaac-c52c09317226.jpg" alt="" caption="" attributes='{"width":"1280px","height":"630px"}'/>