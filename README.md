# Project Pet – Gameplay, Systems & Loop Design [file:29]

This repository documents my **gameplay mechanics**, **gameplay loop**, and **system design** work for **Project Pet**, a fast‑paced, physics‑driven PvP party game about chaotic pets and their wizards. [file:29]

---

## Overview

- **Game Type:** Online/team‑based party game (4–10 players, 2–5 teams of 2) [file:29]  
- **Core Fantasy:** Animal “pets” dash around arenas collecting food while their “wizard” owners manipulate the environment from above. [file:29]  
- **Match Structure:** 4 rounds of 2.5 minutes each, plus an optional tiebreaker round. [file:29]  
- **My Focus:**  
  - Designing the **core gameplay mechanics** for Seekers and Observers  
  - Building the **gameplay loop & flow**  
  - Designing the **system architecture**, including the “DO NOT PUSH” button event system and multiplayer foundations [file:29]  

---

## Cover & Arcweave Diagram

> Replace these paths with your actual filenames (for example, inside a `Docs/Images/` folder).

- `![Project Pet – Cover Art](project-pets-2026-01-18-141915.jpg)` – Hero image used as the visual identity for the game. [file:30]  
- `![Arcweave Game Loop Diagram](arcweave-project-pet.png)` – High‑level visual of the round flow and state transitions. (Use your exported Arcweave image here.) [file:29]  

---

## Core Gameplay & Roles

Project Pet is built around **asymmetrical 2‑player teams**: the **Seeker (Pet)** and the **Observer (Wizard)**. [file:29]

### Seeker – Pet (3D Character)

The Seeker is the physics‑driven avatar in the arena. [file:29]

- Navigates the map: walk, dash, jump, and interact with props. [file:29]  
- Collects food while avoiding disguised mines and poisoned items. [file:29]  
- Can bump, steal or interfere with other pets in close‑quarters chaos. [file:29]  
- Optionally uses special interactions (e.g. photo capture) to confirm or reveal items. [file:29]  

### Observer – Wizard (Top‑Down)

The Observer is a strategic support/chaos role viewing the whole arena from above. [file:29]

- Uses abilities to **assist allies** and **sabotage enemies**: [file:29]  
  - Physical Flick – pushes objects or enemy pets.  
  - Spotlight – reveals or highlights key items.  
  - Remote Mines – places hazards on the arena.  
- Manages cooldowns and positioning to control space and tempo. [file:29]  

Together, these roles create constant communication: Observers call shots while Seekers execute moment‑to‑moment movement and risk decisions. [file:29]

---

## Signature Mechanic – “DO NOT PUSH” Button

At the heart of Project Pet is the **“DO NOT PUSH” button**, a systemic risk‑reward mechanic that defines the game’s identity. [file:29]

- Pressing the button triggers a **random event** from a curated pool. [file:29]  
- **70% chance**: beneficial or fun‑chaotic outcomes for the activating team. [file:29]  
- **30% chance**: disruptive or harmful outcomes that can punish greed. [file:29]  

Examples of **good events**: [file:29]  

- Golden Collectible Drop (worth extra points)  
- Magnetic Pull (items move toward the button)  
- Cooldown Reset (team abilities instantly refreshed)  
- Temporary Immunity (brief mine/enviro protection)  

Examples of **bad events**: [file:29]  

- Mine Shower (mines rain down across the arena)  
- Tornado Lift (throws a random Seeker across the map)  
- Role Confusion (inverted controls)  

This system keeps every round unpredictable, encourages table‑talk (“should we press it?”), and heavily supports party‑game drama and comedy. [file:29]

---

## Gameplay Loop

I designed the **core gameplay loop** to alternate between skillful play, strategic decisions, and deliberate chaos. [file:29]

### Round Flow

1. **Game Start** – Players are assigned to teams and roles (Seeker / Observer). [file:29]  
2. **Exploration & Collection** – Seekers move through the arena collecting visually identical food items under time pressure. [file:29]  
3. **Observer Influence** – Observers place traps, use abilities, and manipulate the environment in real time. [file:29]  
4. **Chaos Trigger** – A Seeker may press the **“DO NOT PUSH”** button, firing a random event from the event pool. [file:29]  
5. **Progress Check** – The game checks whether a team has collected all assigned food. [file:29]  
6. **Round End** – Results are shown; if tied across rounds, a tiebreaker round is activated. [file:29]  
7. **Match End** – The overall winner is declared. [file:29]  

This loop ensures rounds are short, readable, and always slightly different because of how players and systems interact. [file:29]

---

## System Design

My system design work focused on making the chaotic party experience **predictable for the engine** but **unpredictable for players**. [file:29]

### Event Pool System (Button Logic)

- Central controller for all “DO NOT PUSH” button events. [file:29]  
- Supports **probability weighting** (e.g. 70% good / 30% bad) and easy addition of new events. [file:29]  
- Designed as modular components so designers can plug in new effects without rewriting core logic. [file:29]  

### Cooldown & Pacing System

- Global and per‑team cooldowns prevent button spam and ability abuse. [file:29]  
- Creates tension: players must choose **when** to force chaos instead of mashing the button. [file:29]  

### Multiplayer Foundation

- Built around **Unity** + **Photon PUN** for real‑time synchronization of: [file:29]  
  - Seeker movement and physics  
  - Observer abilities and trap placement  
  - Global events and button outcomes  

### Tooling & Visual Scripting

- Visual scripting tools (e.g. Fungus/Bolt) used for: [file:29]  
  - Prototyping game‑loop logic quickly  
  - Showing Seeker/Observer state flows clearly to non‑programmers  
  - Iterating on event sequencing and conditions without heavy code changes  

---

## Designed Levels & Role Support (High‑Level)

While level art and detailed layouts were collaborative, the **mechanical side** of levels was designed to reinforce my systems work. [file:29]

- **Dog Park:** Compact arena encouraging frequent collisions; one‑way gates give Observers direct control over routes. [file:29]  
- **Horse Arena:** Open central kill‑box with covered outskirts, balancing visibility for Seekers and tactical obscurity for Observers. [file:29]  
- **Rat Race:** Larger city map with a central road; Observers can trigger cars as moving hazards, and Seekers can hide under vehicles and scenery. [file:29]  

Each level is built “with both roles in mind,” supporting navigation for Seekers and meaningful map controls for Observers. [file:29]

---

## What I Worked On (Portfolio Focus)

For Project Pet I:

- Designed and documented the **core gameplay mechanics** for Seekers and Observers. [file:29]  
- Built the **gameplay loop**, including state transitions, round structure, and Arcweave diagrams. [file:29]  
- Created the **system design** for the “DO NOT PUSH” button, random event pools, and cooldown logic. [file:29]  
- Helped define **level requirements** so arenas reinforce asymmetrical roles and party‑game chaos. [file:29]  
- Specified the **technical foundations** (Unity, Photon PUN, event systems, visual scripting) to support responsive, online party gameplay. [file:29]  

Use this README as a portfolio page or GitHub `README.md` by adding your exported Arcweave and in‑engine screenshots next to the rele
