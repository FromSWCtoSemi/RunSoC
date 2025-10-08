\# RunSoC: An Allocation Framework for Automotive Software Components to Semiconductor Design Partitions in System-on-Chips



\## Overview



\*\*RunSoC\*\* is a specialized engineering framework designed for scheduling and allocation of automotive software components on multi-core SoCs. RunSoC integrates static and dynamic strategies to improve core utilization and task latency.



Automotive systems are transitioning from traditional microcontroller-based designs to high‑performance, multi‑core System‑on‑Chip (SoC) platforms, driven by the requirements of software‑defined vehicles. This evolution makes it more challenging to assign software components while ensuring both safety and real‑time performance. Here, existing static and dynamic allocation approaches often face difficulties in achieving an optimal balance between determinism, adaptability, and efficiency.



RunSoC delivers a versatile, metrics‑guided framework that incorporates task dependencies and safety criticality, enabling reproducible, performance‑focused scheduling and allocation for next‑generation software‑defined vehicles.



The repository incorporates theoretical background developed through a rapid review of relevant literature, complemented by expert consultations in an automotive industry context. 

The repository is kept anonymous to satisfy the requirement of blind peer reviews for manuscript submission at scientific journals.
Once the peer review is complete, the repository will be updated with researcher-specific data and a reference to the manuscript containing detailed information.



\## Core Capabilities



1. \*\*Directed Acyclic Graph (DAG) Construction\*\*

&nbsp;	\* Enables users to define custom tasks and their dependencies.

&nbsp;	\* Automatically builds a DAG to represent the workload.

&nbsp;	\* Supports both periodic and event-driven task types.

&nbsp;	\* Provides visualization of task dependencies for validation and analysis.



2\. \*\*Task Scheduling\*\*

&nbsp;	\* Implements two scheduling policies:\*\*

&nbsp;		> FCFS (First-Come-First-Served) – optimized for simplicity and low overhead.

&nbsp;		> PAS (Priority-Aware Scheduling) – respects task priority levels, suited for safety-critical workloads.

&nbsp;	\* Integrates both periodic and event-driven semantics in one cohesive scheduling framework.

&nbsp;	\* Operates with a global event loop that advances system time and evaluates decisions at discrete “decision points.”

&nbsp;	\* Enforces strict periodicity guard logic to ensure timing integrity of periodic tasks.



3\. \*\*Core Allocation and Parallelization\*\*

&nbsp;	\* Provides two complementary allocation strategies:

&nbsp;		> Static Core Allocation: fixed number of cores assigned at simulation start; deterministic and low overhead.

&nbsp;		> Dynamic Core Allocation: adjusts the number of active cores in real time depending on task eligibility; supports adaptability.

&nbsp;	\* Calculates optimal allocation using metrics like maximum parallelism (Pmax) and minimum required core count (Nmin).

&nbsp;	\* Ensures efficient resource utilization and analysis of makespan (total completion time).



4\. \*\*Simulation and Evaluation Environment\*\*

&nbsp;	\* Built as a modular web-based simulation system with:

&nbsp;		> Frontend (Next.js/React): interactive interface for input, configuration, and DAG visualization.

&nbsp;		> Backend (Python): executes all scheduling, allocation, and simulation logic.

&nbsp;	\* Nginx deployment enables seamless communication and integrated execution between frontend and backend.



5\. \*\*Input/Output and Visualization\*\*

&nbsp;	\* User inputs include:

&nbsp;		> Number of cores (C)

&nbsp;		> Scheduling policy (FCFS or PAS)

&nbsp;		> Allocation mode (static or dynamic)

&nbsp;		> Task definitions (execution time, priority, dependencies)

&nbsp;		> Simulation iterations

&nbsp;	\* Outputs include:

&nbsp;		> Schedule trace (task, start time, finish time, core)

&nbsp;		> Gantt chart visualization

&nbsp;	\* Performance metrics:

&nbsp;		> Makespan

&nbsp;		> Critical path length (TCP)

&nbsp;		> Total work (W)

&nbsp;		> Maximum parallelism (Pmax)

&nbsp;		> Average core utilization (Cavg)



6\. \*\*Data Structures and Simulation Logic\*\*

&nbsp;	\* Employs efficient internal representations:

&nbsp;		> Task objects (with properties such as ID, execution time, priority, dependencies).

&nbsp;		> Ready queue using a custom comparator (based on time or priority).

&nbsp;		> Execution log and core pool to track allocation states.

&nbsp;	\* Event-driven main loop ensures deterministic progression and reproducible simulation.



7\. \*\*Analytical and Evaluation Capabilities\*\*

&nbsp;	\* Supports comparative studies (e.g., static vs. dynamic allocation, FCFS vs. PAS).

&nbsp;	\* Provides derived analytical metrics like throughput, latency, and core utilization.

&nbsp;	\* Enables performance benchmarking with different task structures (long critical path vs. balanced DAG).



8\. \*\*Design Principles and Extendability\*\*

&nbsp;	\* Integrates dependency- and criticality-awareness in scheduling and allocation.

&nbsp;	\* Offers practical guidelines for selecting allocation/scheduling methods based on measurable metrics.

&nbsp;	\* Designed for reproducibility, determinism, and scalability in research and real-world SoC evaluations.

&nbsp;	\* Future-ready for extensions such as:

&nbsp;		> Heterogeneous SoC support (different core types)

&nbsp;		> Adaptive load balancing

&nbsp;		> Enhanced periodicity guards

&nbsp;		> Redundancy and fault-tolerance mechanisms

