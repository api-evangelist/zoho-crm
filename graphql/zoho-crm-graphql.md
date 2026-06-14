# Zoho CRM GraphQL Schema

## Overview

This is a conceptual GraphQL schema for Zoho CRM, derived from the Zoho CRM REST API v8. Zoho CRM is an AI-powered sales and customer relationship management platform that helps businesses manage leads, contacts, accounts, deals, and customer engagement across multiple channels. The schema models the full breadth of the Zoho CRM data model including CRM records, pipeline management, activity tracking, commerce objects, support, automation, analytics, and organizational settings.

The authoritative Zoho CRM API documentation is available at:
- REST API v8: https://www.zoho.com/crm/developer/docs/api/v8/
- Developer Portal: https://www.zoho.com/crm/developer/
- GitHub Organization: https://github.com/zoho

## Schema Design

The schema is organized into the following functional areas:

### Core CRM Records

The primary objects that drive sales and relationship management:

- **Lead** — Prospective customers who have expressed interest. Leads can be converted to Contacts, Accounts, and Deals. Includes lead source, status, company information, and conversion tracking.
- **Contact** — Individual people associated with accounts and deals. Tracks communication history, mailing and other addresses, and links to the associated Account.
- **Account** — Companies or organizations. Supports parent-child hierarchies, billing and shipping addresses, and links to all associated Contacts, Deals, and Cases.
- **Deal** — Sales opportunities tracked through a pipeline. Carries amount, closing date, stage, probability, and expected revenue.

### Pipeline Management

- **Stage** — A named phase within a sales pipeline, carrying probability and forecast category.
- **Pipeline** — An ordered collection of Stages that Deals progress through.

### Activities

CRM activities represent interactions and scheduled work items:

- **Activity** — Abstract union of Task, Event, Call, and Email.
- **Task** — Discrete to-do items with due dates, priority, and status.
- **Event** — Calendar events with start/end times, participants, and reminders.
- **Call** — Logged phone calls with duration and outcome.
- **Note** — Free-text notes attached to any CRM record.

### Modules and Fields

Zoho CRM's module system allows for customization of the data model:

- **Module** — A data entity in Zoho CRM (Leads, Contacts, Accounts, etc.) with metadata about available operations and field definitions.
- **ModuleField** — A field definition within a Module, including data type, validation rules, and pick list values.
- **CustomView** — Saved filter and column configurations for any Module.

### Segmentation and Campaigns

- **Segment** — A defined subset of CRM records matching specified criteria, used for targeting.
- **Campaign** — A marketing campaign tracking budget, ROI, start/end dates, and associated members.
- **CampaignMember** — Association between a Campaign and a Lead or Contact with membership status.

### Email and Templates

- **Email** — Sent and received email messages tracked against CRM records, with open and click tracking.
- **EmailTemplate** — Reusable email templates that can include attachments and merge fields.
- **Template** — General-purpose templates covering email, inventory documents, and mail merge.

### Social Media

- **SocialMedia** — Social media profile associations (Twitter, Facebook, LinkedIn, Instagram, YouTube) linked to Contacts and Leads.

### Documents and Attachments

- **Document** — Files stored in Zoho CRM's document library.
- **Attachment** — File attachments linked to any CRM record.

### Commerce Objects

Full order management and inventory tracking:

- **Product** — Items for sale with pricing, tax, and inventory information.
- **Price / PriceBook** — Pricing structures and books supporting multi-currency scenarios.
- **Tax** — Tax rates applied to line items on inventory documents.
- **Invoice** — Customer billing documents with line items and payment terms.
- **SalesOrder** — Confirmed orders generated from Quotes.
- **PurchaseOrder** — Orders placed with Vendors for Products.
- **Quote** — Sales proposals including line items, discounts, and expiry dates.
- **Vendor** — Supplier companies from whom Products are sourced.
- **LineItem** — Individual line on a commerce document (Invoice, SalesOrder, PurchaseOrder, Quote) linking a Product with quantity, price, and applied taxes.

### Support

- **Case** — Customer support tickets linked to Accounts, Contacts, and Products.
- **Solution** — Knowledge base articles that resolve Cases.
- **PortalInvite** — Invitations sent to Contacts to access the self-service customer portal.

### Users, Roles, and Security

- **User** — Zoho CRM users with language, locale, and formatting preferences.
- **Role** — Organizational roles controlling record visibility through role hierarchies.
- **UserRole** — Assignment of a Role to a User.
- **Profile** — Permission sets controlling which modules and operations a User can access.
- **Permission** — A granular capability (create, read, update, delete, import, export, approve, convert, share, print) scoped to a Module.
- **Group** — Collections of Users (static, dynamic, or territory-based) for bulk operations and sharing.
- **GroupMember** — A User or Role assigned to a Group.

