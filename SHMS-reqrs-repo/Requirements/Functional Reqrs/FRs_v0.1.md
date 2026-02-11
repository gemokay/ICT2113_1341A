# Functional Requirements

## Authentication & Access Control

-   **FR-001:** The system shall allow users to log in using a username
    and password.
-   **FR-002:** The system shall authenticate credentials against stored
    records and route users to their role-appropriate dashboard.
-   **FR-003:** The system shall enforce role-based access control
    (Admin, Warden, Security, Student, Facilities Manager, System
    Administrator, Project Leader/Finance Manager).
-   **FR-004:** The system shall allow users to log out and terminate
    their session.
-   **FR-005:** The system shall display user-friendly error messages
    for invalid credentials, network issues, or server unavailability.
-   **FR-006:** The system shall temporarily lock an account after
    multiple failed login attempts.
-   **FR-007:** The system shall allow users to request a password reset
    via their registered school email.
-   **FR-008:** The system shall require school-issued email addresses
    for student registration and revoke access when the email becomes
    inactive.
-   **FR-009:** The system shall maintain user session state after
    successful authentication and automatically expire sessions after a
    period of inactivity.

## Room & Bed Management

-   **FR-010:** The system shall allow administrators to create, read,
    update, and delete rooms with attributes including room number, type
    (General/Bedroom), block, floor, and capacity.
-   **FR-011:** The system shall allow administrators to create, read,
    update, and delete beds under bedroom-type rooms with attributes
    including bed number and status.
-   **FR-012:** The system shall display real-time room and bed
    occupancy status (Vacant/Occupied/Maintenance).
-   **FR-013:** The system shall prevent allocation of students to rooms
    or beds that are already at full capacity.

## Student Record Management

-   **FR-014:** The system shall allow administrators to create, read,
    update, and delete student records.
-   **FR-015:** The system shall allow administrators to assign a
    student to an available room and bed based on the selected room
    type.
-   **FR-016:** The system shall prevent double-booking of beds or rooms
    beyond their capacity.
-   **FR-017:** The system shall allow administrators to end or modify a
    student's room allocation.

## NFC Scanning & Attendance

-   **FR-018:** The system shall allow students to scan NFC tags at
    their assigned room to record attendance check-in.
-   **FR-019:** The system shall log each NFC scan as an event
    containing student ID, NFC tag ID, location, timestamp, scan action
    (Enter/Exit), and device ID.
-   **FR-020:** The system shall calculate nightly attendance status
    (Present/Absent) based on whether the student scanned at their
    assigned room between 18:00--22:00 (inclusive).
-   **FR-021:** The system shall generate automated alerts for students
    who have not checked in by 22:00.
-   **FR-022:** The system shall allow administrators to view attendance
    logs for all students with filtering by date and by room or student
    ID.
-   **FR-023:** The system shall allow students to view only their own
    attendance logs with filtering by date.
-   **FR-024:** The system shall allow wardens to override a student's
    attendance status with a documented reason.

## Facility Access Logging

-   **FR-025:** The system shall log student NFC scans at facility
    locations (library, mess, gym, AV room, hostel entry/exit).
-   **FR-026:** The system shall record each facility scan with student
    ID, NFC tag ID, location, timestamp, and action (Enter/Exit).

## Student Self-Service

-   **FR-027:** The system shall allow students to view their own
    profile including personal details, assigned room, and bed.
-   **FR-028:** The system shall allow students to update their personal
    details.
-   **FR-029:** The system shall allow students to change their
    password.

## Reporting & Dashboard

-   **FR-030:** The system shall provide a real-time occupancy dashboard
    showing current room and bed status across all blocks with refresh
    interval not exceeding 5 seconds.
-   **FR-031:** The system shall generate weekly facility utilization
    reports showing peak usage times for library, gym, mess, and AV
    room.
-   **FR-032:** The system shall provide attendance compliance reports
    showing the percentage of students who checked in on time.
-   **FR-033:** The system shall provide an executive dashboard with
    read-only KPIs and summary reports for Project Leader and Finance
    Manager roles.

## Security & Monitoring

-   **FR-034:** The system shall allow security staff to view entry/exit
    logs in real time.
-   **FR-035:** The system shall allow security staff to monitor
    real-time student NFC scan activity.
-   **FR-036:** The system shall allow security staff to generate
    security incident reports.

## Facilities

-   **FR-037:** The system shall allow the Facilities Manager to view
    room occupancy status.
-   **FR-038:** The system shall allow the Facilities Manager to export
    occupancy and facility utilization reports.

## System Administration

-   **FR-039:** The system shall allow the System Administrator to
    configure system settings.
-   **FR-040:** The system shall allow the System Administrator to
    manage backups.
-   **FR-041:** The system shall allow the System Administrator to view
    audit logs.

## Audit & Logging

-   **FR-042:** The system shall log all key administrative actions
    (create, update, delete on rooms, beds, students) with user ID,
    action, affected entity, and timestamp.
