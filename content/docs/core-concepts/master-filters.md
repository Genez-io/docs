# Master Filters

**Master Filters** let you slice a single brand's data by product line — so a multi-product company can stay as one brand in Genezio and still see how each line is doing individually.

A master filter is defined as a **set of topics**. When you create master filters and pick one from the picker, every view in Genezio narrows to that filter's topics: dashboards, conversations, insights, citations, share of voice, perceptions, everything.

> **Note:** Master Filters were previously called **Products**. They were renamed to avoid confusion with the products AI mentions in shopping answers — see [Shopping -> Products](../shopping/products.html), which is a different feature entirely.

---

## When to Use Master Filters vs. Separate Brands

Genezio supports two ways to model a multi-product company. Picking the right one matters.

### Use Separate Brands When...

Your products have their own brand presence in answer engines:

* the products are well-known to answer engines **by their product names**
* customers and buyers refer to them directly by product name
* each product has its own distinct competitors

In this case, model each product as its own brand. Microsoft Word, Microsoft Excel, and Microsoft Teams are different brands to an answer engine — each has its own competitors (Google Docs, Google Sheets, Slack), its own buyer personas, and its own visibility story.

See [Brands -> Multi-Product Companies](brands.html#multi-product-companies).

### Use Master Filters When...

Your **brand** is strong but your individual product lines don't carry their own brand recognition:

* customers know the company name, not the product-line names
* answer engines describe the lines as offerings of the parent brand, not as standalone names
* lines often share competitors, or the competitive set isn't sharply different per line
* you want a single source of truth at the brand level, with product-line slices on top

In this case, keep everything at the brand level and define **Master Filters** to filter the data per product line.

### Quick Decision

| If... | Use |
| --- | --- |
| Each product has its own brand recognition and distinct competitors | **Separate brands** |
| The parent brand is strong; product lines don't have independent brand presence | **Master Filters** (within one brand) |
| You're not sure | Start with one brand + Master Filters. Splitting later is easy; merging later is harder. |

---

## How Master Filters Work

A master filter is a **named set of topics**. That's the whole definition.

* Topics can be **shared across master filters**. The topic *"Customer support best practices"* might belong to your Sales filter and your Service filter at the same time.
* Topics that aren't tied to any master filter still exist on the brand — they just don't appear when a filter is active.
* Master filters are managed at the brand level. Each brand has its own list.

---

## Where to Set Them Up

Master Filters are defined in **Settings**.

You give each one a name and pick the topics that belong to it. Once at least one master filter is defined, a **picker** appears in the main header — letting you switch the entire view between filters (or back to the unfiltered default).

---

## Filtering Your Reports

Filters live in the **report header** and carry across screens — a selection you make on one page follows you to the next, so you don't have to re-apply it everywhere.

Two filters are available there:

* **Master filter** — appears once at least one master filter is defined for the brand. Picking one narrows every view to that filter's topics.
* **Persona** — appears when the brand's topics span **two or more personas**. Picking one narrows the view to that persona's data. See [Personas](personas.html).

If you haven't defined any master filters, that dropdown stays hidden and Genezio behaves as it always has.

When you pick a master filter:

* **dashboards** show metrics for the topics in that filter
* **conversations** filter to that filter's topics
* **insights** are scoped to that filter's data
* **citations**, **SOV**, **perceptions**, **competitors** — every view narrows accordingly

The default view is **unfiltered** — the brand-wide picture, untouched by any master filter. The picker is an optional lens you opt into.

---

## A Typical Setup

A consumer-electronics company, for example, with three product lines:

1. The company creates one brand for itself.
2. In Settings, it defines three master filters: *Headphones*, *Speakers*, *Wearables*.
3. Topics that apply to all three (e.g., *"Brand reputation"*) are attached to all three — or left at the brand level if leadership cares about them company-wide.
4. Topics specific to one line (e.g., *"Noise-cancelling headphones for travel"*) belong only to *Headphones*.
5. The picker appears in the header. The marketing manager for *Headphones* uses it daily to see just their slice; the CMO leaves it unfiltered for the company-wide view.

---

## Master Filters and the Rest of the Platform

Because the picker filters at the data level, Master Filters work cleanly with the rest of Genezio:

* the [Geo Assistant](../geo-assistant/geo-assistant.html) respects the current master filter when answering questions
* [Insights](../insights/actionable-insights.html) and [Share of Voice](../insights/share-of-voice.html) reflect the active filter
* exporting reports for stakeholder reviews picks up the filter context
* [Topic Tags](../getting-started/topic-tags.html) still work independently — you can have *Headphones* (master filter) and *Pricing* (tag) on the same topic

---

## Not the Same as Shopping Products

Master Filters group **topics** to slice your own reporting. They are a reporting lens you configure.

The [Shopping](../shopping/product-visibility.html) section deals with something different: the **individual products answer engines actually mention** in shopping answers, which Genezio detects automatically from conversations. You don't configure those — they're discovered.

---

## Related Pages

* [Brands](brands.html)
* [Topic Tags](../getting-started/topic-tags.html)
* [Competitors](competitors.html)
* [Shopping -> Product Visibility](../shopping/product-visibility.html)
