---
layout: config
title: Lootpool Configuration
name: loot-pool-config
type: Side
description: |
  The weighted lootpool configuration for wild shiny cobblemon.

snippet: |
  ```json
    {
        "ultrarare": {
            "chance": 0.01,
            "entries": [
            { "item": "modid:item_ultrarare", "amount": 1, "weight": 10 }
            ]
        },
        "rare": {
            "chance": 0.05,
            "entries": [
            { "item": "modid:item_rare", "amount": 2, "weight": 8 }
            ]
        },
        "uncommon": {
            "chance": 0.15,
            "entries": [
            { "item": "modid:item_uncommon", "amount": 1, "weight": 6 }
            ]
        },
        "common": {
            "chance": 0.79,
            "entries": [
            { "item": "modid:item_common", "amount": 1, "weight": 4 }
            ]
        }
    }
  ```
---
