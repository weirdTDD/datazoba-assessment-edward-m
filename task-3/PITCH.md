# Story Pitch — Task 03

---

## The Dataset

**Source:** World Bank Open Data — *Remittance Inflows to GDP (%) · Sub-Saharan Africa · 2000–2023*  
**URL:** https://data.worldbank.org/indicator/BX.TRF.PWKR.DT.GD.ZS  
**Supplementary:** KNOMAD Remittance Data (Global Knowledge Partnership on Migration and Development)  
**Coverage:** 48 Sub-Saharan African countries · annual figures · percentage of GDP and USD totals

---

## The Story

In 2023, Sub-Saharan Africa received an estimated **$54 billion in remittances** — more than the combined total of foreign direct investment and official development aid flowing into the region.

That number alone is striking. But the real story is in the *shape* of it.

For countries like Gambia, Lesotho, and Comoros, remittances don't just supplement the economy — they *are* the economy, accounting for between 20% and 35% of GDP in some years. These are not footnotes in a development report. They are the reason families eat, children stay in school, and small businesses survive dry seasons.

And yet the dominant conversation about African economic development almost never starts here. It starts with aid. It starts with FDI. It starts with debt. The money that Africans in the diaspora wire home every month — quietly, consistently, often at punishing transfer fees — is treated as a footnote.

The tension I want to tell: **remittances are the most reliable financial lifeline in Sub-Saharan Africa, and almost nobody talks about them that way.**

There is a second layer. The data shows a sharp divergence after 2020. In West Africa, remittance volumes *grew* during the COVID years — diaspora communities rallied to support families through lockdowns. In East Africa, growth was uneven. In Southern Africa, some countries saw declines as migrant workers in South Africa lost informal employment. The same global crisis produced three completely different stories on the same continent.

That divergence is the story I want to build.

---

## How I Would Visualise It

**Primary chart: A small-multiples area chart**  
One panel per country (or per region), showing remittance inflows as % of GDP over 2000–2023. Arranged from highest to lowest remittance dependency. This lets a reader scan across the continent and immediately see which countries are structurally reliant on diaspora income — and which have diversified away from it.

The visual metaphor I'm drawn to: the area under each curve as a kind of *breathing* — it expands and contracts with global conditions (the 2008 crash, COVID, the 2022 cost-of-living squeeze). You'd see the continent inhale and exhale together, except it doesn't — and that's the story.

**Overlay: A dot annotation layer**  
Mark key global events — 2008 financial crisis, 2014 oil price crash, 2020 COVID lockdowns, 2022 inflation surge — as thin vertical lines across all panels. This lets readers see how diaspora giving responds to external shocks, and whether it *absorbs* them or amplifies them.

**Interaction: Click a country panel to expand it**  
On click, expand to a full-width view showing: USD total (not just % of GDP), the top three source corridors where known (e.g. Nigeria ← United States, United Kingdom, Canada), and the average transfer fee for that corridor. The fee data is from the World Bank's Remittance Prices Worldwide database — and it is quietly devastating. Sending $200 to Sub-Saharan Africa costs an average of 8.5% in fees, compared to 5.4% globally. That is money leaving the diaspora twice.

**Tool choice: D3.js with Svelte**  
Small-multiples at this scale need precise layout control that a charting library won't give cleanly. D3 for the geometry, Svelte for state management on the expand/collapse interaction.

---

## Who Should Care — And Why It Matters

**Policymakers** should care because the data makes a direct argument: transfer fee regulation has a larger immediate impact on household income in remittance-dependent economies than most aid programs. The G20 set a target of 3% average transfer fees in 2011. In 2023, the Sub-Saharan Africa corridor average is still nearly triple that.

**Diaspora communities** should care because this is their story, and it has never been told at the scale it deserves. The Ghanaian nurse in London, the Nigerian engineer in Houston, the Senegalese trader in Paris — they are the continent's largest development institution. They do not have a monument. They barely have a Wikipedia page. They deserve a data story.

**Anyone who thinks about Africa** should care because the dominant frame — aid dependency, institutional failure, waiting for investment — misses the most durable financial system on the continent, which is families taking care of each other across borders.

This is not a story about poverty. It is a story about an economic infrastructure that the formal world built around, and still hasn't fully seen.

---

*Pitch prepared for DataZoba Frontend Engineering Fellowship · Task 03*  
*Word count: ~620 · Dataset: World Bank Open Data (public domain)*