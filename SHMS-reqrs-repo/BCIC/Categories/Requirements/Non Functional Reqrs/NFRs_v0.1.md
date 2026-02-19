# Non-Functional Requirements

## 1. Performance

- **NFR-001:** The system shall respond within 3 seconds for common operations under normal load.
- **NFR-002:** The system shall handle 200 NFC scans per minute during peak check-in period (18:00–22:00).
- **NFR-003:** The system shall support 300 students and 10 staff concurrently during peak load without performance degradation.
- **NFR-004:** The system shall complete nightly batch attendance calculation for all 533 students by 22:01.
- **NFR-005:** The real-time occupancy dashboard shall refresh within 5 seconds.

## 2. Availability

- **NFR-006:** The system shall maintain 99% uptime during operational hours (06:00–23:59 daily).
- **NFR-007:** Scheduled maintenance windows shall not exceed 2 hours per month and shall be conducted during off-peak hours (02:00–05:00).

## 3. Security

- **NFR-008:** All communication shall be encrypted using HTTPS/TLS. All personal data shall be encrypted at rest.
- **NFR-009:** All passwords shall be stored as hashed values using a secure algorithm (e.g., bcrypt).
- **NFR-010:** Error messages shall not expose sensitive system information such as database details or stack traces.

## 4. Privacy & Regulatory Compliance

- **NFR-011:** The system shall comply with the Singapore PDPA 2012, including consent, data retention, and user rights provisions.
- **NFR-012:** Location data retention shall be configurable by the administrator.
- **NFR-013:** The system shall obtain explicit user consent before collecting and processing personal and location data.

## 5. Scalability & Capacity

- **NFR-014:** The system shall support a minimum of 533 beds across 260–280 rooms.
- **NFR-015:** The system architecture shall allow for future expansion to additional hostel halls without major redesign.

## 6. Compatibility & Platform

- **NFR-016:** The mobile application shall support Android 12 or higher.

## 7. Architecture & Deployment

- **NFR-017:** The system shall be deployable in a hosting environment approved by the University IT Office.
- **NFR-018:** The system shall maintain separate Production and Test environments.

## 8. Usability

- **NFR-019:** The system shall provide clear and consistent UI branding including university logo, hostel branding, consistent color scheme, and typography.

## 9. Reliability

- **NFR-020:** The system shall ensure data consistency across rooms, beds, student records, allocations, and attendance logs at all times.
- **NFR-021:** The system shall gracefully handle network interruptions and display appropriate messages to users.
