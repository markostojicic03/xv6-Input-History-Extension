# xv6 Input History Extension

## Project Overview
This project involves modifying the xv6 operating system to support an input history feature within the shell. The primary goal is to allow users to browse, edit, and re-execute previously entered commands, enhancing the overall usability of the xv6 command-line interface.

The implementation ensures that the new functionality is integrated seamlessly without disrupting the core stability or performance of the original operating system.

---

## Features

### 1. Command History Storage
* The system captures and stores previously entered commands in a dedicated buffer.
* Empty commands are automatically filtered out and are not saved to the history to maintain a clean record.

### 2. Navigation and Visualization
* Users can navigate through the history using keyboard shortcuts (Shift + Arrow Up for older commands and Shift + Arrow Down for more recent commands).
* History entries are visually distinguished by being printed in green color.
* If a user exits the history navigation by scrolling past the most recent entry, the terminal correctly handles the restoration or clearing of the current input line.

### 3. Command Re-execution and Editing
* Commands retrieved from the history can be executed immediately by pressing Enter.
* The system supports appending additional characters to a command retrieved from history. Any newly typed characters are displayed in white, maintaining a clear distinction between the historical command and the new input.

---

## Technical Implementation
The modification required changes to the console and shell components of the xv6 kernel:

* Input Buffer Management: Logic was added to handle the circular or linear storage of command strings.
* Keyboard Interrupt Handling: Custom logic was implemented to intercept specific key combinations (Shift + Arrows) for history navigation.
* Console Output: The console driver was modified to support color-coded output for history entries.

---

## Build and Execution
This project is managed and submitted via GitHub Classroom.

1. Clone the repository containing the modified xv6 source code.
2. Compile the operating system using the provided Makefile:
   make qemu
3. Once the xv6 shell is active, type several commands and use Shift + Up/Down arrows to test the history functionality.

---
Developed as a project for the Operating Systems course.
