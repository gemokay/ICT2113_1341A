# Non-Functional Requirements

## Performance

-   **NFR-001:** The system shall respond within 3 seconds for common
    operations under normal load.
-   **NFR-002:** The system shall handle 200 NFC scans per minute during
    peak check-in period (18:00--22:00).
-   **NFR-003:** The system shall support 80--100 students and 10 staff
    concurrently during normal operations.
-   **NFR-004:** The system shall support 300 students and 10 staff
    concurrently during peak load without performance degradation.
-   **NFR-005:** The system shall handle up to 400 concurrent users
    under stress test conditions (75% of 533 students).
-   **NFR-006:** The system shall complete nightly batch attendance
    calculation for all 533 students by 22:01.
-   **NFR-007:** The real-time occupancy dashboard shall refresh within
    5 seconds.

## Availability

-   **NFR-008:** The system shall maintain 99% uptime during operational
    hours (06:00--23:59 daily).
-   **NFR-009:** Scheduled maintenance windows shall not exceed 2 hours
    per month and shall be conducted during off-peak hours
    (02:00--05:00).
-   **NFR-010:** Maximum tolerable downtime shall not exceed 7.2 hours
    per month.

## Security

-   **NFR-011:** All communication between client and server shall be
    encrypted using HTTPS/TLS.
-   **NFR-012:** All passwords shall be stored as hashed values using a
    secure algorithm (e.g., bcrypt). No plaintext passwords shall be
    stored.
-   **NFR-013:** Error messages shall not expose sensitive system
    information such as database details or stack traces.

## Privacy & Regulatory Compliance

-   **NFR-014:** The system shall comply with the Singapore Personal
    Data Protection Act (PDPA) 2012, including consent, data retention,
    and user rights provisions.
-   **NFR-015:** The system shall comply with the University IT Security
    Policy including HTTPS/TLS enforcement, RBAC, and audit logging.
-   **NFR-016:** All personal data shall be encrypted at rest and in
    transit.
-   **NFR-017:** Location data retention shall be configurable by the
    administrator.
-   **NFR-018:** The system shall obtain explicit user consent before
    collecting and processing personal and location data.

## Scalability & Capacity

-   **NFR-019:** The system shall support a minimum of 533 beds across
    260--280 rooms.
-   **NFR-020:** The system shall support 3--5 administrative user
    accounts and 5--8 support staff accounts.
-   **NFR-021:** The system architecture shall allow for future
    expansion to additional hostel halls without major redesign.

## Compatibility & Platform

-   **NFR-022:** The mobile application shall support Android 12 or
    higher.
-   **NFR-023:** The web application shall support the latest versions
    of Chrome, Edge, and Firefox on Windows and macOS.
-   **NFR-024:** The system shall not allow direct database access from
    mobile or web client applications.

## Architecture & Deployment

-   **NFR-025:** The system shall be implemented as a multi-tier
    client-server application with separate presentation,
    application/service, and data layers.
-   **NFR-026:** The system shall be deployable in a hosting environment
    approved by the University IT Office (on-premises or cloud).
-   **NFR-027:** The system shall maintain separate Production and Test
    environments.
-   **NFR-028:** Core business operations (NFC scan logging, room
    allocation, attendance queries) shall be exposed through RESTful
    APIs or equivalent service endpoints.
-   **NFR-029:** The system shall use a relational database (e.g., SQL
    Server, PostgreSQL, or MySQL) to store core data.

## Usability

-   **NFR-030:** The login screen shall load within 3 seconds on a
    stable network connection.
-   **NFR-031:** The system shall display a loading indicator during
    authentication processing.
-   **NFR-032:** The system shall provide clear and consistent UI
    branding including university logo, hostel branding, consistent
    color scheme, and typography.
-   **NFR-033:** The app launcher icon shall be provided in adaptive and
    legacy formats in university colors, with 3 icon concepts submitted
    for customer approval.

## Reliability

-   **NFR-034:** The system shall ensure data consistency across rooms,
    beds, student records, allocations, and attendance logs at all
    times.
-   **NFR-035:** The system shall prevent data loss through regular
    automated backups.
-   **NFR-036:** The system shall gracefully handle network
    interruptions and display appropriate messages to users.

## Maintainability

-   **NFR-037:** The system shall include complete system documentation,
    user manuals, and training materials.
-   **NFR-038:** The system shall include PDPA compliance documentation.
-   **NFR-039:** The vendor shall provide a 90-day warranty period post
    final acceptance.
-   **NFR-040:** The system shall support post-implementation annual
    maintenance including software support, hardware warranty extension,
    and server hosting.

## Assumptions

-   **NFR-041:** Students are assumed to have NFC-capable Android
    devices with GPS and push notification capabilities.
-   **NFR-042:** Reliable internet connectivity is assumed to be
    available at all hostel locations.
-   **NFR-043:** Hardware for smart locks, CCTV, and NFC readers shall
    be installed before the application launch.
-   **NFR-044:** Students are assumed to have a working school email
    account.
