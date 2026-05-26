# VIVIA PROPERTY OS v3

Multi-tenant rental operations system connecting:
Fillout → HubSpot → Stripe → TurboTenant Live Listings → Zite Database → Twilio SMS → Cal.com Scheduling

---

## 🌐 Core Domain

- Domain: VIVIAPROPERTY.COM
- Platform: https://turbo-tenant.zite.so/employees
- System Type: Rental Operations OS + Employee Onboarding + Listing Syndication

---

## 🧠 System Architecture


Fillout Intake
↓
HubSpot CRM (Portal 147969685)
↓
Stripe Billing + Employee Activation
↓
Zite Database (Employees + Properties + Conversations)
↓
TurboTenant Live Listing Sync
↓
Marketing Syndication (Zillow / Zumper / External)
↓
Twilio + WhatsApp + SMS Alerts
↓
Cal.com Training + Onboarding Session


---

## 🔁 Unified Redirect Flow (Fillout → HubSpot → Stripe → TurboTenant)


fillout_session
→ hubspot_contact
→ stripe_customer
→ stripe_checkout_session
→ turbotenant_live_listing
→ zite_employee_activation
→ marketing_syndication


---

## 🔑 20-Key Reusable Redirect Parameters


email={{email}}
phone={{phone}}
first_name={{first_name}}
last_name={{last_name}}
city={{city}}
state={{state}}
country={{country}}
zip={{zip}}
role={{role}}
employee_id={{employee_id}}
client_reference_id={{client_reference_id}}
hubspot_deal_id={{hubspot_deal_id}}
stripe_customer_id={{stripe_customer_id}}
checkout_session_id={{CHECKOUT_SESSION_ID}}
property_id={{property_id}}
listing_id={{listing_id}}
signup_source={{signup_source}}
utm_source={{utm_source}}
utm_campaign={{utm_campaign}}
utm_medium={{utm_medium}}


---

## 💳 Stripe Employee Activation Link


https://billing.stripe.com/p/login/test_8x200j4nogd5em60pagYU00?client_reference_id={{client_reference_id}}&email={{email}}&role=remote_property_manager


---

## 🏠 TurboTenant Live Listing Embed

```html
<html>
<body>
<iframe 
  style="border:none;"
  src="https://rental.turbotenant.com/embedpropertylist.html#/PROPERTY_ID_PLACEHOLDER"
  height="1240"
  width="100%">
</iframe>
</body>
</html>
📡 Webhook Routing System
TurboTenant
https://your-n8n.com/webhook/turbotenant-lead
Twilio SMS Inbound
https://your-n8n.com/webhook/twilio-inbound
HubSpot Lead Sync
https://your-n8n.com/webhook/hubspot-lead
🔐 API Authentication Headers
Zite API
Authorization: Bearer YOUR_ZITE_KEY
HubSpot API (EU Portal 147969685)
Authorization: Bearer YOUR_HUBSPOT_TOKEN
Twilio
Account SID + Auth Token (via n8n node)
🧑‍💼 Employee Onboarding Flow (V2)
Step 1 — Fillout Intake
Collect employee profile
Assign role (Remote Property Manager)
Step 2 — HubSpot Creation
Contact + Deal created
Pipeline Stage = "Onboarding"
Step 3 — Stripe Activation
Customer created
Checkout session generated
Employee redirected to:
Stripe Billing Portal
Step 4 — TurboTenant Assignment
Property assigned
Listing synced
Status = Live
Step 5 — Zite Employee Record
Employee ID generated
Conversation + task routing activated
Step 6 — Cal.com Training
https://cal.com/turbo-rentals/tenant-landlord-services
📊 Service Offer Options
Rental Management
Payment Processing
Scheduling (Tours + Onboarding)
Employee Onboarding System
📲 SMS Alert System
Publish Code Format
SMS Logged — Publish Code: 676788
Status: Sent → Queued → Delivered
🧾 Custom Event Payload (Onboarding JSON)
{
  "workflow_version": "vivia-rentals-v2",
  "environment": "production",
  "automation": {
    "stripe_redirect": true,
    "hubspot_sync": true,
    "turbotenant_sync": true,
    "sms_verification": true
  },
  "integrations": {
    "stripe": "bpc_1TaPNUDI5ZfGRQdNl8QFpcs7",
    "hubspot": "147969685",
    "turbotenant": "active",
    "zite": "enabled"
  }
}
🔄 Multi-Tenant Routing Rules
Condition	Action
Renter	Tour scheduling + SMS invite
Landlord	Listing onboarding
Employee	Stripe activation + training
Lead	HubSpot + Zite sync
🚀 Final System Behavior
All leads are captured instantly
Employees are auto-assigned
Stripe activates onboarding access
TurboTenant listings go live automatically
Twilio sends SMS confirmations
HubSpot tracks full lifecycle
🏁 Production Status
Environment: Production Ready
Version: v3
Deployment: Active
Domains: VIVIAPROPERTY.COM
