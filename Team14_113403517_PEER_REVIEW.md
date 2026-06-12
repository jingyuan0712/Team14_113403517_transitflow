# Peer Review Report

## Your Details

| Field          | Your answer         |
| -------------- | ------------------- |
| Full Name      | Jingyuan Peng (彭靖淵) |
| Student ID     | 113403517           |
| Team ID        | 14      |
| Date submitted | 2026/6/12   |

---

# Section A — Self-Assessment

## A1. What did you personally implement?

I was primarily responsible for the Neo4j graph database component and the graph-related extensions developed for Task 6.

My major contributions included designing and implementing the entire Neo4j seeding process in `seed_neo4j.py`. This included creating `MetroStation` and `NationalRailStation` nodes, establishing `METRO_LINK`, `RAIL_LINK`, and `INTERCHANGE_TO` relationships, defining graph constraints, generating fare and travel-time mappings, and creating bidirectional graph connections to support route traversal.

I was also the primary author of the graph query implementation in `queries.py`. I developed several graph-based query functions, including:

* `query_shortest_route`
* `query_cheapest_route`
* `query_alternative_routes`
* `query_interchange_path`
* `query_delay_ripple`
* `query_reachable_stations`
* `query_station_connections`

In addition, I implemented supporting helper functions, path conversion logic, APOC-based routing functionality, fallback routing mechanisms, and error-handling logic to improve robustness and reliability.

Beyond the database layer, I modified `agent.py` to expose graph-related tools to the application, including route-finding, delay-ripple analysis, and reachable-station queries. I also updated `ui.py` to support Task 6 demonstrations, graph query examples, model switching, and user interface enhancements that allowed graph database functionality to be demonstrated during testing and presentations.

Finally, I participated in integration testing, debugging, and documentation work, particularly for the graph database design and graph query sections of the project report.

---

## A2. What challenges did you face?

The main challenge I faced was that I had never worked with Neo4j before this project. I was responsible for the Neo4j and graph query components, so I had to spend several days learning Neo4j, graph databases, and Docker from scratch. During development, I encountered issues where the graph structure did not behave as expected, and I spent a significant amount of time debugging routing logic and understanding how Neo4j handled nodes and relationships. For example, I once removed a station from the dataset, but the station label still appeared in Neo4j even though the underlying data had been removed, which was confusing to diagnose.

Another challenge occurred when testing graph queries through Ollama. Some queries would produce correct results on one machine but incorrect results on another, making it difficult to determine whether the issue was caused by my implementation or by differences in the environment. This required repeated testing and verification with my teammates to ensure the correctness of the graph query functions.

For the bonus Task 6 functionality, I initially struggled to decide what new features to implement. I used AI tools to brainstorm possible graph-based extensions and then evaluated which ideas were feasible within the project scope. After implementation, I repeatedly tested and refined the features to ensure that the outputs were accurate and useful.

During project integration, additional challenges appeared when merging the relational database, vector database, and graph database components. Since each team member worked on a different subsystem, unexpected integration issues occasionally emerged after branch merges. These problems were resolved through collaborative testing, debugging, and iterative improvements to the integration branches.

Through these challenges, I gained valuable experience with Neo4j, graph database design, graph algorithms, Docker, Git-based collaboration, and multi-database system integration.

---

## A3. Self-rating

| Criterion                                                   | Rating (1–5) | Justification                                                                                                                       |
| ----------------------------------------------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------------- |
| I delivered the tasks assigned to me in the work allocation | 5            | I completed all assigned Neo4j, graph query, and Task 6 responsibilities according to the agreed work allocation.                   |
| The quality of my work was satisfactory                     | 5            | My implementations were successfully integrated into the final system and passed testing during development and integration stages. |
| I communicated well and kept the team informed              | 5            | I regularly discussed progress, shared updates, and participated in integration and debugging activities with my teammates.         |
| I met deadlines agreed within the team                      | 5            | All assigned work was completed according to the team's planned schedule.                                                           |
| **Overall self-rating**                                     | **5**        | I fulfilled my assigned responsibilities and contributed actively throughout the project.                                           |

---

## A4. Estimated contribution percentage

My estimated contribution: **34%**

---

# Section B — Peer Assessments


## B1. Assessment of Teammate 1

| Field                 | Your answer |
| --------------------- | ----------- |
| Teammate's full name  | 張循          |
| Teammate's student ID | 113403521   |

### What did this teammate deliver?

This teammate took primary responsibility for the PostgreSQL database portion of the project. They developed and maintained the database seeding functionality in `seed_postgres.py`, ensuring that the seeding process could be executed safely and repeatedly without causing inconsistencies. They also prepared and maintained multiple seed-data configurations used during development and testing.

In addition, they were heavily involved in the design of the relational schema defined in `schema.sql`. This included establishing the table structure, defining relationships between entities, configuring keys and constraints, and creating indexes to support efficient data access. They also applied database normalization practices, particularly Third Normal Form (3NF), to improve data organization and reduce unnecessary duplication.

