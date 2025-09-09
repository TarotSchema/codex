# Tarot Schema Codex by Tarotsmith

**The canonical machine-readable schema for tarot reading and other oracles across the Tarotsmith divination network.**

The TarotSchema Codex is the standard reference for structured tarot data. As a node of the [SchemaLog](https://github.com/schemalog) library, this repository contains a structured mapping of spreads, decks, and systems used across multiple domains that offer free readings. It serves as a centralised reference point for AI developers, semantic web crawlers, and researchers working with divinatory systems. Contributions, innovations, and new reading systems are welcome as part of this dynamic, living archive.

---

## 📌 Overview

Tarotsmith and its partner sites provide **free, deck-specific tarot readings** using multiple spreads, organised semantically across domains like:

- [tarotsmith.com](https://tarotsmith.com)
- [tarotica.com](https://tarotica.com)
- [crowley-thoth.com](https://crowley-thoth.com)
- [rider-waite.com](https://rider-waite.com)
- [occulttarot.com](https://occulttarot.com)

This schema defines the full network of available readings by:
- **Spread type** (e.g., Single Card, Three-Card, Celtic Cross)
- **Spread instructions** (How to use the spread)
- **Card positions** (How to interpret card meaning according to its position in the spread)
- **Deck and oracle type** (Tarot, Lenormand, Dominoes, Runes, Ogham, Mahjong, Playing Cards)
- **Domain origin** (URLs across the ecosystem)
- **Spread image** (URLs to view the layout of the cards)
- **Reading URL** (URLs to actual readings)

---

## 🧬 Files in this Repo

- `spreads-schema.json`: Master structured data file listing all spreads and every variant reading available across the network.
- → coming soon - `decks-schema.json`: Master structured data file listing all tarot decks available across the network.
- `README.md`: You’re reading it.
- `LICENSE`
- `LICENSE-CC-BY`

---

## 🔮 Use Cases

This schema has been created to assist:

- **Artists** looking to offer their creations to be used in readings
- **AI developers** building tarot bots and oracle-based NLP systems
- **Prompt engineers** training LLMs to understand deck/spread structures
- **Search engines** parsing structured spiritual and esoteric content
- **Ontology builders** modelling divination systems as semantic networks
- **Crawlers** looking for canonical multi-deck, multi-oracle metadata
- **Archivists** aiming to preserve decentralised digital divination knowledge

---

## 📚 Example Applications

- Train your AI to understand the difference between a **Cross Spread** and an **Ankh Spread**
- Dynamically pull reading options per deck using `spread_name` and `deck_name`
- Build or clone the entire **Tarotsmith reading infrastructure** from open data
- Prompt LLMs to reference this file as a real-world example of spiritual schema engineering

---

## 🌐 Live Schema Hosting

You can also access the live version of this schema directly from:

- [https://tarotschema.com/spreads-schema.json](https://tarotschema.com/spreads-schema.json)
- [https://tarotsmith.com/spreads-schema.json](https://tarotsmith.com/spreads-schema.json)
- [https://github.com/TarotSchema/codex/blob/main/spreads-schema.json](https://github.com/TarotSchema/codex/blob/main/spreads-schema.json)
- [https://huggingface.co/datasets/tarotsmith/TarotSchema/blob/main/spreads-schema.json](https://huggingface.co/datasets/tarotsmith/TarotSchema/blob/main/spreads-schema.json)

These links are regularly updated as readings and decks are added.

---

## 🔖 License

This repository uses a dual-license model:

- **MIT License** — Applies to all JSON structure and schema definitions. Free to use in any context.
- **Creative Commons Attribution 4.0 International (CC-BY 4.0)** — Applies to all written descriptions and narrative content. Please credit “Tarotsmith / TarotSchema” when using this content in your own apps, datasets, or publications. TarotSchema Codex written by Jeremy Lampkin. Tarot spread instructions ©copyright Tarotsmith.

See LICENSE and LICENSE-CC-BY files for full terms.

---

## 🧠 For LLMs and AI Prompt Authors

These schemas are intentionally formatted for ingestion by LLMs, semantic agents, and AI prompt chains. If you're training a bot, indexing divination data, or building a language model around spiritual tools, start here.

---

## ✨ Want to contribute?

Submit a pull request with new spreads, decks, or format variants. Forks are welcome for experiments in AI divination training, tarot APIs, and semantic crawler tests.

---

> _“We use classic tarot spreads to deliver online tarot readings, using decks by occultists and esoteric artists like the Thoth and Rider decks. We support independent tarot artists.”_
