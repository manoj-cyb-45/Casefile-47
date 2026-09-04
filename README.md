# CASEFILE: 47 — The Last Night at MIT University

A standalone Java AWT mystery investigation game.

## Submission status

- Java AWT only — no Swing and no external libraries.
- Source code included.
- Character portrait assets included.
- Runnable JAR included.
- Tested with `javac` compilation.
- UI uses a buffered custom canvas to avoid the previous blank-screen/flicker problem.
- No `ScrollPane`, Maven, Gradle, or third-party dependency is required.

## Story

At 11:47 PM, brilliant Computer Engineering student **Nitheesh Reedy** is found dead in the basement parking area of **Met Institute of Technology (MIT)**.

Five people have believable motives:

1. Manjunath S — close friend
2. Om Prakesh — bullying/revenge conflict
3. Aaradhya Rao — girlfriend
4. Maniappa — hostel warden
5. Yashwanth — roommate

The investigator, **Imran Khan**, must examine locations, interview witnesses, question suspects, collect evidence, build deductions, reconstruct the timeline, and make a final accusation.

## Main features

- Case briefing and detective journal
- Five suspect profiles with portraits
- Two witness interviews
- Nine searchable campus locations
- Evidence locker with duplicate-safe clue storage
- Timeline reconstruction
- Deduction board
- Multiple accusation outcomes
- Replay/reset support
- Final written reasoning before accusation
- Self-contained runnable JAR with image resources

## Data structures and algorithms demonstrated

### Data structures

- `LinkedHashMap<String, Suspect>` — maintains suspects in insertion order while providing name-based lookup.
- `ArrayList` — witnesses, locations, timeline events, and journal entries.
- `LinkedHashSet` — prevents duplicate evidence and deduction entries while preserving discovery order.
- `Map<String, Set<String>>` — adjacency-list representation of the deduction graph.

### Algorithms

- Linear search for selected suspects and searched locations.
- Duplicate detection through set membership.
- Graph edge insertion for clue relationships.
- Breadth-First Search (BFS) in `DeductionBoard.shortestPath()` for finding the shortest clue-to-clue deduction chain.

## OOP concepts

- Encapsulation through private fields and public methods.
- Abstraction through separate logic and UI classes.
- Composition: `Game` owns the investigation collections and `DeductionBoard`.
- Separation of concerns: `detective.logic` contains game state/rules; `detective.ui` contains presentation and AWT event handling.

## Project structure

```text
final_casefile/
├── src/detective/
│   ├── Main.java
│   ├── logic/
│   │   ├── Game.java
│   │   ├── DeductionBoard.java
│   │   ├── Location.java
│   │   ├── Suspect.java
│   │   ├── Witness.java
│   │   └── TimelineEvent.java
│   └── ui/
│       ├── GameWindow.java
│       ├── ImageLoader.java
│       └── Theme.java
├── resources/images/
│   └── character portraits
├── Casefile47.jar
├── build.bat
├── run.bat
└── README.md
```



## Run the submission JAR

From the project folder:

```text
java -jar Casefile47.jar
```

The JAR contains the portrait resources, so the game does not depend on the `resources` folder when launched as a JAR.



## Controls

All navigation and investigation actions are mouse-driven. On the Accuse screen, select a suspect and enter at least a short evidence-based explanation before submitting.

## Academic demonstration checklist

| Requirement | Included |
|---|---|
| Java | Yes |
| AWT GUI | Yes |
| OOP | Yes |
| Collections / data structures | Yes |
| Graph representation | Yes |
| BFS | Yes |
| Search / lookup | Yes |
| Evidence management | Yes |
| Timeline | Yes |
| Multiple endings | Yes |
| Images | Yes |
| Runnable application | Yes |
