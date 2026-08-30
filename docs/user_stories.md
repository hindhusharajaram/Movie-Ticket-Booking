# CineWave Booking Engine — Business Requirements & User Stories

### US-001: Customer Booking Submission
* **As a** customer,
* **I want to** select a movie, show timing, show tier, and ticket count,
* **So that** I can register a formal booking request.
* **Acceptance Criteria:** `Movie`, `Show`, `ShowType`, and `NumberOfTickets` are mandatory.

---

### US-002: Dynamic Cost Calculation & Inventory Validation
* **As a** system,
* **I want to** calculate ticket costs and validate available seating capacity,
* **So that** tickets are not overbooked.
* **Acceptance Criteria:** Total cost computes as `NumberOfTickets * TicketPrice`. Availability validation blocks submissions exceeding current seat inventory.

---

### US-003: Customer Review & Decision Stage
* **As a** customer,
* **I want to** review an immutable summary of my booking before final commitment,
* **So that** I can confirm or cancel the request.
* **Acceptance Criteria:** Summary fields are read-only. Customer selects `Confirmed` or `Cancelled`.

---

### US-004: Automated Seat Allocation & Execution
* **As a** system,
* **I want to** allocate seat numbers and generate a unique Ticket ID upon confirmation,
* **So that** the booking record is fulfilled.
* **Acceptance Criteria:** Generates `TKT-####`, decrements `AvailableSeatsCount`, and resolves as `Resolved-Completed`.

---

### US-005: Cancellation & Notification Handling
* **As a** customer,
* **I want to** receive an automated email alert if my booking is cancelled,
* **So that** I have confirmation of the cancellation.
* **Acceptance Criteria:** Case transitions to `Cancellation` alternate stage, dispatches email alert, and resolves as `Resolved-Cancelled`.

---

### US-006: SLA Governance & Turnaround Escalation
* **As an** operations supervisor,
* **I want to** enforce a 1-day Goal and 2-day Deadline on pending availability checks,
* **So that** booking requests do not bottleneck.
* **Acceptance Criteria:** Case urgency escalates by +10 on Goal and +20 on Deadline.
