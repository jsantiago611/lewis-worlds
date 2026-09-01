---
title: "The Deeper Heavens Tour: A Perelandra Solo Journaling Game"
description: "An open-source solo journaling and exploration game built inside a digital Zettelkasten based on C.S. Lewis's Perelandra."
draft: false
---

[!card] The Long Walk
An Open-Source Solo Journaling & Exploration Game
Step into C.S. Lewis's Perelandra. Navigate shifting worlds, confront psychological thresholds, and let your daily writing build a path from floating islands up to the mountain summit. Pick your coordinate and begin your pilgrimage.

## How to Play
Play without dice, complex stats, or mechanical bloat. Your daily journal entries drive your movement.

### The Deck & The Map
Five structural directories act as your geographical and psychological terrain:

- 01-WORLDS/: The macro-environments (ranging from the shifting waters of Venus to the fixed stone summit).
- 02-CHARACTERS/: The mirrors and voices pressing against your attention (from the Un-man to the Green Lady).
- 03-CLAIMS/: The foundational metaphysical truths and apologetic lenses tested in daily life.
- 04-THRESHOLDS/:  Scenes, obstacles, and decision points.
- 05-THREADS/ & 06-COMPANIONS/: Cross-corpus connections and historical context.

### The Daily Turn Loop
1. The Draw: Pull one random card from the vault or run a daily randomizer script. The card serves as your daily coordinate.
2. The Inquiry: Read the prompt or governing illusion on the card. Apply the core tension to your daily life. Examine where you rationalize, avoid, or stand firm.
3. The Journal Entry: Write an honest entry in your daily log addressing the prompt.
4. The Climb: Insert a wikilink to your drawn card at the bottom of your entry, such as [[The-Forgotten-Luggage]].

### Progression & The Climb
No artificial scoring system exists. Your links show your progress. Over weeks of journaling, clicking any card note reveals a growing network of backlinks. This network maps your spiritual and psychological patterns across Lewis's universe.

## The Vault Index
Browse the card deck below to explore manually, or use the random card draw below to start your pilgrimage.

Worlds: [[Earth-Ransoms-England|Earth — Ransom's England]] | [[Deep-Heaven|Deep Heaven]] | [[The-Floating-Islands-of-Perelandra|Floating Islands]] | [[The-Fixed-Land|Fixed Land]] | [[The-Subterranean-Basalt-Caves|Basalt Caves]] | [[The-Harappan-Mountain-Summit|Mountain Summit]]

Characters: [[The-Traveler|The Traveler]] | [[Ransom-I|Ransom (Scholar)]] | [[Ransom-II|Ransom (Warrior)]] | [[The-Green-Lady|The Green Lady]] | [[Professor-Edward-Weston|Weston]] | [[The-Un-man|The Un-man]] | [[The-King-Tor|King Tor]] | [[Oyarsa-Malacandra|Oyarsa]]

Claims: [[Naturalism-As-An-Artificial-Shield|Naturalism Shield]] | [[Enemy-Occupied-Territory|Occupied Territory]] | [[The-Numinous|The Numinous]] | [[Evasive-Rationalization|Evasive Rationalization]] | [[Plastic-Creation|Plastic Creation]] | [[Satanic-Parasitism|Satanic Parasitism]] | [[The-Great-Dance|The Great Dance]]

Thresholds: [[Worchester-Common-Walk|The Common Walk]] | [[The-Forgotten-Luggage|Forgotten Luggage]] | [[Pillar-of-Light|Pillar of Light]] | [[Capsule-Launch|Capsule Launch]] | [[Cave-Crucible|Cave Crucible]] | [[Coronation-Ceremony|Coronation]]

<div class="card-draw-widget" style="border: 2px solid var(--dark); border-radius: 8px; padding: 1.5rem; background: var(--light); text-align: center; margin: 2rem 0;">
  <h3>Begin Your Pilgrimage</h3>
  <p>Draw a random coordinate from the Perelandra deck to establish your starting point.</p>
  
  <div id="card-display" style="font-family: serif; font-size: 1.2rem; margin: 1rem 0; font-weight: bold; min-height: 2rem;">
    <em>Click below to reveal your first coordinate...</em>
  </div>

  <button id="draw-btn" style="background: var(--tertiary); color: white; border: none; padding: 0.75rem 1.5rem; border-radius: 4px; font-weight: bold; cursor: pointer;">
    Draw Coordinate Card
  </button>
</div>

<script>
// The master deck list corresponding to your vault notes
const perelandraDeck = [
  { title: "Earth — Ransom's England", link: "01-WORLDS/Earth-Ransoms-England" },
  { title: "The Floating Islands of Perelandra", link: "01-WORLDS/The-Floating-Islands-of-Perelandra" },
  { title: "The Fixed Land", link: "01-WORLDS/The-Fixed-Land" },
  { title: "The Subterranean Basalt Caves", link: "01-WORLDS/The-Subterranean-Basalt-Caves" },
  { title: "The Harappan Mountain Summit", link: "01-WORLDS/The-Harappan-Mountain-Summit" },
  { title: "The Green Lady (Tinidril)", link: "02-CHARACTERS/The-Green-Lady" },
  { title: "The Un-man", link: "02-CHARACTERS/The-Un-man" },
  { title: "Evasive Rationalization", link: "03-CLAIMS/Evasive-Rationalization" },
  { title: "Plastic Creation", link: "03-CLAIMS/Plastic-Creation" },
  { title: "The Great Dance", link: "03-CLAIMS/The-Great-Dance" },
  { title: "The Walk Across Worchester Common", link: "04-THRESHOLDS/Worchester-Common-Walk" },
  { title: "The Cave Crucible", link: "04-THRESHOLDS/Cave-Crucible" }
];

document.getElementById('draw-btn').addEventListener('click', function() {
  const randomIndex = Math.floor(Math.random() * perelandraDeck.length);
  const card = perelandraDeck[randomIndex];
  
  const display = document.getElementById('card-display');
  // Generate an internal Quartz link styled cleanly
  display.innerHTML = `Your Coordinate: <a href="${card.link}" style="color: var(--secondary); text-decoration: underline;">[[${card.title}]]</a>`;
  this.innerText = "Draw Another Coordinate";
});
</script>
