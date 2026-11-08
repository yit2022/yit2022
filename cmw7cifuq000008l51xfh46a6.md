---
title: "Your eTIMS Problem Is Not the Invoice. It Is the Item Master."
datePublished: 2026-11-08T04:42:03.790Z
cuid: cmw7cifuq000008l51xfh46a6
slug: item-master-data-checklist-food-processors-kenya
canonical: https://factoraerp.com/en/blog/item-master-data-checklist-food-processors-kenya

---

*By Isaac Muthui, CEO, Tamalaki Business Network Ltd. Originally published at [factoraerp.com](https://factoraerp.com/en/blog/item-master-data-checklist-food-processors-kenya).*

Most stock problems in a food factory look like counting problems. Many of them are naming problems.

The same 50 kg bag of sugar is "Sugar 50kg" on the purchase order, "SUGAR-BRN" in stores, "Raw sugar" on the recipe and "Sugar (local)" on the supplier's invoice. A 500 ml yoghurt is sold as a single, a 12-pack and a promotional twin pack, but the system only knows one of them. Maize flour is bought in tonnes, issued in kilograms and sold in 2 kg packets, and nobody wrote down the conversion. When the month-end variance appears, the team recounts the warehouse. The warehouse was never the problem. The item master was.

That matters more now. Kenya Revenue Authority has told businesses invoicing through TIMS/eTIMS to keep accurate, up-to-date stock records aligned with the invoices they issue. Reporting in The Star on 2 October 2026 described manufacturers preparing for a January 2027 stock-tracking rollout. And KRA's own technical specification for system-to-system integration makes one thing very clear: every invoiced and stocked item carries a structured code, a product type, a packaging unit, a quantity unit and a tax type. If your item list is a spreadsheet called "Items_final_v3", that is where your eTIMS stock story will break first.

This item master data checklist for food processors is written for dairies, millers, juice and beverage plants, bakeries, meat and ready-to-eat processors, snack makers and other Kenyan and East African food and agro factories. It is deliberately different from earlier guides. Our [stock count reconciliation checklist](https://factoraerp.com/en/blog/stock-count-reconciliation-checklist-food-factories-kenya) and [year-end stock take checklist](https://factoraerp.com/en/blog/year-end-stock-take-checklist-food-processors-kenya) cover counting. Our [eTIMS guide for food and agro manufacturers](https://factoraerp.com/en/blog/etims-for-food-agro-manufacturers-kenya) covers invoicing. This article is about the data underneath both: how you name, code, measure, classify and control the items you buy, make, hold and sell.

It does not replace your accountant, tax adviser or eTIMS integrator. It sets out twelve practical checks so that one physical item has one identity — in stores, on the recipe, on the invoice and in the stock record.

## What the guidance and the specification actually say

**KRA stock management for electronic invoicing.** On its [stock management functionality page](https://www.kra.go.ke/business/etims-electronic-tax-invoice-management-system/learn-about-etims/stock-management-functionality-for-electronic-invoicing), KRA informs taxpayers that they must maintain accurate and up-to-date stock records while invoicing through TIMS/eTIMS, in accordance with section 23A(2)(b) of the Tax Procedures Act, 2015. The records should cover stock received, purchased, sold, transferred, returned, adjusted or otherwise disposed of, and should align with the transactions invoiced through TIMS/eTIMS.

**System-to-system integration.** KRA's [eTIMS system-to-system integration page](https://www.kra.go.ke/business/etims-electronic-tax-invoice-management-system/learn-about-etims/etims-system-to-system-integration) describes two options for connecting an invoicing or ERP system: the Online Sales Control Unit (OSCU), for taxpayers whose invoicing is always online, and the Virtual Sales Control Unit (VSCU), suited to bulk invoicing where the system is not always online.

**What an item looks like to eTIMS.** KRA's published [OSCU requirements and communication protocols (version 2.0)](https://www.kra.go.ke/images/publications/OSCU_Specification_Document_v2.0.pdf) define the item record an integrated system saves. Required fields include an item classification code, a unique item code, an item type, the item name, the country of origin, a packaging unit code, a quantity unit code, a taxation type and a default unit price. Optional fields include a barcode and a batch number. The specification says the item code is mandatory and must be unique, and shows how it is built — for example, `KE2NTBA0000012` is country of origin (KE), product type (2, finished product), packaging unit (NT), quantity unit (BA) and an incrementing sequence. The product type code list has three values: 1 raw material, 2 finished product, 3 service without stock. The taxation type list in the same document runs A (exempt), B (16%), C (0%), D (non-VAT) and E (8%).

**Stock movements have types too.** The same specification lists stock in/out types, including incoming import, purchase, return, stock movement, processing and adjustment, and outgoing sale, return, stock movement, processing, discarding and adjustment. For a food processor, "processing" in and out is where raw materials become finished goods — which is why the recipe and the item master have to agree.

**Manufacturers' open questions.** [The Star (2 October 2026)](https://www.the-star.co.ke/business/markets/2026-10-02-manufacturers-seek-clarity-as-kra-plans-etims-stock-tracking-rollout) reported that the Kenya Association of Manufacturers has asked for clarity on how stock functionality will sit beside existing ERP systems and how the conversion of raw materials into finished goods — including wastage, by-products, damaged goods and samples — will be captured. [People Daily (10 October 2026)](https://peopledaily.digital/insights/beyond-etims-invoices-why-kenyan-businesses-must-account-for-every-unit-of-stock) added a point that is really about master data: multi-branch businesses need consistent product codes and transfer records so goods do not appear twice or vanish.

Treat the specification as KRA's technical reference for integrators, not as tax advice. Which tax type applies to which product is a question for your tax adviser.

## Why item masters go wrong in food plants

Item masters rarely fail on day one. They decay.

A new supplier arrives and stores creates a new item instead of linking the existing one. A pack size changes and someone edits the old item's description rather than creating a new SKU, so last year's sales and this year's sales now share a name but not a weight. Promotional bundles are sold under the single-unit code. Units of measure are implied ("bags") rather than defined. By-products such as bran, whey or pulp are not items at all, so they are sold off-system. Tax types are copied from the last item created. Nobody owns the list, so everybody edits it.

None of that is visible on a normal day. It all becomes visible when stock movements and invoices are expected to tell one story.

## The 12-point item master data checklist for food processors

### Govern the list

**1. Name one owner and one change process.**  
Decide who can create, change and retire items — typically one person in finance or supply chain, with a named backup. Requests come from stores, production, QA or sales with a reason. No one creates items "just for today". A shared spreadsheet that anyone can edit is not an item master.

**2. Write a naming convention and apply it to every item.**  
For example: product or material, variant, net quantity, pack format — "Maize flour, sifted, 2 kg, packet". Names must be readable on a pick list and on an invoice. Keep a separate field for the supplier's name for the same material, rather than renaming your item to match each supplier. The KRA specification provides for a supplier item code and name on purchase records for exactly that reason.

**3. Clean duplicates before you integrate.**  
Export the item list, sort by name and by barcode, and look for the same physical item under two or more codes. Merge or block the duplicates, move their history to the surviving code where your system allows, and record what you merged. Integrating a duplicate-ridden list simply sends the duplicates to eTIMS faster.

### Define what each item is

**4. Classify every item by type: raw material, finished product, or service.**  
Ingredients, packaging, consumables you track, semi-finished goods, finished goods and by-products all need a type decided on purpose. The eTIMS product type list distinguishes raw material, finished product and service without stock. Decide internally how you treat packaging, intermediates and by-products, and document the rule so it is applied the same way every time.

**5. Map each item to the right classification code.**  
eTIMS integrations retrieve standard item classification codes from KRA's system, and each saved item carries one. Map your items to codes deliberately with your integrator — not by picking the first match. Record the mapping in the item master so a new joiner can see why sugar, maize, milk powder and PET preforms sit where they do.

**6. Define units of measure and conversions explicitly.**  
For every item, record the base unit (kg, litre, piece), the purchase unit, the issue unit, the sales unit, and the conversion factors between them. Map your units to the eTIMS packaging unit and quantity unit codes — the specification's lists include, for instance, bag, carton, kilogram and litre. "Bag" without a weight is not a unit. Unit confusion is one of the commonest causes of variances that disappear on recount, as in our [stock count reconciliation checklist](https://factoraerp.com/en/blog/stock-count-reconciliation-checklist-food-factories-kenya).

**7. Give every pack size and bundle its own SKU.**  
A 500 g and a 1 kg packet are different items. A 12-pack shrink-wrapped tray is a different item from the single unit, unless your system handles it as a defined packaging level with a fixed conversion. If you change the net quantity of a product, create a new item rather than editing the old one. Our [net quantity and pack weight checks](https://factoraerp.com/en/blog/net-quantity-pack-weight-checks-food-factories-kenya) and [label control checklist](https://factoraerp.com/en/blog/label-control-checklist-food-manufacturers-kenya) depend on the SKU meaning one declared quantity.

### Connect the item to tax, recipes and lots

**8. Set the tax type per item with your tax adviser — and lock the field.**  
The eTIMS item record carries a taxation type. Decide each item's type with your tax adviser, record the basis, and restrict who can change it. Copying the tax type from "the last item we created" is how a zero-rated or exempt product ends up invoiced at the wrong rate, or the reverse.

**9. Make recipes use the same item codes as stores and purchasing.**  
Every ingredient and packaging line on a bill of materials should point to the item that stores actually receive and issue — not a recipe-only description. Declare by-products, co-products and waste as items where they have value or must be disposed of, so processing out (raw materials consumed) and processing in (finished goods and by-products made) can be reconciled. This is the conversion question KAM has raised. See our [batch costing and yield tracking guide](https://factoraerp.com/en/blog/batch-costing-yield-tracking-agro-processors-kenya).

**10. Decide which items are lot-controlled, and with which dates.**  
Food-contact ingredients, packaging and finished goods usually need lot or batch tracking for traceability and recall; some consumables do not. Record per item whether lots, expiry or best-before dates and shelf-life rules apply, and keep lot codes consistent with what you print. Note that the specification's batch number field on the item record is short (up to 10 characters in version 2.0), so agree your lot code format with your integrator early. See [FEFO and batch expiry tracking](https://factoraerp.com/en/blog/reduce-expiry-spoilage-losses-fefo-batch-expiry-tracking) and [how to run a mock recall](https://factoraerp.com/en/blog/how-to-run-a-mock-recall-food-traceability-kenya).

### Keep it true over time

**11. Use consistent codes across every branch, depot and warehouse.**  
One item, one code, everywhere. Depots must not create local versions of central items. Transfers between sites should move stock of the same item code out of one location and into another. People Daily's warning on multi-branch businesses is, in practice, a master data rule.

**12. Retire, don't delete — and review the list every month.**  
Items you stop buying or selling should be blocked or marked unused, not deleted, so history, stock and invoices still resolve. The eTIMS item record includes a used/unused flag for the same reason. Once a month, review new items created, items changed, items with stock but no movement, items with movement but no recipe or price, and any item whose tax type or units changed. Keep the change log: master data changes are part of the records behind your stock and invoices, and section 23 of the [Tax Procedures Act, 2015](https://new.kenyalaw.org/akn/ke/act/2015/29) sets a general five-year retention period for documents required under a tax law.

## A simple item master template

| Field | What to record |
|---|---|
| Internal item code | Unique, never reused |
| Item name | Per naming convention (product, variant, net quantity, pack) |
| Item type | Raw material / finished product / service; internal sub-type (packaging, intermediate, by-product) |
| eTIMS classification code | Mapped with integrator; basis noted |
| eTIMS item code | As generated for your integration; unique |
| Origin | Country of origin |
| Units | Base, purchase, issue and sales units; conversion factors |
| eTIMS units | Packaging unit code; quantity unit code |
| Tax type | Agreed with tax adviser; field locked |
| Barcode | Where used; one barcode per SKU |
| Lot control | Yes/no; expiry or best-before; shelf-life rule |
| Recipe links | BOMs using the item; by-product / waste declared |
| Supplier links | Supplier item codes and names |
| Status | Active / blocked / unused; date and approver |
| Change log | Who changed what, when and why |

If two people in your plant would give the same product two different item codes, your eTIMS stock record will too.

## An illustration

*This is an illustrative example, not a real case.* A maize miller buys grain in tonnes, issues it to the mill in kilograms and sells flour in 1 kg and 2 kg packets and 24 kg bales. Over three years the item list grows to four codes for the same 2 kg packet — one per depot and one from a promotion. Bran is sold for cash at the gate but is not an item. Two packets are set up with a different tax type from the others because they were copied from an old item. The 24 kg bale has no item of its own, so each bale is invoiced as twelve 2 kg packets.

Every month the stock report shows large swings: depots appear short of the 2 kg packet while head office is long, flour output never reconciles to grain consumed, and nobody can tell bale stock or bale sales apart from loose packets. A recount changes nothing. Under KRA's stock-management expectation — stock received, processed, sold, transferred and adjusted, aligned with invoices — that business would struggle to explain any single month. The fix is not another count. It is checks 2, 3, 6, 7, 8, 9 and 11.

## How FactoraERP helps

FactoraERP keeps one item master for purchasing, stores, production, QA and sales, with item types, units of measure and conversions, lot and expiry control, and status (active or blocked) on each item. Recipes reference the same items stores receive and issue, and can declare primary product, co-product, by-product or waste, so material consumed and output produced can be reconciled. Stock is held by item, lot, location and status, and receipts, issues, output, transfers and dispatches are recorded as they happen. See [factoraerp.com](https://factoraerp.com).

## Free download: eTIMS readiness checklist for factories

Kenyan manufacturers increasingly need their item lists, stock records and invoices to tell one consistent story. If you want a free **eTIMS readiness checklist for factories**, sign up for the FactoraERP Insights newsletter at [https://isaacmuthui.substack.com](https://isaacmuthui.substack.com). You will get practical operations notes for food and agro manufacturers. No spam; unsubscribe anytime. For background, see our guide to [eTIMS for food and agro manufacturers](https://factoraerp.com/en/blog/etims-for-food-agro-manufacturers-kenya) and our [month-end close checklist](https://factoraerp.com/en/blog/month-end-close-checklist-food-processors-kenya).

## FAQ

**What is item master data in a food factory?**  
It is the controlled list of every material, packaging item, intermediate, finished product and by-product you buy, make, hold or sell, with its code, name, type, units and conversions, tax type, lot rules, recipe and supplier links and status.

**Why does item master data matter for eTIMS?**  
KRA expects stock records to align with TIMS/eTIMS invoices. In KRA's OSCU specification, each item saved by an integrated system carries a classification code, a unique item code, a product type, packaging and quantity unit codes and a taxation type. Duplicate, mis-typed or badly measured items make that alignment hard.

**What product types does eTIMS use?**  
The OSCU specification (version 2.0) lists three product types: raw material, finished product, and service without stock. Agree with your integrator and adviser how packaging, intermediates and by-products are treated.

**Should a new pack size get a new item code?**  
Yes. A different net quantity or pack format is a different item. Editing an existing item's size mixes history and breaks stock and sales comparisons.

**How do by-products like bran or whey fit in?**  
Where they have value or must be disposed of, set them up as items and declare them on the recipe, so production output and stock movements account for them. KAM has asked KRA for clarity on how wastage and by-products will be captured; confirm current guidance.

**Who should own the item master?**  
One named owner, usually in finance or supply chain, with a documented request and approval process. Stores, production, QA and sales request changes; they do not create items freely.

**Can a small plant manage its item master in a spreadsheet?**  
It can start there if one person owns it, codes are unique, units and conversions are written down, duplicates are removed and changes are logged. Once you have several sites, many SKUs, lot control or an eTIMS integration, a system with controlled fields and history is safer.

---

*Isaac Muthui, CEO, Tamalaki Business Network Ltd*