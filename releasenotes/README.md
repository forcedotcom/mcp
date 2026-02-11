# Salesforce DX MCP Server Release Notes

Here are the new and changed features in recent updates of Salesforce DX MCP Server.

> **NOTE**: The tools marked NON-GA are not yet generally available. To use them, specify the `--allow-non-ga-tools` flag in your DX MCP Server configuration. See the README file in the [Salesforce MCP GitHub repository](https://github.com/salesforcecli/mcp). 

We publish a new stable (that has the `latest` tag) version of Salesforce DX MCP Server on Wednesdays. At the same time we also publish a release candidate (`latest-rc` tag) that contains changes that will likely be in next week's stable release. Merges into `main` are published with the `nightly` tag.

To display the version of Salesforce DX MCP Server currently installed on your computer, run `npx --offline @salesforce/mcp --version` in a terminal or command window.

Report and read about issues [here](https://github.com/forcedotcom/mcp/issues). Join the discussion about new features we're considering [here](https://github.com/forcedotcom/mcp/discussions).

Additional documentation:

- [Salesforce DX MCP Server (Beta)](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_mcp.htm): Contains an overview of the DX MCP server, a quick tutorial to get you started, steps to configure the MCP server, and reference information about the MCP tools.
- [Contribute to Salesforce DX MCP Server](https://github.com/salesforcecli/mcp/blob/main/DEVELOPING.md)

## 0.26.0 (February 13, 2026) [latest]

* NEW: Since the 0.23.3 release, we added these new toolsets and tools.

    * The `code-analysis` toolset is now GA. We also added two new tools to the toolset. See [Use MCP Tools to Analyze Your Code](https://developer.salesforce.com/docs/platform/salesforce-code-analyzer/guide/mcp.html).
        * `list_code_analyzer_rules`: List all available Code Analyzer rules, which enables an LLM to discover which checks are possible and request specific rule executions.
        * `query_code_analyzer_results`: Retrieve results from a previous run's output. Filter by file or severity and paginate through results.

    * The `devops` toolset has these new Non-GA tools. See [DevOps Center MCP Tools](https://help.salesforce.com/s/articleView?id=platform.devops_center_mcp_intro.htm&type=5).
        * `check_devops_center_commit_status` (NON-GA): Check the current status of a work item committed to DevOps Center.
        * `checkout_devops_center_work_item` (NON-GA): Check out the branch associated with a selected work item by name.
        * `commit_devops_center_work_item` (NON-GA): Commit SFDX project changes and register the commit SHA in DevOps Center.
        * `create_devops_center_pull_request` (NON-GA): Commit local changes to a DevOps Center work item’s feature branch.
        * `list_devops_center_projects` (NON-GA): List all DevOps Center projects in a specific org.
        * `list_devops_center_work_items` (NON-GA): List all the work items for a specific  DevOps Center project.
        * `promote_devops_center_work_item` (NON-GA): Promote an approved work item to the next stage in the DevOps Center pipeline.

    * The `lwc-experts` toolset has these new tools. See [Use DX MCP Tools for LWC (Beta)](https://developer.salesforce.com/docs/platform/lwc/guide/mcp-intro.html).
        * `create_lightning_type` (GA): Provide guidance for creating Custom Lightning Types (CLT) for Salesforce applications, Agent actions, Lightning Web Components, and Lightning Platform integrations.
        * `create_lds_graphql_read_query` (GA): Create GraphQL read queries for Lightning Data Service (LDS).
        * `create_lds_graphql_mutation_query` (GA): Provide comprehensive guidance text for creating GraphQL mutation queries.
        * `explore_lds_graphql_schema` (GA): Explore GraphQL schema structure for LDS.
        * `guide_lds_graphql` (GA): Provide LDS GraphQL usage patterns and guidelines.
        * `guide_design_general` (GA): Provide comprehensive Salesforce Lightning Design System (SLDS) guidelines and best practices for Lightning Web Components with accessibility, responsive design, and component usage patterns.
        * `guide_utam_generation` (NON-GA): Provides UTAM Page Object generation guidelines and best practices.

* NEW: The `metadata` toolset now supports the `ignoreConflict` parameter. If specified, conflicts between your project’s local files and your org are ignored. For the `deploy_metadata` tool, local file changes are deployed and overwrite remote changes in the org. For the `retrieve_metadata` tool, remote changes in the org are retrieved and overwrite local files. If not specified, the default parameter value is `false`.    
    
    Example prompt: `Retrieve X metadata from my org and ignore any conflicts between the local project and org.`  
    
    (GitHub Discussion [#24](https://github.com/forcedotcom/mcp/discussions/24), mcp PR [#321](https://github.com/salesforcecli/mcp/pull/321), source-tracking PR [#828](https://github.com/forcedotcom/source-tracking/pull/828))


## 0.23.3 (September 30, 2025)

* NEW: (Beta) We're happy to announce the Beta release of the Salesforce DX MCP Server! This release contains these new features:

    * New toolsets, such as `devops` and `lwc-experts`, with many new tools to help you develop Salesforce application using a variety of features.
    * The new `--tools` flag for enabling a specific tool.   

  Check out the [new documentation](https://developer.salesforce.com/docs/atlas.en-us.sfdx_dev.meta/sfdx_dev/sfdx_dev_mcp.htm) for all the details. 

   > **NOTE**: _Salesforce DX MCP Server is a pilot or beta service that is subject to the Beta Services Terms at [Agreements - Salesforce.com](https://www.salesforce.com/company/legal/) or a written Unified Pilot Agreement if executed by Customer, and applicable terms in the [Product Terms Directory](https://ptd.salesforce.com/). Use of this pilot or beta service is at the Customer's sole discretion._

## 0.17.1 (August 17, 2025)

FIX: Organizational changes and bug fixes.
