# Functional Requirements

## 1. Authentication & Access Control

- **FR-001:** The system shall allow users to log in using school-issued email.
- **FR-002:** The system shall authenticate credentials against stored records and route users to their role-appropriate dashboard.
- **FR-003:** The system shall enforce role-based access control (Hostel Operations Manager, Security Manager, Student, System Administrator).
- **FR-004:** The system shall allow users to request a password reset via their registered school email.
- **FR-005:** The system shall require school-issued email addresses for student registration and revoke access when the email becomes inactive.
- **FR-006:** The system shall automatically track and maintain the status of each user.
- **FR-007:** The system shall allow a student to submit a leave request.

## 2. Room & Bed Management

- **FR-008:** The system shall allow Hostel Operations Manager to manage room and bed allocation.
- **FR-009:** The system shall allow hostel managers to view the list of unallocated students.
- **FR-010:** The system shall automatically add newly registered students to the list of unallocated students.

## 3. Student Record Management

- **FR-011:** The system shall prevent double-booking of beds or rooms beyond their capacity.

## 4. NFC Scanning & Attendance

- **FR-012:** The system shall allow students to scan NFC at their assigned room to record attendance check-in.
- **FR-013:** The system shall log each NFC scan as an event containing student ID, NFC tag ID, location, timestamp, scan action (Enter/Exit), and device ID.
- **FR-014:** The system shall calculate nightly attendance status (Present/Absent) based on whether the student scanned at their assigned room at 22:00.
- **FR-015:** The system shall generate automated alerts for students who have not checked in by 2200h (inclusive).
- **FR-016:** The system shall allow administrators to view attendance logs for all students with filtering by date and by room or student ID.
- **FR-017:** The system shall allow students to view only their own attendance logs with filtering by date.
- **FR-018:** The system shall allow Hostel Operation Managers to override a student's attendance status with a documented reason.

## 5. Facility Access Logging

- **FR-019:** The system shall log student NFC scans at facility locations (library, mess, gym, AV room, hostel entry/exit).
- **FR-020:** The system shall record each facility NFC scan, including the student ID, location, timestamp, and access action (Enter or Exit).

## 6. Student Self-Service

- **FR-021:** The system shall allow students to view their own profile including personal details, assigned room, and bed.
- **FR-022:** The system shall allow students to update their personal details.

## 7. System Administration

- **FR-023:** The system shall allow the System Administrator to view audit logs.

## 8. Audit & Logging

- **FR-024:** The system shall log all key administrative actions (create, update, delete on rooms, beds, students) with user ID, action, affected entity, and timestamp.