### Territories

- **Territory** — A defined sales territory with assignment rules for Accounts.
- **TerritoryManager** — A User assigned as manager or member of a Territory.

### Automation

- **Rule** — Workflow rules that fire actions based on triggers and criteria.
- **AutomationRule** — Advanced workflow automation with time-based and field-change triggers.
- **BlueprintProcess** — Structured sales or support processes with defined stage transitions, required fields, and validation.
- **BlueprintStage** — A named stage within a Blueprint process.
- **BlueprintTransition** — A permitted movement between Blueprint stages, with conditions and required fields.
- **Approval** — A pending approval request for a CRM record, tracked through request and decision states.

### Settings and Configuration

- **OrganizationSettings** — Company-wide settings including name, address, currency, time zone, and locale.
- **CurrencyList** — Supported currencies with exchange rates and formatting.
- **OAuthToken** — OAuth 2.0 access tokens for API authentication.
- **APIKey** — API keys used for server-to-server integrations.
- **AccountSettings** — Per-user preferences for currency, language, date/time formatting, and notifications.
- **Variable** — Custom variables (text, number, date, boolean, JSON) used in automation and functions.
- **CustomView** — Saved record views with filters, field selections, and sort configuration.

### Analytics

- **AnalyticsReport** — Tabular, summary, matrix, or chart reports aggregating CRM data.
- **ReportField** — A field included in a report with optional aggregation function.
- **Dashboard** — A collection of DashboardWidgets providing an at-a-glance overview.
- **DashboardWidget** — A visualization component (bar chart, line chart, pie chart, funnel, scorecard, table, heat map) embedded in a Dashboard.

### Webhooks and Notifications

- **Webhook** — A registered endpoint that receives HTTP callbacks when CRM record events occur.
- **WebhookEvent** — A specific module-and-operation combination subscribed to on a Webhook.
- **Notification** — In-app notifications for task reminders, event reminders, approvals, record assignments, and mentions.

## Type Count

The schema defines the following named GraphQL types:

| Category | Named Types |
|---|---|
| Core CRM Records | Lead, Contact, Account, Deal |
| Pipeline | Stage, Pipeline |
| Activities | Activity, ActivityType, Task, Event, EventParticipant, Call, Note |
| Modules | Module, ModuleField, PickListValue, PickListValueMap |
| Segmentation | Segment, Campaign, CampaignMember |
| Email | Email, EmailTemplate, Template, TemplateType |
| Social | SocialMedia, SocialMediaType |
| Documents | Document, Attachment |
| Commerce | Product, Price, PriceBook, Tax, Invoice, LineItem, SalesOrder, PurchaseOrder, Quote, Vendor |
| Support | Case, Solution, PortalInvite |
| Users & Security | User, Role, UserRole, Profile, Permission, PermissionAction, Group, GroupType, GroupMember |
| Territories | Territory, TerritoryManager, TerritoryManagerRole |
| Automation | Rule, RuleAction, RuleActionType, AutomationRule, AutomationTrigger, BlueprintProcess, BlueprintStage, BlueprintTransition, Approval, ApprovalStatus |
| Settings | OrganizationSettings, CurrencyList, OAuthToken, APIKey, AccountSettings, Variable, VariableType, CustomView, SortOrder |
| Analytics | AnalyticsReport, ReportType, ReportField, AggregateFunction, DashboardWidget, Dashboard, WidgetType |
| Webhooks | Webhook, HTTPMethod, WebhookEvent, WebhookEventType, Notification, NotificationType |
| Root | Query, Mutation, Subscription |
| Scalars | DateTime, JSON, Upload |
| Unions | ActivityRelatable, NoteRelatable, EmailRelatable, AttachmentRelatable |

**Total named types: 80+**

## Usage Notes

This schema is a conceptual representation of the Zoho CRM data model translated into GraphQL SDL. Zoho CRM does not currently offer a native GraphQL API endpoint. This schema serves as:

1. A reference for teams building GraphQL wrappers or BFF (Backend for Frontend) layers over the Zoho CRM REST API.
2. A data modeling reference for integrations mapping third-party systems to Zoho CRM concepts.
3. A foundation for tooling that generates resolvers, mock servers, or type-safe client code targeting the Zoho CRM REST API.

The REST API base URLs are `https://www.zohoapis.com/crm/v8` (standard) with regional variants for EU, AU, IN, JP, and CN data centers. All requests require OAuth 2.0 Bearer tokens obtained via the Zoho Accounts server.
