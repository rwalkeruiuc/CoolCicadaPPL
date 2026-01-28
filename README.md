# Workout Tracker (SwiftUI)

A lightweight SwiftUI workout tracking app focused on clarity, structure, and extensibility.  
Workouts are modeled cleanly, views are separated by responsibility, and history is treated as a first-class concept rather than an afterthought.

<p align="center">
  <img src="images/main-screen.png" width="350">
</p>

---

## Overview

The app allows users to create workouts, add exercises with sets/reps/weight, and view past workout history.  
Workouts can be predefined, custom-built, or persisted as historical records tied to a specific date.

The internal model is intentionally simple: workouts own exercises, and views reflect that hierarchy directly.

<p align="center">
  <img src="images/workout-flow.png" width="600">
</p>

---

## Data Model

### Exercise

An `Exercise` represents a single movement within a workout. Reps are stored as a string to allow flexible formats (e.g. `8–10`, `AMRAP`, `30s`).

```swift
struct Exercise: Identifiable {
    var id: UUID
    var name: String
    var sets: Int
    var reps: String
    var weight: Int
}
