# BrightAid Project Report

## Introduction

BrightAid is a comprehensive web-based platform designed to address the critical issue of student dropouts in rural Bangladesh by connecting donors, NGOs, and schools through a transparent, data-driven system. The platform serves as a bridge between those who want to help and those who need assistance, ensuring that educational support reaches the most vulnerable students and schools.

The system provides real-time monitoring of school conditions, student performance, and fund utilization while implementing  dropout prediction algorithms to identify at-risk students before they leave school. Through gamification elements and transparent reporting mechanisms, BrightAid encourages sustained engagement from donors and NGOs while maintaining accountability in fund usage.

Built with modern web technologies including React.js for the frontend, Spring Boot for the backend, and MySQL for data management, BrightAid offers a scalable and secure solution that can handle multiple stakeholders including schools, students, donors, NGOs.

## Motivation

The development of BrightAid was driven by several critical challenges in Bangladesh's education sector:

• **High Dropout Rates**: Rural schools face significant student dropout due to poverty, early marriage, child labor, and lack of basic infrastructure

• **Funding Gap**: Many schools lack adequate resources and funding to provide quality education and maintain basic facilities

• **Lack of Transparency**: Existing donation systems often lack transparency, making donors hesitant to contribute

• **No Systematic Approach**: Absence of data-driven systems to identify and support at-risk students before they drop out

• **Limited Donor-School Connection**: No direct platform connecting willing donors with schools that need specific support

• **Inefficient Resource Allocation**: Resources are not always directed to the areas of greatest need

• **Poor Monitoring**: Limited tracking of fund utilization and project outcomes

• **Geographic Barriers**: Rural schools struggle to reach potential donors and NGOs due to location constraints

• **Data-Driven Decision Making**: Need for analytics and insights to guide educational policy and intervention strategies

## Similar Projects

