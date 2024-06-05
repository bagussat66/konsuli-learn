# konsuli-learn

ERD (Entity Relationship Diagram)

Entitas utama:
1. User
   - id (PK)
   - name
   - email
   - password
   - role (student/admin)

2. Course
   - id (PK)
   - title
   - description
   - price
   - admin_id (FK ke User)
#
3. Enrollment
   - id (PK)
   - user_id (FK ke User)
   - course_id (FK ke Course)
   - enrollment_date
#
4. Lesson
   - id (PK)
   - course_id (FK ke Course)
   - title
   - description
   - video_url
#
Relasi:
- User (1) --- (*) Enrollment
- User (1) --- (*) Course (sebagai admin)
- Course (1) --- (*) Enrollment
- Course (1) --- (*) Lesson

Use Case Diagram

Aktor:
1. Student
2. Admin
#
Use Case untuk Student:
- Mendaftar akun
- Login
- Melihat daftar kursus
- Mendaftar kursus
- Mengakses materi kursus
- Melihat progress belajar
#
Use Case untuk Admin:
- Login
- Mengelola data user (CRUD)
- Mengelola data kursus (CRUD)
- Mengelola data enrollment
- Melihat laporan dan statistik
- Membuat kursus baru
- Mengedit detail kursus
- Menambah materi kursus
- Melihat daftar student yang terdaftar di kursus
#
Use Case umum:
- Melihat profil
- Mengedit profil
- Logout

DFD (Data Flow Diagram)

DFD Level 0:
- Sistem Aplikasi Clone Udemy
  - Input: data user, data kursus, data enrollment
  - Output: informasi kursus, materi kursus, laporan
- Entitas eksternal: Student, Admin
#
DFD Level 1:
- Proses 1: Manajemen User
  - Input: data user
  - Output: informasi user
- Proses 2: Manajemen Kursus
  - Input: data kursus, data lesson
  - Output: informasi kursus, materi kursus
- Proses 3: Manajemen Enrollment
  - Input: data enrollment
  - Output: informasi enrollment, laporan
- Data Store: User, Course, Enrollment, Lesson
