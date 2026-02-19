# Breakdown_v0.1 — Incongruent Requirements  
**Project:** Hostel Management App & System (SHMS)  
**Vendor:** TechNest Solutions Pte. Ltd.  
**Customer:** Greenwood University Hostels Division (G-UHD)  
**Document Version:** v0.1  
**Status:** Completed  

---

## Summary

All requirements below were flagged during the Breakdown activity using the Incongruous Requirements Checklist (IRC). Each entry records the original requirement excerpt, the incongruity type, the nature of the issue, the breakdown action taken, whether clarification was required, and the final status with resolution remarks.

---

## Breakdown Table

| Req ID | Requirement Excerpt | Req Type | Incongruity Category (IRC) | Nature of Issue Identified | Breakdown Action Taken | Clarification Required | Status | Remarks |
|---|---|---|---|---|---|---|---|---|
| BO-L0-01 | "The system shall provide end-to-end hostel operations support" | Biz Ops | Ambiguous / Vague | "End-to-end" is undefined and not testable | Flagged as ambiguous; decomposed into functional areas | Yes | Resolved | Hostel Operations Manager clarified that "end-to-end" covers room allocation, attendance tracking, access control visibility, and operational reporting. The requirement was decomposed into distinct functional areas to improve clarity and testability. |
| BO-L1-003 | "The system shall record attendance logs through student QR scanning" | Biz Ops | Omission | No specification of scan frequency or validation rules | Identified missing constraints | Yes | Resolved | Hostel Operations Manager confirmed that attendance is recorded per NFC scan event at designated checkpoints, with each scan logged using student ID, location, and timestamp. Duplicate scans within the same checkpoint window are ignored. |
| BO-L1-007 | "The system should provide basic occupancy visibility" | Biz Ops | Unclear priority | "Should" — weak imperative for operationally critical function | Flagged for priority review | Yes | Resolved | Hostel Operations Manager and Facilities Manager jointly confirmed that occupancy visibility is operationally critical. Requirement priority was upgraded from "should" to "shall" to support daily allocation and maintenance planning. |
| BO-L1-008 | "The system should provide basic auditability of key admin actions" | Biz Ops | Ambiguous | "Basic" undefined; audit scope unclear | Flagged as vague | Yes | Resolved | System Administrator clarified that audit logs must capture create, update, and delete actions on rooms, beds, and student records, including timestamp and admin role. Logs are required for operational accountability but not real-time monitoring. |
| TR-L0-06 | "Android phones have NFC, GPS capture, push notification capabilities" | Technical | Assumption risk | Hardware dependency not validated for all students | Flagged assumption risk | Yes | Resolved | System Administrator accepted stated technology assumptions, confirming that hostel access infrastructure and student Android devices meet the specified capabilities. Students without compatible devices will be managed via manual exception procedures. |
| TR-L0-07 | Performance requirements (peak load, concurrency) | Technical | Compound requirement | Multiple performance metrics in single clause | Split into atomic performance requirements | No | Resolved | Compound performance requirements were separated into atomic clauses covering concurrency limits, response time targets, scan throughput, and batch processing constraints to support independent verification and testing. |
| TR-L1-01 | "The login screen shall support role-based authentication" | Technical | Incomplete | No explicit role definitions listed | Identified omission | Yes | Resolved | System Administrator confirmed supported user roles as Hostel Operations Manager, Security Manager, Facilities Manager, System Administrator, and Student. Each role's access scope will be enforced via role-based access control (RBAC). |
| TR-L0-08 | Availability requirements | Technical | Potential infeasibility | 99% uptime unclear for maintenance windows | Flagged feasibility risk | Yes | Resolved | System Administrator clarified that scheduled maintenance windows are excluded from uptime calculations. Availability is measured only during defined operational hours (06:00–23:59), with maintenance limited to pre-approved off-peak windows. |
| TR-L0-02 | "System shall be deployed in hosting environment approved by University IT Office" | Technical | Omission | Approval process and timeline unspecified | Cross-checked against university IT standards | Yes | Resolved | System Administrator confirmed that deployment approval will be obtained through the University IT Office's standard security review process. The vendor is required to submit architecture and security documentation at least two weeks prior to production deployment. |


---

## Legend

| Field | Description |
|---|---|
| Req ID | Unique identifier for the requirement |
| Req Type | Biz Ops = Business Operations, Technical = Technical Requirement |
| Incongruity Category (IRC) | Classification from the Incongruous Requirements Checklist |
| Breakdown Action Taken | Action applied during the Breakdown activity |
| Clarification Required | Whether the Clarify stage was needed |
| Status | Resolution status at time of this document version |

---


*Extracted by: TechNest Solutions Requirements Analysis Team*
*Date of extraction: 26 January 2026*