They further contributed to the project's technical documentation by explaining database design choices and evaluating trade-offs such as normalization benefits, indexing strategies, maintenance overhead, and query efficiency. They also assisted with database testing, verification, and documentation tasks associated with the final system and extension features.

### Did their actual contribution match the agreed work allocation?

**Yes.**

Their contributions closely matched the agreed work allocation. They successfully completed the PostgreSQL schema design and seeding responsibilities, contributed to documentation, and participated in testing and integration activities throughout the project.

### Peer rating for this teammate

| Criterion                                           | Rating (1–5) | Justification                                                                                                                 |
| --------------------------------------------------- | ------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| Delivered the tasks assigned in the work allocation | 5            | Completed all assigned PostgreSQL schema design, database seeding, and documentation tasks successfully.                      |
| Quality of their work was satisfactory              | 5            | The database design and seeding workflow were well implemented and integrated smoothly with the rest of the system.           |
| Communicated well and kept the team informed        | 5            | Regularly shared progress updates and participated in discussions regarding development, testing, and integration.            |
| Met deadlines agreed within the team                | 5            | All assigned work was completed according to the agreed project schedule.                                                     |
| **Overall rating for this teammate**                | **5**        | Made significant contributions to the relational database component and consistently fulfilled all assigned responsibilities. |

### Estimated contribution percentage for this teammate

My estimate of their contribution: **33%**



---

## B2. Assessment of Teammate 2

| Field                 | Your answer |
| --------------------- | ----------- |
| Teammate's full name  | 陳衡毅         |
| Teammate's student ID | 113403058   |

### What did this teammate deliver?

This teammate was primarily responsible for implementing the relational database query layer and authentication functionality.

Their work included developing core query functions such as `query_national_rail_availability`, `query_national_rail_fare`, `query_metro_schedules`, `query_metro_fare`, `query_available_seats`, `auto_select_adjacent_seats`, `query_user_profile`, `query_user_bookings`, and `query_payment_info`.

They also implemented transaction-based operations including `execute_booking` and `execute_cancellation`, as well as user authentication features such as registration, login, password recovery, security-question verification, and password updates. For Task 6, they implemented analytical queries including `query_user_travel_history` and `query_route_statistics`.

### Did their actual contribution match the agreed work allocation?

**Yes.**

Their implementation closely followed the planned work allocation and successfully delivered the required relational query and authentication functionality.

### Peer rating for this teammate

| Criterion                                           | Rating (1–5) | Justification                                                                                 |
| --------------------------------------------------- | ------------ | --------------------------------------------------------------------------------------------- |
| Delivered the tasks assigned in the work allocation | 5            | Completed all assigned query, booking, authentication, and analytics tasks.                   |
| Quality of their work was satisfactory              | 5            | The implemented functionality worked correctly and supported key project features.            |
| Communicated well and kept the team informed        | 5            | Participated actively in discussions and provided updates during development and integration. |
| Met deadlines agreed within the team                | 5            | Completed assigned work according to project deadlines.                                       |
| **Overall rating for this teammate**                | **5**        | Consistently contributed to the project and fulfilled all assigned responsibilities.          |

### Estimated contribution percentage for this teammate

My estimate of their contribution: **33%**

---

# Section C — Contribution Percentage Summary

| Member    | Your estimated % | Notes                                                                                  |
| --------- | ---------------- | -------------------------------------------------------------------------------------- |
| Yourself  | 34%              | Neo4j graph database, graph queries, Task 6 graph extensions, UI and agent integration(私心給我自己多1% 幫大家湊到100%) |
| 張循        | 33%              | PostgreSQL seeding, vector database seeding, policy embedding pipeline                 |
| 陳衡毅       | 33%              | Relational database queries, authentication, booking workflows, analytics queries      |
| **Total** | **100%**         |                                                                                        |

---

# Section D — Overall Team Reflection

## D1. What went well in the team's collaboration?

Our team had a clear division of responsibilities from the beginning of the project. Each member focused on a different component, which allowed us to work efficiently without interfering with one another. After completing our individual tasks, we merged our work through Git branches and collaborated on testing and integration. Overall, communication was smooth and the project progressed steadily.

---

## D2. What would you do differently if you did this project again?

If I were to do this project again, I would spend more time understanding the overall system architecture before starting implementation. Although I became familiar with my assigned component, having a broader understanding of the entire system earlier would have made integration easier. I would also begin integration testing earlier to identify cross-component issues sooner.

---

## D3. Is there anything else the markers should know about team dynamics or individual contributions?

Our team primarily worked on separate branches and merged our components throughout the project. When integration issues appeared, we worked together to identify the cause and resolve the problems before merging the fixes back into the project. Overall, the project was completed through teamwork, regular communication, and collaborative problem-solving.

---

# Declaration

I confirm that this peer review reflects my honest and independent assessment. I understand it will be kept confidential from my teammates.

**Signed:** 彭靖淵

**Date:** 2026/6/12
