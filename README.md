# Intent-Driven POS Operations: Square API Integration via Claude and MCP

![Status](https://img.shields.io/badge/Status-Proof_of_Concept-success.svg)
![Protocol](https://img.shields.io/badge/Protocol-MCP-orange.svg)
![Integration](https://img.shields.io/badge/Integration-Square_API-lightgrey.svg)
![AI](https://img.shields.io/badge/AI-Claude_3.5_Sonnet-purple.svg)

An experimental Proof of Concept (PoC) bridging the **Square Point of Sale (POS) API** with **Claude Desktop** using the **Model Context Protocol (MCP)**. 

This project explores the shift from traditional UI-driven workflows to intent-driven systems. By mapping natural language requests to structured API calls, this integration allows operators to update catalogs, query locations, and generate sales reports instantly without navigating a dashboard.

---

## 🎯 Executive Summary
Traditional business operations require navigating complex dashboards to perform bulk updates or pull reports. This project replaces those manual clicks with a conversational interface. 

Instead of opening a catalog editor to adjust pricing, a user simply types:
> *"Change all tacos to $15 and drinks to $5"*

Behind the scenes, Claude parses the intent, the MCP server maps it to structured API calls, and the Square APIs execute the bulk updates. Results are validated and returned in seconds.

---

## ⚙️ Architecture & Tech Stack

This prototype utilizes a simplified stack to interact with real-time APIs via secure authentication:

*   **LLM Cognitive Layer:** Claude AI (Sonnet 3.5)
*   **Integration Layer:** Model Context Protocol (MCP) Server
*   **Target System:** Square Developer REST APIs (Catalog, Locations, Orders, Payments)
*   **Authentication:** OAuth 2.0 

```text
[ User Intent ] --> [ Claude AI ] --> [ MCP Server ] --> [ Square REST API ] --> [ Square POS ]
```

---

## 🚀 Key Features Explored

1. **Bulk Menu Updates (Catalog API):** Translating natural language into bulk pricing changes.
2. **Multi-Location Queries (Locations API):** Querying active business locations, verifying timezones, and retrieving Location IDs.
3. **Sales & Reporting (Orders/Payments APIs):** Hooking into sales data to generate formatted executive summaries of daily net sales and order volumes.

---

## 📸 Demo & Visual Evidence

*Note: This prototype was built and tested entirely within a fresh Square Developer sandbox account. No production data, real customers, or active business operations were utilized.*

### 1. Intent-Driven Catalog Updates
Executing a bulk price change across multiple item categories using a single natural language command. The system processes the request and returns the updated menu validation instantly.

![Bulk Price Updates](assets/bulk-price-update.jpg)

### 2. Multi-Location Queries & Reporting
Retrieving active sandbox locations and generating a real-time sales report dashboard directly within the Claude interface.

![Locations and Sales Report](assets/location-sales-report.jpg)

---

## 🧠 Key Takeaways

* **The Shift to Intent-Driven Systems:** We are moving away from UI-driven workflows. Instead of navigating tools, operators can simply tell the system what to do.
* **The Power of MCP:** The Model Context Protocol serves as a highly effective, standardized bridge for securely extending LLM capabilities into external REST APIs.
* **Security Boundaries:** Exposing financial or operational APIs to an LLM requires strict boundary controls, reinforcing the importance of OAuth 2.0 and scoped access when designing AI-driven business tools.
