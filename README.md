# simulation_airport_queue

In this project, I designed and implemented a discrete-event simulation to model the queue dynamics at an airport security checkpoint. The aim was to observe the behavior of passengers as they proceed through security under various conditions and configurations. Leveraging the power of both theoretical and empirical methodologies, I investigated scenarios from a single queue setup to more complex multi-queue systems, including the involvement of senior security officers. <br><br>
Implementation Details:
<br><br>
Event-Driven Simulation: I constructed an event-based simulator where different events (e.g., passenger arrivals, service completion) are scheduled and processed in chronological order.<br>
Classes and Data Structures: Used classes like Event, Schedule, Queue, and Airport to manage the flow of passengers, queues, and service times.
Service Dynamics: Incorporated both regular security checks and occasional additional screenings by senior security officers.<br><br>
Assumptions:
<br><br>
The inter-arrival times of passengers and the service times are probabilistically determined, drawing from predefined distributions.<br>
Each queue has at most one person being served at a time.<br>
In the multi-queue scenario with a senior officer, only one person at a time undergoes additional screening.<br>
Passenger selection for additional screening is random, with a specified probability.<br><br>
Use Cases: <br><br>
Capacity Planning: By simulating the flow of passengers, airport administrators can optimize the number of security checkpoints based on the expected traffic.
Policy Testing: Before implementing new security policies (e.g., random additional screenings), officials can simulate their impact to ensure they won’t excessively delay passengers.
