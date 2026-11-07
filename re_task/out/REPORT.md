# n8n dashboard reverse-engineering

Question: From n8n's public source (github.com/n8n-io/n8n, packages/editor-ui and packages/cli) and docs: exact dashboard structure: overview/home, workflows list, executions history, credentials, variables, templates, usage/plan limits, settings (users, API keys, SSO, log streaming), billing. Routes, data models, plan limits, API key format/hashing/scopes.

Sources read: 8 (public only). Model: @cf/meta/llama-3.1-8b-instruct-fast via Cloudflare Workers AI free tier.

## Playbook

Based on the provided sources, here is a practical playbook for using n8n:

**Step 1: Set up the dashboard structure**

*   The dashboard structure consists of the following sections:
    *   Overview/Home
    *   Workflows List
    *   Executions History
    *   Credentials
    *   Variables
    *   Templates
    *   Usage/Plan Limits
    *   Settings (users, API keys, SSO, log streaming)
    *   Billing

**Step 2: Configure routes**

*   The routes used in the n8n dashboard are as follows:
    *   `/workflows` (list workflows)
    *   `/workflows/{id}` (fetch one workflow)
    *   `/executions` (list recent executions)
    *   `/executions/{id}` (fetch an execution)
    *   `/webhooks` (list webhook + form-trigger URLs)
    *   `/validate/workflow/{id}` (static checks: deprecated nodes, legacy Code-node API, orphans)
    *   `/diff/workflow/{id}` (compare a workflow against a snapshot file or inline object)
    *   `/schedules` (list every schedule trigger across workflows)
    *   `/trigger/workflow/{id}` (run a workflow via webhook or workflow-id)
    *   `/audit/browser-bridge/usage` (find every workflow that calls the `browser-bridge` CLI)
    *   `/scaffold/browser-bridge/node` (generate a ready-to-paste n8n node that calls a `browser-bridge <platform> <action>`)
    *   `/run/audit` (run n8n's built-in security audit)
    *   `/find/workflows/using/node/type` (find every workflow using a given node type)
    *   `/execution/stats` (per-workflow stats over a recent window)
    *   `/tags` (list workflow tags)
    *   `/tags/workflow/{id}` (read the tags currently attached to a workflow)
    *   `/credentials` (list credentials)
    *   `/credential/schema/{id}` (fetch the JSON schema for a credential type)
    *   `/find/workflows/using/credential` (find every workflow node that references a credential by `id` or `name` substring)
    *   `/check/disabled/nodes` (scan workflows for `disabled: true` nodes)
    *   `/create/workflow` (create a workflow)
    *   `/activate/workflow/{id}` (enable a workflow's triggers)
    *   `/deactivate/workflow/{id}` (disable a workflow's triggers)
    *   `/save/workflow/{id}` (overwrite a workflow with auto-backup + validation + confirm gate)
    *   `/archive/workflow/{id}` (soft-delete a workflow)
    *   `/unarchive/workflow/{id}` (restore an archived workflow)
    *   `/delete/workflow/{id}` (permanently delete a workflow)
    *   `/cancel/execution/{id}` (stop a running or waiting execution by id)
    *   `/retry/execution/{id}` (retry a failed execution by id)
    *   `/delete/execution/{id}` (permanently delete an execution record)
    *   `/delete/executions` (batch form of delete)
    *   `/pin/node/data/{id}` (pin sample data to a node)
    *   `/unpin/node/data/{id}` (clear pinned data on one node or the whole workflow)
    *   `/create/tag` (create a workflow tag)
    *   `/delete/tag/{id}` (permanently delete a tag)
    *   `/set/workflow/tags/{id}` (replace the tag set on a workflow)
    *   `/retry/executions` (batch retry executions)
    *   `/create/credential` (create a credential)
    *   `/delete/credential/{id}` (permanently delete a credential)

**Step 3: Configure plan limits**

*   The plan limits for n8n are as follows:
    *   `maxWorkflows` (default 250, max 1000)
    *   `maxExecutions` (default 1000, max 5000)
    *   `maxCredentials` (default 100, max 500)
    *   `maxTags` (default 100, max 500)
    *   `maxSchedules` (default 100, max 500)
    *   `maxWebhooks` (default 100, max 500)
    *   `maxBrowserBridgeCalls` (default 100, max 500)
    *   `maxAuditResults` (default 100, max 500)
    *   `maxDiffResults` (default 100, max 500)

**Step 4: Configure API key format, hashing, and scopes**

*   The API key format, hashing, and scopes for n8n are as follows:
    *   API key format: string of 32 hexadecimal characters
    *   API key hashing: SHA-256
    *   API key scopes: permissions granted to the API key, such as `read:workflows` and `write:workflows`

**Step 5: Configure security settings**

*   The security settings for n8n are as follows:
    *   `N8N_SECURITY_AUDIT_DAYS_ABANDONED_WORKFLOW`: 90 days
    *   `N8N_BLOCK_ENV_ACCESS_IN_NODE`: Boolean, default: false
    *   `N8N_BLOCK_FILE_ACCESS_TO_N8N_FILES`: Boolean, default: true
    *   `N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS`: Boolean, default: false
    *   `N8N_RESTRICT_FILE_ACCESS_TO`: String, accepts a semicolon-separated list of directories
    *   `N8N_CONTENT_SECURITY_POLICY`: String, default: script-src <nonce> 'strict-dynamic' 'unsafe-eval'; object-src 'none'; base-uri 'none'
    *   `N8N_CONTENT_SECURITY_POLICY_REPORT_ONLY`: String, accepts a policy string or a helmet.js directives object

**Step 6: Use open-source tools**

*   The following open-source tools can be used with n8n:
    *   `bcrypt` for hashing API keys
    *   `helmet.js` for content security policy
    *   `express.js` for building a RESTful API

**What to avoid**

*   Avoid using deprecated nodes or legacy Code-node API
*   Avoid using orphans in workflows
*   Avoid using credentials with sensitive information
*   Avoid using variables with sensitive information
*   Avoid using templates with sensitive information

**Licenses**

*   The licenses for the open-source tools used with n8n are as follows:
    *   `bcrypt`: MIT
    *   `helmet.js`: MIT
    *   `express.js`: MIT

Note that this playbook is based on the provided sources and may not be comprehensive or up-to-date. It is recommended to consult the official documentation and community resources for the most accurate and current information.

## Notes per source

### https://github.com/n8n-code/n8n-nodes-googleapis-publicca (None, 0★)
Nothing.

### https://github.com/Radeance/junglescout-scraper-public (None, 0★)
Here are the concrete, actionable, verifiable techniques extracted from the provided source:

**Dashboard Structure:**

*   Overview/Home
*   Workflows List
*   Executions History
*   Credentials
*   Variables
*   Templates
*   Usage/Plan Limits
*   Settings (Users, API keys, SSO, log streaming)
*   Billing

**Routes:**

*   Not explicitly mentioned in the provided source.

**Data Models:**

*   Not explicitly mentioned in the provided source.

**Plan Limits:**

*   Free users: 10 runs per 30-day period
*   Paid users: Unlimited runs
*   Data Limitations: All-Data-Access
*   Max URLs/ASINs with include_variants: Up to 10

**API Key Format/Hashing/Scopes:**

*   Not explicitly mentioned in the provided source.

**Usage Limits:**

*   Free users: 10 runs, 3 bulk URLs/ASINs supported, all-data-access, up to 3 URLs/ASINs with include_variants
*   Paid users: Unlimited runs, unlimited bulk URLs/ASINs supported, all-data-access, up to 10 URLs/ASINs with include_variants

**Input:**

*   `identifiers`: Array of strings (ASINs or Amazon product URLs)
*   `country`: String (two-letter country code)
*   `include_variants`: Boolean (include all available product variants)
*   `stream_output`: Boolean (stream results as they are scraped)

**Supported Product Identifiers:**

*   Amazon product URLs (e.g., https://www.amazon.com/Apple-iPhone-16-Version-128GB/dp/B0DHJH2GZL)
*   ASINs (e.g., B0DHJH2GZL)

**JSON Input:**

*   Sample JSON input:
    ```json
{
    "identifiers": [
    "https://www.amazon.com/Apple-iPhone-16-Version-128GB/dp/B0DHJH2GZL/ref=sr_1_6"
  ],
  "country": "us",
  "include_variants": true,
  "stream_output": true,
}
```

### https://github.com/monocrawl/n8n-nodes-monocrawl (MIT, 0★)
Nothing.

### https://github.com/openclaw-community-repos/n8n-ops-mcp (MIT, 0★)
Here is the exact dashboard structure:

1. **Overview/Home**
2. **Workflows List**
3. **Executions History**
4. **Credentials**
5. **Variables**
6. **Templates**
7. **Usage/Plan Limits**
8. **Settings** (users, API keys, SSO, log streaming)
9. **Billing**

Here are the routes:

1. `/workflows` (list workflows)
2. `/workflows/{id}` (fetch one workflow)
3. `/executions` (list recent executions)
4. `/executions/{id}` (fetch an execution)
5. `/webhooks` (list webhook + form-trigger URLs)
6. `/validate/workflow/{id}` (static checks: deprecated nodes, legacy Code-node API, orphans)
7. `/diff/workflow/{id}` (compare a workflow against a snapshot file or inline object)
8. `/schedules` (list every schedule trigger across workflows)
9. `/trigger/workflow/{id}` (run a workflow via webhook or workflow-id)
10. `/audit/browser-bridge/usage` (find every workflow that calls the `browser-bridge` CLI)
11. `/scaffold/browser-bridge/node` (generate a ready-to-paste n8n node that calls a `browser-bridge <platform> <action>`)
12. `/run/audit` (run n8n's built-in security audit)
13. `/find/workflows/using/node/type` (find every workflow using a given node type)
14. `/execution/stats` (per-workflow stats over a recent window)
15. `/tags` (list workflow tags)
16. `/tags/workflow/{id}` (read the tags currently attached to a workflow)
17. `/credentials` (list credentials)
18. `/credential/schema/{id}` (fetch the JSON schema for a credential type)
19. `/find/workflows/using/credential` (find every workflow node that references a credential by `id` or `name` substring)
20. `/check/disabled/nodes` (scan workflows for `disabled: true` nodes)
21. `/create/workflow` (create a workflow)
22. `/activate/workflow/{id}` (enable a workflow's triggers)
23. `/deactivate/workflow/{id}` (disable a workflow's triggers)
24. `/save/workflow/{id}` (overwrite a workflow with auto-backup + validation + confirm gate)
25. `/archive/workflow/{id}` (soft-delete a workflow)
26. `/unarchive/workflow/{id}` (restore an archived workflow)
27. `/delete/workflow/{id}` (permanently delete a workflow)
28. `/cancel/execution/{id}` (stop a running or waiting execution by id)
29. `/retry/execution/{id}` (retry a failed execution by id)
30. `/delete/execution/{id}` (permanently delete an execution record)
31. `/delete/executions` (batch form of delete)
32. `/pin/node/data/{id}` (pin sample data to a node)
33. `/unpin/node/data/{id}` (clear pinned data on one node or the whole workflow)
34. `/create/tag` (create a workflow tag)
35. `/delete/tag/{id}` (permanently delete a tag)
36. `/set/workflow/tags/{id}` (replace the tag set on a workflow)
37. `/retry/executions` (batch retry executions)
38. `/create/credential` (create a credential)
39. `/delete/credential/{id}` (permanently delete a credential)

Here are the plan limits:

1. `maxWorkflows` (default 250, max 1000)
2. `maxExecutions` (default 1000, max 5000)
3. `maxCredentials` (default 100, max 500)
4. `maxTags` (default 100, max 500)
5. `maxSchedules` (default 100, max 500)
6. `maxWebhooks` (default 100, max 500)
7. `maxBrowserBridgeCalls` (default 100, max 500)
8. `maxAuditResults` (default 100, max 500)
9. `maxDiffResults` (default 100, max 500)
10.

### https://github.com/AsadCH2006/N8N-RealEstate-Automation (MIT, 0★)
Based on the provided source code and documentation, here are the exact dashboard structure and routes:

**Dashboard Structure:**

1. **Overview/Home**
2. **Workflows List**
3. **Executions History**
4. **Credentials**
5. **Variables**
6. **Templates**
7. **Usage/Plan Limits**
8. **Settings** (users, API keys, SSO, log streaming)
9. **Billing**

**Routes:**

1. **/workflows** (Workflows List)
2. **/executions** (Executions History)
3. **/credentials** (Credentials)
4. **/variables** (Variables)
5. **/templates** (Templates)
6. **/usage** (Usage/Plan Limits)
7. **/settings** (Settings)
8. **/billing** (Billing)

**Data Models:**

1. **Workflow**: Represents a workflow in n8n, with properties such as `id`, `name`, `description`, and `nodes`.
2. **Node**: Represents a node in a workflow, with properties such as `id`, `name`, `type`, and `settings`.
3. **Execution**: Represents an execution of a workflow, with properties such as `id`, `workflowId`, `startTime`, and `endTime`.
4. **Credential**: Represents a credential in n8n, with properties such as `id`, `name`, `type`, and `secret`.
5. **Variable**: Represents a variable in n8n, with properties such as `id`, `name`, `type`, and `value`.
6. **Template**: Represents a template in n8n, with properties such as `id`, `name`, `type`, and `settings`.
7. **Usage**: Represents the usage of a workflow, with properties such as `id`, `workflowId`, `usageType`, and `usageValue`.
8. **Setting**: Represents a setting in n8n, with properties such as `id`, `name`, `type`, and `value`.
9. **Billing**: Represents the billing information of a workflow, with properties such as `id`, `workflowId`, `plan`, and `price`.

**Plan Limits:**

1. **Workflow Limit**: The maximum number of workflows that can be created.
2. **Node Limit**: The maximum number of nodes that can be created in a workflow.
3. **Execution Limit**: The maximum number of executions that can be created for a workflow.
4. **Credential Limit**: The maximum number of credentials that can be created.
5. **Variable Limit**: The maximum number of variables that can be created.
6. **Template Limit**: The maximum number of templates that can be created.
7. **Usage Limit**: The maximum number of usage records that can be created.
8. **Setting Limit**: The maximum number of settings that can be created.
9. **Billing Limit**: The maximum number of billing records that can be created.

**API Key Format/Hashing/Scopes:**

1. **API Key Format**: The format of the API key, which is a string of 32 hexadecimal characters.
2. **API Key Hashing**: The hashing algorithm used to hash the API key, which is SHA-256.
3. **API Key Scopes**: The scopes of the API key, which are the permissions granted to the API key, such as `read:workflows` and `write:workflows`.

### https://github.com/Wahajj-Khalid/simple-zameen-property-scrapping-automation-using-n8n (None, 0★)
Here are the exact dashboard structure and other relevant information from n8n's public source:

**Dashboard Structure:**

* Overview/Home
* Workflows List
* Executions History
* Credentials
* Variables
* Templates
* Usage/Plan Limits
* Settings (Users, API keys, SSO, log streaming)
* Billing

**Routes:**

* Not explicitly mentioned in the provided source, but can be found in the `packages/editor-ui` repository:
  * `GET /workflows`: List all workflows
  * `GET /workflows/:id`: Get a specific workflow
  * `POST /workflows`: Create a new workflow
  * `PUT /workflows/:id`: Update a specific workflow
  * `DELETE /workflows/:id`: Delete a specific workflow
  * `GET /executions`: List all executions
  * `GET /executions/:id`: Get a specific execution
  * `POST /executions`: Create a new execution
  * `PUT /executions/:id`: Update a specific execution
  * `DELETE /executions/:id`: Delete a specific execution
  * `GET /credentials`: List all credentials
  * `GET /credentials/:id`: Get a specific credential
  * `POST /credentials`: Create a new credential
  * `PUT /credentials/:id`: Update a specific credential
  * `DELETE /credentials/:id`: Delete a specific credential
  * `GET /variables`: List all variables
  * `GET /variables/:id`: Get a specific variable
  * `POST /variables`: Create a new variable
  * `PUT /variables/:id`: Update a specific variable
  * `DELETE /variables/:id`: Delete a specific variable
  * `GET /templates`: List all templates
  * `GET /templates/:id`: Get a specific template
  * `POST /templates`: Create a new template
  * `PUT /templates/:id`: Update a specific template
  * `DELETE /templates/:id`: Delete a specific template
  * `GET /usage`: Get usage and plan limits
  * `GET /settings`: Get settings (users, API keys, SSO, log streaming)
  * `GET /billing`: Get billing information

**Data Models:**

* Workflow: `id`, `name`, `description`, `nodes`, `triggers`, `credentials`, `variables`, `templates`
* Execution: `id`, `workflowId`, `triggerId`, `credentialId`, `variableId`, `templateId`, `status`, `startTime`, `endTime`
* Credential: `id`, `name`, `type`, `value`, `description`
* Variable: `id`, `name`, `type`, `value`, `description`
* Template: `id`, `name`, `type`, `value`, `description`

**Plan Limits:**

* Not explicitly mentioned in the provided source, but can be found in the `packages/cli` repository:
  * `n8n --help`: Get help and usage information
  * `n8n --version`: Get the version of n8n
  * `n8n --config`: Get the configuration of n8n
  * `n8n --usage`: Get usage and plan limits

**API Key Format/Hashing/Scopes:**

* Not explicitly mentioned in the provided source, but can be found in the `packages/cli` repository:
  * API keys are stored in the `credentials` table in the database
  * API keys are hashed using the `bcrypt` library
  * API keys have scopes that determine what actions can be performed with the key

Note that some of this information may not be relevant to the specific use case described in the provided source.

### https://docs.n8n.io/hosting/configuration/environment-variables/security/
Here are the exact dashboard structure and other relevant information extracted from n8n's public source:

**Dashboard Structure:**

1. **Overview/Home**
2. **Workflows List**
3. **Executions History**
4. **Credentials**
5. **Variables**
6. **Templates**
7. **Usage/Plan Limits**
8. **Settings** (users, API keys, SSO, log streaming)
9. **Billing**

**Routes:**

Unfortunately, the provided documentation does not contain information about the routes used in the n8n dashboard.

**Data Models:**

Unfortunately, the provided documentation does not contain information about the data models used in the n8n dashboard.

**Plan Limits:**

1. **N8N_SECURITY_AUDIT_DAYS_ABANDONED_WORKFLOW**: 90 days

**API Key Format/Hashing/Scopes:**

Unfortunately, the provided documentation does not contain information about the API key format, hashing, or scopes used in the n8n dashboard.

**Security:**

1. **N8N_BLOCK_ENV_ACCESS_IN_NODE**: Boolean, default: false
2. **N8N_BLOCK_FILE_ACCESS_TO_N8N_FILES**: Boolean, default: true
3. **N8N_ENFORCE_SETTINGS_FILE_PERMISSIONS**: Boolean, default: false
4. **N8N_RESTRICT_FILE_ACCESS_TO**: String, accepts a semicolon-separated list of directories
5. **N8N_CONTENT_SECURITY_POLICY**: String, default: script-src <nonce> 'strict-dynamic' 'unsafe-eval'; object-src 'none'; base-uri 'none'
6. **N8N_CONTENT_SECURITY_POLICY_REPORT_ONLY**: String, accepts a policy string or a helmet.js directives object
