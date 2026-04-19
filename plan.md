# Project 10  In-Network Storage (Implementation Plan)

## Goal

The goal is to store, data in forwarding loops and circles in the network. The implementation should support puting new data, reading, removing, and listing all available data in the network.

## Implementation

## Components:

### P4 Data Plane

Handles packet parsing, metadata tagging, and m aintains packet circulation in loops.

### Controller 

- Manages the "storage" and keeps the packets circulating
- Manages storage operations .
actions:  
- Insert: allow packet into loop.
- Query: clone or send match to controller.
- Delete: drop matching packets.
- Update: Refresh packet TTL or discard from the loop.

### Client
CLI interface for inserting/fetching/removing data from the network
Commands:  
- store <key> <value>
- get <key>
- delete <key>
- list

## Data Structure
Data is encapsulated in custom packet headers
Each packet contains:
- key(id)
- value
- TTL / hop counter