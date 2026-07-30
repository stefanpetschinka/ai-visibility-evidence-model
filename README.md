# AI Visibility Evidence Model

A reference model that orders the publisher-side factors behind AI visibility by strength of evidence. Compiled by Stefan Petschinka, Founder of [richresults.ai](https://www.richresults.ai).

**Canonical source:** [richresults.ai/evidence.html](https://www.richresults.ai/evidence.html) (English) · [richresults.ai/de/evidenz.html](https://www.richresults.ai/de/evidenz.html) (German)

This repository is the Markdown mirror of the reference document. The website version is canonical; grades move as evidence accumulates, and every change to the model is committed here with a dated history.

**Status: July 30, 2026**

---

## 01 Definition

**What the AI Visibility Evidence Model is.**

The AI Visibility Evidence Model is a reference model that orders the publisher-side factors behind AI visibility by strength of evidence. It defines five factors, Topical Relevance, Machine Access, Entity Consistency, Extractability and Independent Corroboration, and assigns each a documented evidence grade based on peer-reviewed research and official platform documentation.

The model exists because the field lacks exactly this: a single, verifiable reference that separates what research demonstrates from what marketing claims. Every factor in the model carries its grade and its sources, so every statement on this page can be checked against the primary literature listed in the source register below.

## 02 Purpose and Boundary

**A map of the evidence, not a methodology.**

The AI Visibility Evidence Model maps what the evidence shows works. The AEO Mastery Framework describes how richresults.ai implements it. The model is descriptive: it reports the state of the research. The framework is prescriptive: it defines a working method. Neither replaces the other.

The model is not a ranking system, not a score and not a promise of results. AI visibility is a distribution across repeated, non-deterministic answers, and no factor in this model guarantees a citation. What the model provides is priority: it tells you which work is supported by evidence, which work is hygiene, and which work the evidence contradicts. That is less modest than it sounds. Knowing which factor rests on which evidence tells you what to start with and what can wait. A promise of results cannot tell you that.

One boundary is deliberate: the model orders the factors a publisher can work on. The retrieval stage itself, which engine selects which sources, how it ranks them and where it places them in the model context, is system-side. Controlled work shows this stage dominates citation outcomes [2], and platform documentation describes engine-specific retrieval decisions, including when a system grounds at all [13]. All five factors work toward that stage; none of them controls it.

## 03 The Evidence Scale

**Four grades, defined before use.**

**Grade A:** peer-reviewed and controlled, or independently replicated.  
**Grade B:** controlled with limited transferability to open production systems, or an official platform statement.  
**Grade C:** correlational or triangulated across independent datasets, without causal proof.  
**Grade D:** unsupported or contradicted by evidence.

Each factor additionally carries its mechanism type. A gate is a binary precondition, a driver influences outcomes gradually, and hygiene reduces errors without creating an advantage. Mechanism type and evidence grade are separate dimensions: a factor can be a hard gate on weak empirical evidence, or a soft driver on strong evidence.

These four grades are this model's own scale, and it is deliberately conservative. A factor rated C is not unimportant; it means no one has isolated its causal effect in production, and anyone claiming otherwise is claiming more than the data supports. Grades move as evidence accumulates, and this page carries a visible update date for that reason.

## 04 The Five Factors

### Factor 1: Topical Relevance

Content that directly addresses the actual question is the strongest documented content-side driver of citation. In the largest controlled citation study to date, 252,000 trials across six language models, topic match to the query and position in the model context were the dominant factors, and off-topic content was practically never cited first [1]. Controlled work confirms the same pattern from the model side: when weighing conflicting evidence, models rely heavily on a page's relevance to the query while largely ignoring stylistic authority signals such as scientific-looking references or neutral tone [14]. No entity work, no markup and no authority signal compensates for content that does not answer the question being asked.

**Mechanism: driver. Evidence grade: A.** Peer-reviewed, controlled, convergent across models and study designs [1, 2, 14].

### Factor 2: Machine Access

A source that crawlers cannot reach cannot be retrieved, and a source that cannot be retrieved cannot be used for the content of an answer. Machine Access covers crawl permissions for the relevant bots, index presence, crawlable and renderable main content, and firewall configurations that do not silently block AI crawlers. Platform documentation is explicit on both sides of this gate. OpenAI requires OAI-SearchBot access for a site's content to be used in ChatGPT search answers; excluded pages can still appear as navigational links [12]. Google requires indexed, snippet-eligible pages and states that its AI features run on the same index and ranking systems as classical search [11].

**Mechanism: gate. Evidence grade: B, official platform documentation.** Missing access prevents the content of a page from being used as a rule; it creates no advantage, no guarantee of retrieval and no guarantee of citation [11, 12].

### Factor 3: Entity Consistency

Consistent entity signals support attributing relevant content to the right source. Structured data, stable identifiers, canonical name strings and connected external profiles can reduce ambiguity in how systems resolve who is speaking. The documented effect is error reduction and disambiguation, not a visibility boost: Google states that no special markup is required for its AI features [11], and controlled work shows that knowledge-graph grounding reduces entity disambiguation errors in benchmark settings [15]. A direct causal effect on citation or mention rates in production answer engines has not been demonstrated; the transfer is inference.

**Mechanism: hygiene. Evidence grade: C.** Official platform statements and benchmark evidence for disambiguation; no causal proof as a citation driver [11, 15].

### Factor 4: Extractability

A model can only cite what it can extract. The position of information in the model context changes outcomes causally [3, 4], and pages with concrete numbers, definitions, comparisons and procedures show substantially higher influence on generated answers than pages without them [7]. The boundary is equally documented: these effects apply after retrieval, the influence finding is descriptive and correlational [7], question-and-answer formatting alone does not help [7], and content rewriting tricks show no reliable effect and are frequently harmful under competition [2]. One transfer remains inference: a publisher does not control which passage a retriever selects or where that chunk lands in the model context, so answer-first page structure is a plausible way to serve extraction, not a demonstrated position lever.

**Mechanism: driver. Evidence grades, split:** B for position effects as a model phenomenon [3, 4] and for evidence density in fixed contexts [6]; C for answer-first page structure as a publisher tactic; correlational in production [7], bounded by [2] and [9].

### Factor 5: Independent Corroboration

Mentions by third parties are the classic path into a model's parametric knowledge, and the evidence for this factor is best read as three separate statements. First, controlled research shows that the frequency and spread of an entity in training data causally determine what a model knows about it without searching; the study makes no claim about the independence of those documents [5]. Second, a preprint analysis reports a strong preference of several AI search systems for earned media over brand-owned content, based on the authors' own source classification [8]. Third, the claim that the independence or authenticity of a mention itself causes higher AI visibility is not demonstrated by either source. The practical principle stands on methodological grounds, not on [5]: self-published corroboration networks replicate one voice in many costumes, provide no independent confirmation, and can violate platform guidelines; for manufactured mentions no reliable evidence of a positive effect exists.

**Mechanism: driver for the parametric layer. Evidence grades, split:** B for training-data frequency as a causal factor in parametric knowledge [5]; C for the observed earned-media preference [8]; unsupported for independence itself as a causal visibility factor.

## 05 What the Evidence Does Not Support

**Graded D, for different reasons.**

**llms.txt as a visibility lever.** Google explicitly states that it does not use llms.txt for search or for generative search features [11]. Within the source register reviewed here, no platform documents the file as a ranking or visibility signal.

**Content-level rewriting tricks.** The broadest controlled benchmark found most conversational optimization methods ineffective and frequently harmful to citation ranking, while classical retrieval position dominated [2].

**Schema as a citation switch.** Structured data clarifies and disambiguates. As a direct citation driver for AI features it is officially not required [11], and no causal evidence exists for language-model citations outside search pipelines.

**AI ranking positions as a metric.** Answers vary heavily between identical runs, so a position from a single run is not a reliable rank [9]. Positions become meaningful only as distributions across repeated, paraphrased measurements with uncertainty intervals; visibility is a share, not a single rank.

**Manufactured mentions.** No reliable evidence exists for a positive effect of manufactured or self-produced mentions. In the literature the line between optimization and manipulation does not run along effectiveness anyway, but along truthfulness, verifiable evidence, the separation of content from model instructions, and disclosure of commercial intent [9]. What this model states about corroboration rests on training-data frequency [5] and an observed earned-media preference [8]; neither of those works examines self-produced mentions.

## 06 Visibility Is Not Citation Fidelity

**Being cited and being cited correctly are different outcomes.**

An independent audit of eight AI search engines found collectively incorrect answers to more than 60 percent of source-attribution queries, with premium systems frequently confidently wrong [10]. For any organization this cuts both ways: citation counts overstate control over what is actually said, and citation frequency alone says little about whether an organization is represented correctly and attributed to the original source. A measurement program should therefore track fidelity, whether a system's statements about the entity are accurate, separately from visibility.

## 07 Method Note

**How this model was compiled.**

Every claim in this model was verified against its source: the papers, official documentation and datasets listed in the register below. The synthesis was additionally checked for completeness and counter-arguments by prompting several AI systems with the same evidence question without access to this model. Convergence across systems is an editorial plausibility check, not independent scientific validation: systems share training data, sources and failure modes, and can converge on the same popular error.

Three limits apply to everything on this page. Production systems are non-deterministic, so no single observation proves an effect. Models and retrieval methods change without notice, so findings carry dates. And no one, including the best published research, can causally isolate a single intervention inside a live answer engine. Where this page says the evidence ends, it ends.

## 08 Source Register

**Numbered as cited above.**

1. Vishwakarma, Kumar, Jamidar (2026). What Gets Cited: Competitive GEO in AI Answer Engines. SIGIR 2026. [DOI:10.1145/3805712.3808445](https://doi.org/10.1145/3805712.3808445), [arXiv:2605.25517](https://arxiv.org/abs/2605.25517). Peer-reviewed; authors affiliated with Sprinklr.
1. Puerto et al. (2025). C-SEO Bench: Does Conversational SEO Work? NeurIPS 2025 Datasets and Benchmarks. [arXiv:2506.11097](https://arxiv.org/abs/2506.11097).
1. Liu et al. (2024). Lost in the Middle: How Language Models Use Long Contexts. TACL 2024. [arXiv:2307.03172](https://arxiv.org/abs/2307.03172).
1. Hsieh et al. (2024). Found in the Middle: Calibrating Positional Attention Bias. ACL 2024 Findings. [arXiv:2406.16008](https://arxiv.org/abs/2406.16008).
1. Kandpal et al. (2023). Large Language Models Struggle to Learn Long-Tail Knowledge. ICML 2023. [arXiv:2211.08411](https://arxiv.org/abs/2211.08411).
1. Aggarwal et al. (2024). GEO: Generative Engine Optimization. KDD 2024. [arXiv:2311.09735](https://arxiv.org/abs/2311.09735). Effects conditional on fixed-context settings; see [2] and [9].
1. Zhang, He, Yao (2026). From Citation Selection to Citation Absorption. Preprint. [arXiv:2604.25707](https://arxiv.org/abs/2604.25707).
1. Chen, Wang, Chen, Koudas (2025). Generative Engine Optimization: How to Dominate AI Search. Preprint, University of Toronto. [arXiv:2509.08919](https://arxiv.org/abs/2509.08919). Acknowledges support by ktau.ai.
1. Martinez (2026). Optimizing Visibility in Generative Engines: A Critical Survey. Preprint. [arXiv:2607.14035](https://arxiv.org/abs/2607.14035).
1. Jaźwińska, Chandrasekar (2025). AI Search Has a Citation Problem. Tow Center, Columbia Journalism Review. [cjr.org](https://www.cjr.org/tow_center/we-compared-eight-ai-search-engines-theyre-all-bad-at-citing-news.php).
1. Google Search Central: AI features and your website. [developers.google.com](https://developers.google.com/search/docs/appearance/ai-features). Also: Optimizing your website for generative AI features on Google Search. [developers.google.com](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide).
1. OpenAI: OAI-SearchBot documentation. [openai.com/searchbot](https://openai.com/searchbot). Also: Publishers and Developers FAQ. [help.openai.com](https://help.openai.com/en/articles/12627856-publishers-and-developers-faq).
1. Google AI for Developers: Grounding with Google Search. [ai.google.dev](https://ai.google.dev/gemini-api/docs/google-search). Documents engine-side retrieval decisions; not a publisher participation requirement.
1. Wan, Wallace, Klein (2024). What Evidence Do Language Models Find Convincing? ACL 2024, pages 7468-7484. [DOI:10.18653/v1/2024.acl-long.403](https://doi.org/10.18653/v1/2024.acl-long.403), [arXiv:2402.11782](https://arxiv.org/abs/2402.11782).
1. Pons, Bilalli, Queralt (2024). Knowledge Graphs for Enhancing Large Language Models in Entity Disambiguation. Proc. 23rd Int. Semantic Web Conference (ISWC 2024), LNCS, Springer. [DOI:10.1007/978-3-031-77844-5_9](https://doi.org/10.1007/978-3-031-77844-5_9), [arXiv:2505.02737](https://arxiv.org/abs/2505.02737).

---

## About

Stefan Petschinka is an AEO Strategist, Entity Architect and Founder of [richresults.ai](https://www.richresults.ai), a specialist AEO agency that makes organizations, brands and experts understandable, citable and recommendable by ChatGPT, Perplexity, Claude, Gemini and Google AI Search through Entity Building.

## Related Resources

**AEO Mastery Framework**  
The prescriptive counterpart: how richresults.ai implements what the evidence supports — Entity Building, Structured Data, Citation Signals and Claim Architecture as a working method.

→ [github.com/stefanpetschinka/aeo-mastery-framework](https://github.com/stefanpetschinka/aeo-mastery-framework)

**AI Citation Readiness Framework**  
A methodology for measuring whether an organization, expert or brand is understandable, verifiable and citable by AI systems.

→ [github.com/stefanpetschinka/ai-citation-readiness-framework](https://github.com/stefanpetschinka/ai-citation-readiness-framework)

**Machine First: Why AEO Is Not SEO 2.0**  
The feature article on the architecture the evidence points to: entity resolution, signal extraction, corroboration and answer construction, including the two-stage logic of retrieval and synthesis this model grades.

→ [richresults.ai/machine-first-aeo.html](https://www.richresults.ai/machine-first-aeo.html)

---

## Profiles and References

- [richresults.ai](https://www.richresults.ai)
- [Stefan Petschinka on richresults.ai](https://www.richresults.ai/stefan-petschinka.html)
- [LinkedIn](https://www.linkedin.com/in/stefan-petschinka/)
- [ORCID](https://orcid.org/0009-0009-8223-0339)
- [GitHub](https://github.com/stefanpetschinka)
- [dev.to](https://dev.to/stefanpetschinka)
- [Amazon Author Page](https://www.amazon.com/author/stefan-petschinka)

---

## License

This reference document is released under the MIT License.

See [LICENSE](LICENSE) for details.
