# simulation_airport_queue

In this [project](https://github.com/miraslavats/simulation_airport_queue/blob/4cfce964efa60225b6ba8cbe82a46f1a4515df4d/%20Airport%20Security%20Queues.ipynb), I designed and implemented a discrete-event simulation to model the queue dynamics at an airport security checkpoint. The aim was to observe the behavior of passengers as they proceed through security under various conditions and configurations. Leveraging the power of both theoretical and empirical methodologies, I investigated scenarios from a single queue setup to more complex multi-queue systems, including the involvement of senior security officers. <br><br>
Implementation Details:
<br><br>
Event-Driven Simulation: I constructed an event-based simulator where different events (e.g., passenger arrivals, service completion) are scheduled and processed in chronological order.<br>
Classes and Data Structures: Used classes like Event, Schedule, Queue, and Airport to manage the flow of passengers, queues, and service times.
Service Dynamics: Incorporated both regular security checks and occasional additional screenings by senior security officers.<br>
Test Cases: I compared the simulated queue length & waiting times to the expected queue length & waiting times. The simulation was run with varying arrival rates, a single queue and no senior security officer. Here are the results: <br> <img width="976" alt="Screenshot 2023-10-18 at 2 30 19 PM" src="https://github.com/miraslavats/simulation_airport_queue/assets/112869592/ad3a13c0-9d3e-47b2-963b-ca608f5b7fdb"> <br><br>
To simulate a more complex scenario, I modelled multiple queues with a fixed arrival rate and no security officer. I then compared the results with the theoretical results: <br> 
<img width="976" alt="Screenshot 2023-10-18 at 2 32 11 PM" src="https://github.com/miraslavats/simulation_airport_queue/assets/112869592/2328fb07-df3d-4729-88c4-148cc82f459c">
<br> <br>
Lastly, I simulated a situation with multiple queues and a possibility of having to undergo additional security check with a senior officer. I compared the results with the expectations, however, the theoretical model cannot account for such complications resulting in a difference between the expected and observed values: <br> <img width="976" alt="Screenshot 2023-10-18 at 2 34 34 PM" src="https://github.com/miraslavats/simulation_airport_queue/assets/112869592/61bca933-52ad-4f92-97bf-c654fcab245c"> <br><br>
Assumptions:
<br><br>
The inter-arrival times of passengers and the service times are probabilistically determined, drawing from predefined distributions.<br>
Each queue has at most one person being served at a time.<br>
In the multi-queue scenario with a senior officer, only one person at a time undergoes additional screening.<br>
Passenger selection for additional screening is random, with a specified probability.<br><br>
Use Cases: <br><br>
Capacity Planning: By simulating the flow of passengers, airport administrators can optimize the number of security checkpoints based on the expected traffic.
Policy Testing: Before implementing new security policies (e.g., random additional screenings), officials can simulate their impact to ensure they won’t excessively delay passengers.
