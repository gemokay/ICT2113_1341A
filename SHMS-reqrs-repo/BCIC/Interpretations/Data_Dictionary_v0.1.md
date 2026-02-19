# Data Dictionary (Interim Version – Analysing Phase)

Version: v0.1
Phase: BCIC – Interpret & Categorize  
Status: Work in Progress  

---

## 1. Student

| Attribute | Data Type | Description | Constraints |
|------------|------------|-------------|-------------|
| student_id | String (PK) | Unique identifier for each student | Must match school ID format |
| name | String | Full name of student | Not null |
| school_email | String | Official school email | Must use university domain |
| phone_number | String | Contact number | Optional |
| status | Enum | Active / On Leave / Inactive | Default = Active |

---

## 2. Room

| Attribute | Data Type | Description | Constraints |
|------------|------------|-------------|-------------|
| room_id | String (PK) | Unique room identifier | Unique |
| room_type | Enum | Single / Double | Not null |
| capacity | Integer | Maximum occupancy | >=1 |
| occupancy_status | Enum | Vacant / Full | Derived |

---

## 3. Bed

| Attribute | Data Type | Description | Constraints |
|------------|------------|-------------|-------------|
| bed_id | String (PK) | Unique bed identifier | Unique |
| room_id | FK | Associated room | Must exist in Room |
| allocation_status | Enum | Allocated / Available | Derived |

---

## 4. Room Allocation

| Attribute | Data Type | Description | Constraints |
|------------|------------|-------------|-------------|
| allocation_id | String (PK) | Unique allocation record | Unique |
| student_id | FK | Linked student | Must exist |
| bed_id | FK | Assigned bed | Must exist |
| start_date | Date | Allocation start | Not null |
| end_date | Date | Allocation end | Nullable |

---

## 5. Attendance Log

| Attribute | Data Type | Description | Constraints |
|------------|------------|-------------|-------------|
| attendance_id | String (PK) | Unique scan event | Unique |
| student_id | FK | Student who scanned | Must exist |
| scan_location | String | NFC checkpoint ID | Must match registered tag |
| timestamp | DateTime | Scan time | Auto-generated |
| status | Enum | Present / Late / Absent | Derived |

---

## 6. Entry Log

| Attribute | Data Type | Description | Constraints |
|------------|------------|-------------|-------------|
| log_id | String (PK) | Unique entry/exit record | Unique |
| student_id | FK | Student involved | Must exist |
| facility_id | FK | Facility accessed | Must exist |
| entry_time | DateTime | Entry timestamp | Auto |
| exit_time | DateTime | Exit timestamp | Nullable |

---

## 7. User Account

| Attribute | Data Type | Description | Constraints |
|------------|------------|-------------|-------------|
| user_id | String (PK) | Unique system user | Unique |
| role | Enum | Student / Ops Manager / Security / Facilities / SysAdmin | Not null |
| username | String | Login username | Unique |
| password_hash | String | Encrypted password | Not null |
| account_status | Enum | Active / Locked | Default Active |

---