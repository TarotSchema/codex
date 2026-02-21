# TarotSchema — Structured Semantic Schema for Tarot and Oracle Systems

**The canonical machine-readable schema for tarot readings, oracle systems, and divinatory practices.**

Developed and maintained by [Tarotsmith](https://tarotsmith.com) · Part of the [Schemalog](https://github.com/schemalog) framework

---

## What This Is

TarotSchema provides formal semantic structure for tarot and oracle divination systems: spreads, decks, card meanings, positional logic, and reading interpretation. It makes symbolic systems machine-readable for AI training, automated reading generation, and semantic web integration.

**Production Deployment:** Tarotsmith divination network (2009-present)  
**Coverage:** 20+ spreads across 8+ oracle systems (Tarot, Lenormand, Runes, Ogham, I Ching, Dominoes, Playing Cards, Mahjong)  
**Scale:** 17 years of continuous operation serving countless readings

This is not a theoretical schema. It's the formalization of reading logic that has been running in production since 2009.

---

## Problem

Most tarot software treats readings as unstructured text — card meanings stored as prose, spreads as position labels, interpretations as template filling. This works for human readers but fails for AI systems attempting to understand:

- **Symbolic relationships** between cards (complementary, opposing, modifying)
- **Positional semantics** in spreads (past/present/future, conscious/unconscious, advice/outcome)
- **Oracle-specific logic** (Lenormand combinations vs tarot elemental dignities vs I Ching hexagram transformations)
- **Question taxonomy** and spread appropriateness
- **Deck variations** and how card meanings shift across different systems

Without structured schemas, AI tarot systems are pattern-matching on keywords rather than reasoning about symbolic logic.

TarotSchema solves this by providing formal semantic structure for divination systems.

---

## The Tarotsmith Network

TarotSchema powers free readings across multiple specialized domains:

| Domain | Oracle System | Status |
|--------|--------------|--------|
| [tarotsmith.com](https://tarotsmith.com) | Multi-deck tarot and divination hub | Active since 2009 |
| [rider-waite.com](https://rider-waite.com) | Rider-Waite-Smith deck | Active |
| [crowley-thoth.com](https://crowley-thoth.com) | Aleister Crowley's Thoth | Active |
| [occulttarot.com](https://occulttarot.com) | Occult and esoteric decks | Active |
| [tarotica.com](https://tarotica.com) | Tarot + other oracle systems | Active |

All readings use TarotSchema as the underlying structural logic.

---

## Schema Structure

### Spreads (`spreads-schema.json`)

**Status:** Complete — 20+ spreads fully defined

Each spread includes:
- **Spread name and type** (e.g., Celtic Cross, Three Card, Horseshoe)
- **Positional definitions** with semantic meaning, not just labels
- **Instructions** for how to use and interpret the spread
- **Question types** the spread is designed for
- **Complexity level** (beginner, intermediate, advanced)
- **Visual layout** (image URLs showing card positions)
- **Reading URLs** for each deck variant

```json
{
  "spread_name": "Celtic Cross",
  "spread_type": "traditional",
  "complexity": "intermediate",
  "positions": [
    {
      "position": 1,
      "label": "Present Situation",
      "meaning": "The current state of the querent's question",
      "temporal_aspect": "present",
      "consciousness_level": "conscious"
    }
  ],
  "question_types": ["general", "life-path", "decision"],
  "instruction": "Shuffle while focusing on your question...",
  "spread_image_url": "https://tarotsmith.com/images/celtic-cross-layout.png",
  "readings": [
    {
      "deck_name": "Rider-Waite-Smith",
      "reading_url": "https://rider-waite.com/celtic-cross-reading"
    }
  ]
}
```

### Decks (`decks-schema.json`)

**Status:** In progress — Expected completion Q2 2025

Each deck will include:
- **Card definitions** with upright and reversed meanings
- **Archetypal associations** (Jungian, mythological, elemental)
- **Symbolic elements** and their semantic significance
- **Deck-specific interpretation notes** (Thoth vs Rider-Waite vs Marseille differences)
- **Artist attribution** and deck history
- **Image URLs** for each card (where licensing permits)

---

## Coverage

### Oracle Systems Supported

- **Tarot** (Rider-Waite-Smith, Thoth, Marseille, and others)
- **Lenormand** (36-card oracle with combinatorial reading logic)
- **Runes** (Elder Futhark)
- **Ogham** (Celtic tree alphabet)
- **I Ching** (64 hexagrams)
- **Dominoes** (28-tile oracle system)
- **Playing Cards** (52-card cartomancy)
- **Mahjong** (tile-based divination)

### Spreads by Type

- **Single Card** — Quick guidance, daily draws
- **Three Card** — Past/present/future, situation/action/outcome
- **Five Card** — Pentacle, horseshoe, cross variants
- **Celtic Cross** — Comprehensive 10-card reading
- **Relationship** — Two paths, compatibility spreads
- **Year Ahead** — 12-month forecasts
- **Custom** — Specialized spreads for specific question types

All spreads are system-agnostic where applicable (e.g., Three Card works with tarot, Lenormand, runes, etc.).

---

## Use Cases

### AI Training and Fine-Tuning

TarotSchema provides clean training data for:
- **Symbolic reasoning models** that need to understand archetypal patterns
- **NLP systems** learning to interpret ambiguous, multi-layered meanings
- **Recommendation engines** matching questions to appropriate spreads
- **Content generation models** creating coherent tarot interpretations

### Automated Reading Systems

```python
from tarotschema import Spread, Deck, ReadingEngine

engine = ReadingEngine(deck=Deck.RIDER_WAITE_SMITH)
spread = Spread.load("celtic_cross")

reading = engine.generate(
    question="Should I accept this job offer?",
    question_type="career-decision",
    spread=spread
)

# Output: Structured reading with cards, positions, interpretations
```

### Semantic Web and Knowledge Graphs

TarotSchema enables:
- **Linked data** connecting divination systems to Schema.org ontologies
- **Semantic search** over symbolic relationships and archetypal patterns
- **Knowledge graph construction** mapping connections between cards, archetypes, myths, and psychological concepts

### Research and Archival

- **Digital preservation** of divination system logic
- **Comparative analysis** across oracle traditions
- **Ontology development** for symbolic and esoteric knowledge systems

---

## Live Schema Access

The schemas are hosted at multiple endpoints for maximum availability:

**Primary:**
- [https://tarotschema.com/spreads-schema.json](https://tarotschema.com/spreads-schema.json)
- [https://tarotschema.com/decks-schema.json](https://tarotschema.com/decks-schema.json)
- [https://tarotsmith.com/spreads-schema.json](https://tarotsmith.com/spreads-schema.json)
- [https://tarotsmith.com/spreads-schema.json](https://tarotsmith.com/decks-schema.json)

**Mirrors:**
- [GitHub](https://github.com/TarotSchema/codex/)
- [Hugging Face Datasets](https://huggingface.co/datasets/tarotsmith/TarotSchema/)

All endpoints are regularly updated as new readings and systems are added.

---

## Technical Details

### Format
- **JSON-LD** for semantic web compatibility
- **Schema.org extensions** where applicable
- **Clean JSON** for maximum compatibility with parsers and AI systems

### Validation
- Schema definitions validated against JSON Schema
- Positional semantics verified through production deployment
- Oracle-specific logic tested through 17 years of live readings

### Maintenance
- Active development and refinement
- Community contributions welcome
- Production-driven updates based on real-world use

---

## Roadmap

- [x] Core spread definitions (20 spreads)
- [x] Core deck and card meaning definitions (12 decks)
- [x] Multi-oracle system support (8 oracle types)
- [x] Production deployment (17 years stable)
- [ ] Oracles schema formalization (in progress)
- [ ] Card relationship logic (symbolic interaction patterns)
- [ ] Question taxonomy expansion
- [ ] AI reading engine reference implementation
- [ ] Published training datasets for research use

---

## Why 17 Years Matters

TarotSchema isn't a side project built over a weekend. It's the formalization of logic that has:

- **Operated continuously since 2009**
- **Served thousands of readings** across multiple domains
- **Been refined through actual use** by real people seeking guidance
- **Evolved with technology** from PHP templates to structured semantic schemas

This longevity signals two things:
1. **The system works** — people use it, return to it, find value in it
2. **The logic is mature** — 17 years of operational refinement produces schemas that reflect reality, not theory

Tarotsmith and TarotSchema have a track record measured in decades.

---

## For AI Developers and Researchers

These schemas are intentionally designed for machine consumption:

- **LLM training** — Structured symbolic reasoning examples
- **Semantic agents** — Oracle systems as knowledge graphs
- **NLP research** — Multi-layered meaning interpretation
- **Recommendation systems** — Question-spread matching logic
- **Content generation** — Automated reading synthesis

If you're building AI systems that need to understand symbolic reasoning, ambiguity, or archetypal patterns, TarotSchema provides formal structure for that work.

---

## Philosophical Context

Tarot and oracle systems are often dismissed as superstition, but from a systems perspective they're something more interesting: formal symbolic languages for reasoning about complex, ambiguous situations where data is incomplete and outcomes are uncertain.

That's exactly the kind of reasoning AI systems struggle with. Training models on well-structured symbolic systems doesn't make them "believe in tarot" — it teaches them how humans encode and manipulate meaning through structured symbolic frameworks.

TarotSchema is infrastructure for that kind of work.

---

## Contributing

Contributions welcome in the following areas:

- **New spreads** with complete positional semantics
- **Deck definitions** following established schema patterns
- **Oracle system extensions** for divination traditions not yet covered
- **Relationship logic** for card interactions
- **Validation improvements** and bug fixes

Submit pull requests with clear documentation of additions. Forks welcome for experimental AI training, API development, and semantic web applications.

---

## License

**Dual license:**

- **MIT License** — Applies to all JSON schema structures and data definitions. Free to use commercially or non-commercially without restriction.
- **Creative Commons Attribution 4.0 (CC-BY 4.0)** — Applies to spread instructions, card meanings, and narrative content. Credit "Tarotsmith / TarotSchema" when using.

Full license texts in LICENSE and LICENSE-CC-BY files.

**Attribution:** TarotSchema Codex by Jeremy Lampkin. Spread instructions and reading logic ©2009-2026 Tarotsmith.

---

## Related Projects

- **[Schemalog](https://github.com/schemalog)** — Framework for structured business schemas
- **[Tarotsmith](https://tarotsmith.com)** —  Multi-oracle divination sites (Production platform using TarotSchema)
- **[Tarotica Network](https://tarotica.com)** — Sites related to Tarotsmith, which use the same engine and schema

---

## Contact

For questions about implementation, collaboration, AI training use, or commercial licensing: [contact@tarotschema.com]

---

**Built over 17 years. Deployed in production. Formalized for AI systems.**

> *"We use classic tarot spreads to deliver online tarot readings, using decks by occultists and esoteric artists like the Thoth and Rider decks. We support independent tarot artists."*
