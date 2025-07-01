# CACHE MEMORY SIMULATOR

**An interactive web-based tool for simulating and visualizing cache memory replacement algorithms.**

## Overview

This project simulates how cache memory operates using various replacement algorithms. It allows users to interactively observe how different policies impact cache performance. The tool is designed primarily for educational purposes, helping students and developers understand cache behavior and replacement strategies in a visual, step-by-step way.

## Features

- Step-by-step simulation of memory access sequences
- Auto-run mode for full automated processing
- Real-time performance statistics:
  - Total accesses
  - Cache hits and misses
  - Hit and miss rates
- Supports multiple replacement algorithms:
  - FIFO (First-In-First-Out)
  - LRU (Least Recently Used)
  - LFU (Least Frequently Used)
  - Random Replacement
- Visual cache memory state with animated feedback
- Descriptions and explanations of each algorithm
- Responsive UI with clean, modern styling using CSS and JavaScript

## Technologies Used

- HTML5
- CSS3 (with custom styles and animations)
- Vanilla JavaScript (no external libraries or frameworks)

## How to Use

1. Clone or download this repository.
2. Open `index.html` in any modern web browser.
3. Enter the following inputs:
   - Cache size (in words)
   - Replacement algorithm
   - Memory address sequence (comma-separated)
4. Use the following controls:
   - **Initialize**: Set up and render the simulation
   - **Step Forward**: Execute one memory access and update the display
   - **Auto Run**: Automatically run through the entire sequence
   - **Reset**: Clear and re-initialize the simulation

## Simulation Logic Explained

### Class: `CacheSimulator`

The simulation is powered by a JavaScript class that manages state, algorithms, and UI updates.

### Key Properties

- `cache`: Array holding current cache content
- `cacheSize`: Number of cache blocks
- `algorithm`: Current replacement policy
- `sequence`: Array of memory addresses to access
- `currentIndex`: Position of the current access
- `hits`, `misses`: Counters for performance tracking
- `accessTimes`: Used for LRU (timestamp map)
- `frequencies`: Used for LFU (frequency map)
- `insertionOrder`: Used for FIFO
- `autoRunning`: Flag for auto-run mode

### Main Methods

- `initialize()`: Sets up cache, algorithm, and input sequence
- `step()`: Processes one memory access
- `handleHit()` and `handleMiss()`: Update cache and stats
- `selectEvictionCandidate()`: Chooses which address to evict
  - FIFO: Evicts the oldest address using `insertionOrder`
  - LRU: Evicts the least recently accessed using `accessTimes`
  - LFU: Evicts the least frequently used using `frequencies`
  - Random: Picks a random entry from cache
- `highlightCacheSlot()`: Adds visual effects for hits and misses
- `updateDisplay()`: Refreshes all UI components:
  - Cache state
  - Access sequence
  - Statistics
  - Progress bar
- `updateAlgorithmInfo()`: Shows description of selected algorithm

### Event Hooks

- `DOMContentLoaded`: Initializes default state on page load
- `change` event on the algorithm dropdown updates the algorithm info

## Use Cases

This tool is ideal for:
- Teaching CPU cache design in computer architecture courses
- Self-study and experimentation with memory systems
- Visual demonstration of algorithmic differences in cache replacement

## Author

Developed by [Farhat Agraine](https://github.com/Farhat-141)


---

![MIT License](https://img.shields.io/badge/license-MIT-green)

![Status](https://img.shields.io/badge/status-active-brightgreen)
