# Task Management Application — C++ & Qt Desktop App

An academic Object-Oriented Programming project developed for the **Object-Oriented Programming** (*Programmazione ad Oggetti*) course at the **University of Padua** (A.Y. 2025/2026). Built with **C++** and the **Qt framework**, the application provides a desktop GUI for organizing, filtering, and persisting heterogeneous personal and professional tasks[cite: 20, 23].

> **Language Note:** While this documentation is in English, the accompanying academic report and GUI labels are written in Italian.

---

## Key Features

* **Multi-Level Class Hierarchy:** Structured around the abstract base class `AbstractTask`, branching into three specialized abstract categories (`TimedTask`, `RepeatableTask`, and `Deadline`) and five concrete task types:
  * `Activity` (events with location, participants, and type)
  * `Reminder` (scheduled notifications and custom messages)
  * `Work` (recurring professional tasks with subtasks, client, and progress status)
  * `Bill` (financial deadlines with amount, provider, IBAN, and recurrence)
  * `Project` (team projects with milestones, budget, status, and tags)[cite: 20]
* **Visitor Design Pattern (`Visitor` & `ConstVisitor`):** Decouples domain logic from both UI rendering and data serialization, adhering to the Open/Closed Principle:
  * **GUI Visitors:** `BlockVisitor`, `DetailVisitor`, and `EditVisitor` dynamically construct task list cards, read-only detail views, and edit forms based on the concrete task type[cite: 22].
  * **Serialization Visitors:** `JsonVisitor` and `XmlVisitor` traverse the object hierarchy to export tasks cleanly[cite: 22].
* **Dual-Format Data Persistence:** Full support for saving and loading tasks in both **JSON** and **XML** via symmetric reader/writer classes (`JsonReader`/`JsonVisitor` and `XmlReader`/`XmlVisitor`)[cite: 22, 23].
* **Interactive Qt GUI:**