**AlterYouth (http://www.alteryouth.com)**: AlterYouth, imagine Uber for scholarships, is a C2C scholarship app enabling users from around the world to start scholarships directly for financially struggling students in Government Primary Schools of Bangladesh, through digital banking. AlterYouth does not accept donations, the app simply transfers scholarships from users to student's bank accounts, with the primary aim of preventing children from choosing work over school.


## Complete Feature List

### 1. User Authentication & Multi-Role Registration System

**Description**: Secure authentication system supporting multiple user roles with JWT token-based security.

**Workflow**:
1. User selects role (School, Donor, NGO) during registration
2. User provides role-specific information and credentials
3. Role-based access control restricts features based on user type

**Key Features**:
- Multi-role registration with role-specific forms
- JWT token-based authentication for secure API access
- Password encryption and secure credential storage
- Session management with token expiration
- Role-based authorization for endpoints

---

### 2. School Management System

**Description**: Comprehensive school profile and data management system.

**Workflow**:
1. School registers with institutional details (name, registration number, type)
2. School provides geographic information (division, district, upazila)
3. School maintains profile with facility information
4. School tracks student enrollment and academic data
5. School tracks and monitor the project and update projects for fund utilizations

**Key Features**:
- School profile creation with unique registration numbers
- Geographic location mapping with coordinates
- School type categorization (Primary, Secondary, High School, Madrasa)
- Document upload 
- Integration with geographic data hierarchy
- School image/logo management

---

### 3. Student Profile & Enrollment System

**Description**: Detailed student information management with family background tracking.

**Workflow**:
1. School enrolls student with basic information (name, ID, class)
2. School enters family background (parents' status, occupation, income)
3. Student profile includes contact information and address
4. Profile image can be uploaded for identification
5. Academic performance and class level are tracked
6. Scholarship status is automatically updated based on donations
7. Student data feeds into dropout prediction algorithm

**Key Features**:
- Comprehensive student profiles with unique ID numbers
- Family background documentation (parent status, occupation, income)
- Class level tracking from grade 1-10
- Gender-based analytics
- Guardian contact information
- Profile image management
- Scholarship status tracking
- Academic performance indicators
- Integration with dropout prediction system

---

### 4.  Dropout Prediction System

**Description**: A risk factor based on Student parents family income, attandance rate that predicts student dropout risk.

**Workflow**:
1. System collects student data (family income, parent status, attendance)
2. Risk calculation algorithm processes multiple parameters
3. Risk score is calculated based on weighted factors
4. Students are categorized as HIGH, MEDIUM, or LOW risk
5. High-risk students are flagged for intervention
6. Schools and donors can view risk assessments
7. System recommends targeted support for at-risk students

**Risk Calculation Algorithm**:
```
Risk Factors:
- Parent Status: 
  * Both deceased = 4 points
  * Father deceased = 3 points
  * Mother deceased = 2 points
  * Both alive = 1 point

- Family Income:
  * < 12,000 BDT = 3 points
  * 12,001-40,000 BDT = 2 points
  * > 40,000 BDT = 1 point

- Attendance Rate:
  * < 30% = 3 points
  * 30-60% = 2 points
  * > 60% = 1 point

Risk Status:
- HIGH: Total score ≥ 8
- MEDIUM: Total score ≥ 5
- LOW: Total score < 5
```

**Key Features**:
- Multi-factor risk assessment
- Automated risk status calculation
- Early warning system for at-risk students
- Risk-based student prioritization for sponsorship
- Historical risk tracking


---

### 5. Donation Management System

**Description**: Comprehensive donation processing with multiple donation types and purposes.

**Workflow**:
1. Donor browses schools, students, or projects
2. Donor chooses donation purpose (Student Sponsorship, School Project)
3. Donor enters amount and optional message
4. Payment is processed through secure gateway
5. Transaction is recorded with unique reference number
6. Receipt and confirmation are sent to donor
7. Funds are allocated to designated recipient
8. Scholarship status is automatically updated for student sponsorships

**Key Features**:
- Purpose-specific donations (Student Sponsorship, School Projects, General Support)
- Secure payment gateway integration
- Transaction reference generation
- Payment status tracking
- Donation history and receipts
- Automated scholarship status updates
- Multi-source donation tracking (Donors + NGOs)

---

### 6. NGO Project Management System

**Description**: NGO-led project creation and management with funding tracking.

**Workflow**:
[NGO and Donor are almost same]
1. NGO creates Campaigns with details (name, description, budget)
2. NGO selects Campaigns type and target schools
3. Campaigns timeline and milestones are defined
4. NGO can invite schools to participate


**Key Features**:
- Campaign creation and management by NGOs
- Campaign type categorization
- Budget planning and tracking
- Timeline management with start/end dates
- School invitation system


---

### 7. School Project System

**Description**: School-initiated projects for infrastructure and educational improvements.

**Workflow**:
1. School creates project with funding requirements
2. School specifies project type (Infrastructure, Equipment, Meals, etc.)
3. Project details include budget breakdown and timeline
4. Project is published for donor visibility
5. Donors and NGO can browse and fund school projects
6. School tracks donations received
7. School posts progress updates with images
8. School records expenses and fund utilization
9. Transparency reports are generated
10. Project is marked complete when goals are achieved

**Key Features**:
- School-initiated project creation
- Project categorization by type
- Budget specification and tracking
- Image-based progress documentation
- Donor and NGO matching and funding
- Progress updates and milestones
- Expense recording and categorization
- Transparency report generation
- Project timeline management
- Completion status tracking

---

### 8. Fund Transparency & Utilization Tracking

**Description**: Comprehensive fund tracking system ensuring transparency in donation usage.

**Workflow**:
1. School receives donations for projects
2. School records each expense with details
3. Expense is categorized (Materials, Labor, Equipment, etc.)
4. Before/after images are uploaded as proof
5. Amount used is deducted from available funds
6. Utilization status is updated 
7. Transparency reports are generated automatically
8. Donors can view how their funds were used

**Key Features**:
- Real-time fund utilization tracking
- Expense categorization and recording
- Before/after project documentation with images
- Transparency report generation
- Audit trail maintenance
- Donor-specific fund tracking
- Utilization status monitoring
- Remaining fund calculation

---

### 9. Gamification System for Donors & NGOs

**Description**: Point-based reward system to encourage sustained engagement.

**Workflow**:
1. Donor/NGO makes a donation
2. Points are awarded based on donation amount
3. Achievement badges are unlocked at milestones
4. User level increases with accumulated points
5. Leaderboard displays top contributors
6. Impact profile shows contribution statistics
7. Recognition certificates are generated
8. Community engagement metrics are tracked

**Key Features**:
- Point-based reward calculation
- Achievement badge system
- Level progression tracking
- Leaderboard and rankings
- Impact visualization
- Recognition certificates
- Community engagement metrics
- Donation milestones
- Comparative analytics

---

### 10. Messaging & Communication System

**Description**: Real-time messaging between stakeholders for collaboration.

**Workflow**:
1. User initiates conversation with another stakeholder
2. Conversation is created with SChool and NGO
3. Messages are sent in real-time
4. Notifications alert participants of new messages
5. Message history is maintained
6. Conversation threads are organized by project/topic
7. School or NGO can view all active conversations

**Key Features**:
- Real-time messaging between users
- Multi-participant conversations
- Message type categorization
- Notification system
- Conversation history
- Project-specific communication channels
- Unread message tracking



### 11. Reporting & Analytics Dashboard

**Description**: Role-specific dashboards with comprehensive analytics and insights.

**Workflow**:
1. User logs into role-specific dashboard
2. Dashboard displays key metrics and statistics
3. Interactive charts visualize data trends
4. Performance indicators are calculated in real-time
5. Financial summaries show donation/expense data
6. Geographic insights display regional distribution
7. Reports can be exported for external use
8. Comparative analysis shows period-over-period changes

**Key Features**:
- Role-specific dashboards (School, Donor, NGO, Admin)
- Real-time data visualization
- Interactive charts and graphs
- Performance metrics tracking
- Financial summaries and breakdowns
- Export functionality (PDF, Excel)
- Scheduled reports
- Comparative analysis
- Trend identification
- Impact assessment metrics

---

---


### 12. Student Sponsorship Matching System

**Description**: Intelligent matching of donors with students needing support.

**Workflow**:
1. System identifies students without scholarships
2. High-risk students are prioritized
3. Students with lowest family income are highlighted
4. Donor and NGO browses available students for sponsorship
5. Donor and NGO selects donation frequency
6. Sponsorship donation is processed
7. Student scholarship status is updated automatically
8. Donor receives updates on sponsored student
9. Monthly sponsorships are tracked
10. Renewal reminders are sent to donors

**Key Features**:
- Intelligent student matching algorithm
- Risk-based prioritization
- Income-based sorting
- Exclusion of already-sponsored students
- Automated scholarship status updates
- Sponsor-student relationship tracking
- Progress updates for sponsors
- Renewal management
- Impact reporting for sponsors

---


### 13. Project Update & Progress Tracking

**Description**: Visual progress tracking with image-based updates.

**Workflow**:
1. School posts project update
2. Update includes description and images
3. Progress percentage is updated
4. Milestone completion is marked
5. Before/after comparisons are displayed


**Key Features**:
- Image-based progress updates
- Update description and details
- Progress percentage tracking
- Milestone management
- Before/after image comparison
- Update frequency tracking

---

### 14. Scholarship Status Management

**Description**: Automated scholarship tracking based on donations.

**Workflow**:
1. Student receives sponsorship donation
2. System checks donation completion status
3. Scholarship status is automatically updated
4. Monthly verification runs to update statuses
5. Students with current month donations get scholarship flag
6. Students without recent donations lose scholarship status


**Key Features**:
- Automated scholarship status updates
- Monthly verification process
- Multi-source donation tracking (Donors + NGOs)
- Current month donation checking
- Scholarship flag management




## Queries to Implement Features

### 1. High-Risk Student Sponsorship Query

**Purpose**: Find high-risk students available for sponsorship, excluding those already sponsored.

**Complexity**: High - Uses multiple JOINs, subqueries, and complex filtering logic.

```sql
SELECT s.* FROM students s 
LEFT JOIN dropout_predictions dp ON s.student_id = dp.student_id 
WHERE s.has_scholarship = false 
AND (dp.risk_status = 'HIGH' OR s.family_monthly_income < 15000)
AND s.student_id NOT IN (
    SELECT DISTINCT d.student_id 
    FROM donations d 
    WHERE d.student_id IS NOT NULL 
    AND d.donation_type = 'STUDENT_SPONSORSHIP'
    AND d.payment_status = 'COMPLETED'
)
AND s.student_id NOT IN (
    SELECT DISTINCT nsd.student_id 
    FROM ngo_student_donations nsd 
    WHERE nsd.student_id IS NOT NULL 
    AND nsd.payment_status = 'COMPLETED'
)
ORDER BY 
    CASE WHEN dp.risk_status = 'HIGH' THEN 1 ELSE 2 END,
    s.family_monthly_income ASC 
LIMIT 10;
```

---

### 2. Comprehensive Donation Tracking Query

**Purpose**: Get all donations from all sources (donors + NGOs) for a specific school.

**Complexity**: Very High - Uses UNION ALL to combine multiple donation sources with complex JOINs.

```sql
SELECT donation_id, amount, payment_status, donated_at, transaction_ref, 
donor_name, project_title, student_name, donation_type, purpose, source FROM (
  SELECT d.donation_id, d.amount, d.payment_status, 
  COALESCE(d.donated_at, d.created_at) as donated_at, 
  COALESCE(pt.transaction_reference, CONCAT('DON', LPAD(d.donation_id, 6, '0'))) as transaction_ref, 
  COALESCE(donor.donor_name, 'Anonymous Donor') as donor_name, 
  sp.project_title, s.student_name, d.donation_type, d.purpose, 'donor' as source 
  FROM donations d 
  LEFT JOIN payment_transactions pt ON d.transaction_id = pt.transaction_id 
  LEFT JOIN donors donor ON d.donor_id = donor.donor_id 
  LEFT JOIN students s ON d.student_id = s.student_id 
  LEFT JOIN school_projects sp ON d.project_id = sp.project_id 
  WHERE (s.school_id = ? OR sp.school_id = ?) 
  UNION ALL 
  SELECT nsd.student_donation_id as donation_id, nsd.amount, 
  nsd.payment_status, nsd.donated_at, 
  CONCAT('NGOS', LPAD(nsd.student_donation_id, 6, '0')) as transaction_ref, 
  COALESCE(n.ngo_name, 'NGO Donor') as donor_name, 
  NULL as project_title, s.student_name, nsd.donation_type, 
  'STUDENT_SPONSORSHIP' as purpose, 'ngo' as source 
  FROM ngo_student_donations nsd 
  LEFT JOIN ngos n ON nsd.ngo_id = n.ngo_id 
  LEFT JOIN students s ON nsd.student_id = s.student_id 
  WHERE s.school_id = ?
  UNION ALL 
  SELECT npd.project_donation_id as donation_id, npd.amount, 
  npd.payment_status, npd.donated_at, 
  CONCAT('NGOP', LPAD(npd.project_donation_id, 6, '0')) as transaction_ref, 
  COALESCE(n.ngo_name, 'NGO Donor') as donor_name, 
  sp.project_title, NULL as student_name, npd.donation_type, 
  'SCHOOL_PROJECT' as purpose, 'ngo' as source 
  FROM ngo_project_donations npd 
  LEFT JOIN ngos n ON npd.ngo_id = n.ngo_id 
  LEFT JOIN school_projects sp ON npd.project_id = sp.project_id 
  WHERE sp.school_id = ?
) AS all_donations 
ORDER BY donated_at DESC;
```

---

### 3. Dropout Risk Calculation Query

**Purpose**: Calculate dropout risk status using multiple weighted factors.

**Complexity**: High - Uses nested CASE statements with complex scoring logic.

```sql
SELECT 
CASE 
WHEN (
  (CASE WHEN s.father_alive = 0 AND s.mother_alive = 0 THEN 4 
        WHEN s.father_alive = 0 AND s.mother_alive = 1 THEN 3 
        WHEN s.father_alive = 1 AND s.mother_alive = 0 THEN 2 
        ELSE 1 END) + 
  (CASE WHEN s.family_monthly_income < 12000 THEN 3 
        WHEN s.family_monthly_income BETWEEN 12001 AND 40000 THEN 2 
        ELSE 1 END) + 
  (CASE WHEN ? < 30 THEN 3 
        WHEN ? BETWEEN 30 AND 60 THEN 2 
        ELSE 1 END)
) >= 8 THEN 'HIGH' 
WHEN (
  (CASE WHEN s.father_alive = 0 AND s.mother_alive = 0 THEN 4 
        WHEN s.father_alive = 0 AND s.mother_alive = 1 THEN 3 
        WHEN s.father_alive = 1 AND s.mother_alive = 0 THEN 2 
        ELSE 1 END) + 
  (CASE WHEN s.family_monthly_income < 12000 THEN 3 
        WHEN s.family_monthly_income BETWEEN 12001 AND 40000 THEN 2 
        ELSE 1 END) + 
  (CASE WHEN ? < 30 THEN 3 
        WHEN ? BETWEEN 30 AND 60 THEN 2 
        ELSE 1 END)
) >= 5 THEN 'MEDIUM' 
ELSE 'LOW' END as risk_status 
FROM students s WHERE s.student_id = ?;
```

---

### 4. School Total Funds Calculation Query

**Purpose**: Calculate total funds received by school from all donation sources.

**Complexity**: High - Aggregates funds from three different donation tables.

```sql
SELECT COALESCE(
    (SELECT SUM(d.amount) FROM donations d 
     JOIN school_projects sp ON d.project_id = sp.project_id 
     WHERE sp.school_id = ? AND d.payment_status = 'COMPLETED') +
    (SELECT SUM(npd.amount) FROM ngo_project_donations npd 
     JOIN school_projects sp ON npd.project_id = sp.project_id 
     WHERE sp.school_id = ? AND npd.payment_status = 'COMPLETED') +
    (SELECT SUM(nsd.amount) FROM ngo_student_donations nsd 
     JOIN students s ON nsd.student_id = s.student_id 
     WHERE s.school_id = ? AND nsd.payment_status = 'COMPLETED'),
    0.0
) as total_funds;
```

---

### 5. Available Project Donations Query

**Purpose**: Get available donations for project utilization with remaining amounts.

**Complexity**: Very High - Combines donor and NGO donations with utilization tracking.

```sql
SELECT donation_id, donor_name, amount, utilized_amount, remaining_amount, donated_at, source 
FROM (
  SELECT d.donation_id, 
  COALESCE(donor.donor_name, 'Anonymous') as donor_name, 
  d.amount, 
  COALESCE(SUM(fu.amount_used), 0) as utilized_amount, 
  d.amount - COALESCE(SUM(fu.amount_used), 0) as remaining_amount, 
  d.donated_at, 
  'Donor' as source 
  FROM donations d 
  LEFT JOIN donors donor ON d.donor_id = donor.donor_id 
  LEFT JOIN fund_utilization fu ON d.donation_id = fu.donation_id 
  WHERE d.project_id = ? AND d.payment_status = 'COMPLETED' 
  GROUP BY d.donation_id, donor.donor_name, d.amount, d.donated_at 
  UNION ALL 
  SELECT npd.project_donation_id as donation_id, 
  COALESCE(n.ngo_name, 'NGO') as donor_name, 
  npd.amount, 
  COALESCE(SUM(fu.amount_used), 0) as utilized_amount, 
  npd.amount - COALESCE(SUM(fu.amount_used), 0) as remaining_amount, 
  npd.donated_at, 
  'NGO' as source 
  FROM ngo_project_donations npd 
  LEFT JOIN ngos n ON npd.ngo_id = n.ngo_id 
  LEFT JOIN fund_utilization fu ON npd.project_donation_id = fu.donation_id 
  WHERE npd.project_id = ? AND npd.payment_status = 'COMPLETED' 
  GROUP BY npd.project_donation_id, n.ngo_name, npd.amount, npd.donated_at 
) AS all_available_donations 
WHERE remaining_amount > 0 
ORDER BY remaining_amount DESC, donated_at DESC;
```

---

### 6. Donor Comprehensive Statistics Query

**Purpose**: Get complete donor statistics including donations, students, and projects.

**Complexity**: Medium - Uses aggregation with multiple COUNT and SUM operations.

```sql
SELECT 
    d.donor_id,
    d.donor_name,
    COUNT(DISTINCT don.donation_id) as total_donations,
    COALESCE(SUM(don.amount), 0) as total_donated,
    COUNT(DISTINCT don.student_id) as students_sponsored,
    COUNT(DISTINCT don.project_id) as projects_supported,
    MAX(don.donated_at) as last_donation_date
FROM donors d
LEFT JOIN donations don ON d.donor_id = don.donor_id 
    AND don.payment_status = 'COMPLETED'
WHERE d.donor_id = ?
GROUP BY d.donor_id, d.donor_name;
```

---

### 7. Scholarship Status Update Query

**Purpose**: Update scholarship status for students with current month donations.

**Complexity**: Very High - Uses UNION, subqueries, and date functions for monthly tracking.

```sql
UPDATE students 
SET has_scholarship = CASE 
    WHEN student_id IN (
        SELECT DISTINCT student_id FROM (
            SELECT d.student_id 
            FROM donations d 
            WHERE d.student_id IS NOT NULL 
            AND d.payment_status = 'COMPLETED'
            AND MONTH(d.payment_completed_at) = MONTH(CURRENT_DATE)
            AND YEAR(d.payment_completed_at) = YEAR(CURRENT_DATE)
            UNION
            SELECT nsd.student_id 
            FROM ngo_student_donations nsd 
            WHERE nsd.student_id IS NOT NULL 
            AND nsd.payment_status = 'COMPLETED'
            AND MONTH(nsd.payment_completed_at) = MONTH(CURRENT_DATE)
            AND YEAR(nsd.payment_completed_at) = YEAR(CURRENT_DATE)
        ) AS current_month_donations
    ) THEN 1 
    ELSE 0 
END;
```

---

### 8. Sponsored Students with School Info Query

**Purpose**: Get all students sponsored by a donor with their school information.

**Complexity**: Medium - Uses multiple JOINs with filtering and ordering.

```sql
SELECT DISTINCT 
    s.student_id,
    s.student_name,
    s.student_id_number,
    s.gender,
    s.date_of_birth,
    s.class_level,
    s.profile_image,
    s.family_monthly_income,
    s.has_scholarship,
    sch.school_name,
    sch.school_id
FROM students s
JOIN donations don ON s.student_id = don.student_id
JOIN schools sch ON s.school_id = sch.school_id
WHERE don.donor_id = ? 
AND don.payment_status = 'COMPLETED'
ORDER BY s.student_name;
```

---

### 9. Recent School Donations Query

**Purpose**: Get the 5 most recent donations received by a school.

**Complexity**: Medium - Uses multiple LEFT JOINs with CASE statements for recipient identification.

```sql
SELECT d.donation_id, d.amount, d.payment_status, 
COALESCE(d.donated_at, d.created_at) as donation_date, 
COALESCE(pt.transaction_reference, CONCAT('TXN', LPAD(d.donation_id, 6, '0'))) as transaction_ref, 
COALESCE(donor.donor_name, 'Anonymous Donor') as donor_name, 
CASE 
  WHEN d.student_id IS NOT NULL THEN CONCAT('Student: ', s.student_name) 
  WHEN d.project_id IS NOT NULL THEN CONCAT('Project: ', sp.project_title) 
  ELSE 'Unknown' 
END as recipient_name 
FROM donations d 
LEFT JOIN payment_transactions pt ON d.transaction_id = pt.transaction_id 
LEFT JOIN donors donor ON d.donor_id = donor.donor_id 
LEFT JOIN students s ON d.student_id = s.student_id 
LEFT JOIN school_projects sp ON d.project_id = sp.project_id 
WHERE (s.school_id = ? OR sp.school_id = ?) 
ORDER BY COALESCE(d.donated_at, d.created_at) DESC 
LIMIT 5;
```

---

### 10. Scholarship Summary Statistics Query

**Purpose**: Get overall scholarship status summary across all students.

**Complexity**: Low - Simple aggregation with conditional counting.

```sql
SELECT 
    COUNT(*) as total_students,
    SUM(CASE WHEN has_scholarship = 1 THEN 1 ELSE 0 END) as students_with_scholarship,
    SUM(CASE WHEN has_scholarship = 0 THEN 1 ELSE 0 END) as students_without_scholarship
FROM students;
```

---

### 11. NGO Project Analytics Query

**Purpose**: Get comprehensive analytics for NGO projects including funding status.

**Complexity**: Medium - Uses aggregation with GROUP BY and funding gap calculation.

```sql
SELECT 
    np.ngo_project_id,
    np.project_name,
    np.budget,
    np.status,
    COALESCE(SUM(npd.amount), 0) as total_donations,
    COUNT(DISTINCT npd.ngo_id) as donor_count,
    (np.budget - COALESCE(SUM(npd.amount), 0)) as funding_gap
FROM ngo_projects np
LEFT JOIN ngo_project_donations npd ON np.ngo_project_id = npd.project_id 
    AND npd.payment_status = 'COMPLETED'
WHERE np.ngo_id = ?
GROUP BY np.ngo_project_id, np.project_name, np.budget, np.status;
```

---

### 12. Geographic School Distribution Query

**Purpose**: Get school distribution and status by geographic regions.

**Complexity**: Medium - Uses multiple JOINs with geographic hierarchy and conditional aggregation.

```sql
SELECT 
    d.division_name,
    dist.district_name,
    u.upazila_name,
    COUNT(s.school_id) as school_count,
    SUM(CASE WHEN s.status = 'ACTIVE' THEN 1 ELSE 0 END) as active_schools,
    SUM(CASE WHEN s.status = 'AT_RISK' THEN 1 ELSE 0 END) as at_risk_schools
FROM schools s
JOIN divisions d ON s.division_id = d.division_id
JOIN districts dist ON s.district_id = dist.district_id
JOIN upazilas u ON s.upazila_id = u.upazila_id
GROUP BY d.division_name, dist.district_name, u.upazila_name
ORDER BY school_count DESC;
```

---

### 13. Fund Utilization Tracking Query

**Purpose**: Track fund utilization with transparency for a specific project.

**Complexity**: Medium - Uses JOINs with remaining amount calculation.

```sql
SELECT 
    fu.utilization_id,
    fu.amount_used,
    fu.expense_category,
    fu.description,
    fu.utilization_date,
    fu.status,
    d.amount as total_donation,
    (d.amount - fu.amount_used) as remaining_amount,
    donor.donor_name
FROM fund_utilization fu
JOIN donations d ON fu.donation_id = d.donation_id
LEFT JOIN donors donor ON d.donor_id = donor.donor_id
WHERE fu.project_id = ?
ORDER BY fu.utilization_date DESC;
```

---

### 14. Student Performance Analytics Query

**Purpose**: Analyze student performance and risk factors by class level.

**Complexity**: High - Uses aggregation with multiple conditional counts and risk status analysis.

```sql
SELECT 
    s.class_level,
    COUNT(*) as total_students,
    AVG(s.family_monthly_income) as avg_family_income,
    SUM(CASE WHEN dp.risk_status = 'HIGH' THEN 1 ELSE 0 END) as high_risk_count,
    SUM(CASE WHEN dp.risk_status = 'MEDIUM' THEN 1 ELSE 0 END) as medium_risk_count,
    SUM(CASE WHEN dp.risk_status = 'LOW' THEN 1 ELSE 0 END) as low_risk_count,
    SUM(CASE WHEN s.has_scholarship = 1 THEN 1 ELSE 0 END) as scholarship_recipients
FROM students s
LEFT JOIN dropout_predictions dp ON s.student_id = dp.student_id
WHERE s.school_id = ?
GROUP BY s.class_level
ORDER BY s.class_level;
```

---

### 15. Gamification Points & Leaderboard Query

**Purpose**: Calculate gamification points and rankings for donors.

**Complexity**: Medium - Uses window functions (RANK) with aggregation.

```sql
SELECT 
    dg.donor_id,
    dg.total_points,
    dg.current_level,
    dg.badges_earned,
    COUNT(d.donation_id) as total_donations,
    SUM(d.amount) as total_donated,
    RANK() OVER (ORDER BY dg.total_points DESC) as leaderboard_rank
FROM donor_gamification dg
JOIN donors donor ON dg.donor_id = donor.donor_id
LEFT JOIN donations d ON donor.donor_id = d.donor_id 
    AND d.payment_status = 'COMPLETED'
GROUP BY dg.donor_id, dg.total_points, dg.current_level, dg.badges_earned
ORDER BY dg.total_points DESC;
```


## Limitations

• **Internet Connectivity**: Rural areas may have limited internet access, affecting real-time data synchronization and platform accessibility

• **Digital Literacy**: Some school administrators and stakeholders may require training to effectively use the platform features

• **Payment Gateway Dependencies**: Reliance on third-party payment processors for donation transactions may cause delays or failures

• **Data Accuracy**: System effectiveness depends on accurate and timely data entry by schools, which may vary in quality

• **Language Barrier**: Currently designed primarily for English users, may need localization for Bengali-speaking users

• **Mobile Optimization**: While responsive, the platform may benefit from dedicated native mobile applications for better user experience


• **Verification Bottleneck**: Manual verification of schools and NGOs by admins may create bottlenecks in onboarding new institutions


---

## Future Work

• **Mobile Application Development**: Develop native iOS and Android apps for better accessibility and offline functionality

• **Bengali Localization**: Complete translation of the platform interface and content for local language support

• **Advanced AI Models**: Implement more sophisticated machine learning models for dropout prediction using historical data and additional factors

• **Blockchain Integration**: Implement blockchain technology for enhanced transparency and immutable donation records

• **SMS Integration**: Add SMS-based notifications and updates for areas with limited internet connectivity

• **Offline Synchronization**: Develop offline data entry capabilities with automatic synchronization when internet is available

• **Advanced Analytics**: Implement predictive analytics for funding needs forecasting and impact prediction


• **Automated Reporting**: Implement AI-generated impact reports and success stories based on data analysis


• **Automated Fraud Detection**: Implement AI-based fraud detection for suspicious activities

• **Parent Portal**: Create a dedicated portal for parents to track their children's progress and scholarship status

• **Government Dashboard**: Develop specialized dashboards for government officials to monitor regional education metrics

• **Scholarship Marketplace**: Create a marketplace where multiple scholarship providers can list opportunities


---

## Conclusion
BrightAid is a technology-driven platform designed to reduce student dropouts in rural Bangladesh by connecting donors, NGOs, and schools through a transparent and data-driven system.

Its key strengths include:

1. Prediction to identify at-risk students early.

2. Transparent fund tracking for donor trust and accountability.

3. Stakeholder engagement through messaging, gamification, and real-time updates.


By combining these features, BrightAid creates a sustainable ecosystem where students get timely help, schools receive resources, and donors see real impact. It addresses issues like poor monitoring and lack of transparency, leading to smarter, data-based decisions.

