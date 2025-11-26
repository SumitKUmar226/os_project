Automated Deadlock Detection & Resolution System

This project is a complete Operating System simulation tool that detects, visualizes, and helps resolve deadlocks in real-time. It models processes, resources, allocations, and wait conditions to identify circular waits using Resource Allocation Graphs (RAGs). The tool includes a full GUI, graph visualizations, detection history, and resolution suggestions, making it useful for OS learning, debugging, and research.

Features
Real-Time Process & Resource Monitoring

Tracks processes, allocated resources, and waiting conditions.

Supports both manual input and automated simulation of deadlock scenarios.

Thread-safe process management using threading.Lock.
(Ref: process tracker code) 

deadlock_detecting_withinput

 Deadlock Detection Engine

Builds a directed Resource Allocation Graph (RAG) with NetworkX.

Identifies circular waits using cycle-detection algorithms.

Logs each detection with a timestamp and stores a complete detection history.
(Ref: DeadlockDetector class) 

deadlock_detector

Interactive GUI

Fully functional Tkinter interface to:

Add processes

Allocate resources

Simulate circular waits

Check for deadlocks

Visualize system state

View detection history

Displays live messages, warnings, and deadlock results.
(Ref: GUI implementation) 

deadlock_detecting_withinput

Graph Visualization

Resource Allocation Graph visualized using Matplotlib.

Highlights processes, resources, and deadlock edges.

Import/export support for presentations or debugging.
(Ref: visualize_system function) 

deadlock_detecting_withinput

Resolution Advisor

Suggests:

Process Termination (lowest PID or priority)

Resource Preemption

Automatically analyzes deadlock cycle nodes to recommend the best recovery strategy.

*How It Works
1️.Process-Resource Simulation

Users can define processes (P1, P2…), assign resources (R1, R2…), and create custom deadlock situations by enforcing hold/wait conditions.

2️.RAG Construction

The system builds a directed graph such as:

P1 → R1 (holds)
R2 → P1 (waiting)
P2 → R2 (holds)
R1 → P2 (waiting)

3️.Cycle Detection

Deadlock exists if:

Process → Resource → Process → Resource → Process ...


forms a cycle of length ≥ 4.

4️.Visualization

The graph is drawn with:

a.Process nodes

b.Resource nodes

c.Deadlock edges highlighted

5️.Suggest Resolution

Shows the best way to break the deadlock:

Terminating a process

Preempting a resource

*Project Structure
📁 os_project
│── deadlock_detector.py
│── deadlock_detecting_withinput.py
│── visualize_path.py
│── requirements.txt
│── README.md
│── os project report.pdf

*Technologies Used
Component	Technology
Language	Python
GUI	Tkinter
Graph Processing	NetworkX
Visualization	Matplotlib
System Monitoring	psutil
Packaging	PyInstaller (optional)

(Ref: Project report section “Technology Used”) 

os project report14

*Installation & Setup
1. Clone the repository
git clone https://github.com/mRsUmItKuMaRcOdEr/os_project

2. Install dependencies
pip install -r requirements.txt

3. Run the application
python deadlock_detector.py


OR the version with input:

python deadlock_detecting_withinput.py

Example Deadlock Scenario

Process 1

Holds: R1

Waiting for: R2

Process 2

Holds: R2

Waiting for: R1

This forms a cycle:

P1 → R1 → P2 → R2 → P1


✔ Deadlock detected
✔ Cycle highlighted in graph
✔ Recommended resolution shown

Screenshots (Optional)

If you want, I can generate UI mockups or example output screenshots for your GitHub page.

*Project Report

A full detailed OS project report (18 pages) is included inside the repo:

Overview

Modules

Flow diagrams

Code explanation

Future scope
(Ref: os project report file) 

os project report14

*Future Enhancements

Integrate with real OS process tables

Add machine-learning-based deadlock prediction

Add web-based dashboard for remote visualization

Support for Banker’s Algorithm & Priority Scheduling

🧑‍💻 Author

Sumit Kumar
B.Tech CSE, Lovely Professional University
