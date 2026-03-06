# Data Dictionary (Updated)

Version: v0.2  
Phase: BCIC – Interpret & Categorize  
Status: Work in Progress  

---

# 1. Room

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| room_id | String (PK) | Unique room identifier | Unique |
| room_type | Enum | Single / Double | Not null |
| capacity | Integer | Maximum occupancy | >=1 |
| occupancy_status | Enum | Vacant / Full | Derived |

---

# 2. Bed

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| bed_id | String (PK) | Unique bed identifier | Unique |
| room_id | FK | Associated room | Must exist in Room |
| allocation_status | Enum | Allocated / Available | Derived |

---

# 3. Student

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| student_id | String (PK) | Unique student identifier | Unique |
| user_id | FK | Linked system account | Must exist in User_Account; Unique |
| name | String | Student full name | Not null |
| email | String | School-issued email address | Unique; Not null |
| room_id | FK | Assigned room | Derived (from active Room Allocation); Nullable |
| bed_id | FK | Assigned bed | Derived (from active Room Allocation); Nullable |

---

# 4. Room Allocation

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| allocation_id | String (PK) | Unique allocation record | Unique |
| student_id | FK | Linked student | Must exist |
| bed_id | FK | Assigned bed | Must exist |
| start_date | Date | Allocation start | Not null |
| end_date | Date | Allocation end | Nullable |

---

# 5. Attendance Log

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| attendance_id | String (PK) | Unique scan event | Unique |
| student_id | FK | Student who scanned | Must exist |
| tag_id | FK | NFC tag scanned | Must exist in NFC_Tag |
| scan_action | Enum | Scan action (Enter / Exit) | Not null |
| device_id | String | Identifier of scanning device | Not null |
| timestamp | DateTime | Scan time | Auto-generated |
| status | Enum | Present / Late / Absent | Derived |

---

# 6. Entry / Exit Log

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| log_id | String (PK) | Unique entry/exit record | Unique |
| tag_id | FK | NFC tag identifier | Must exist in NFC_Tag |
| student_id | FK | Student involved | Must exist |
| facility_id | FK | Facility accessed | Must exist |
| entry_time | DateTime | Entry timestamp | Auto |
| exit_time | DateTime | Exit timestamp | Nullable |

---

# 7. Leave Request

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| request_id | String (PK) | Unique leave request | Unique |
| student_id | FK | Student submitting request | Must exist |
| start_date | Date | Leave start date | Not null |
| end_date | Date | Leave end date | Not null |
| reason | String | Reason for leave | Not null |
| approval_status | Enum | Request status (Pending / Approved / Rejected) | Default Pending |

---

# 8. User Account

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| user_id | String (PK) | Unique system user | Unique |
| role | Enum | Student / Ops Manager / Security / Facilities / SysAdmin | Not null |
| username | String | Login username | Unique |
| password_hash | String | Encrypted password | Not null |
| account_status | Enum | Active / Locked | Default Active |

---

# 9. Audit Log

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| audit_id | String (PK) | Unique audit record | Unique |
| user_id | FK | User performing action | Must exist |
| action | String | Administrative action performed | Not null |
| affected_entity | String | Entity affected by action | Not null |
| timestamp | DateTime | Time of action | Auto-generated |

---

# 10. Facility

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| facility_id | String (PK) | Unique facility identifier | Unique |
| facility_name | String | Facility name | Not null |
| facility_type | Enum | Facility category | Not null |
| status | Enum | Facility availability (Active / Inactive) | Default Active |

---

# 11. NFC Tag / Checkpoint

| Attribute | Data Type | Description | Constraints |
|-----------|-----------|-------------|-------------|
| tag_id | String (PK) | Unique NFC tag identifier | Unique |
| tag_type | Enum | Tag type | Not null |
| room_id | FK | Linked room | Required if tag_type = Room; facility_id must be null |
| facility_id | FK | Linked facility | Required if tag_type = Facility; room_id must be null |
| status | Enum | Tag status (Active / Inactive) | Default Active |

---