# CMS Public School — Clean Final

Single-file responsive website with Supabase Auth, Admin, Teacher and Student portals.

## Supabase
Project: CMS School
Project ref: vhbcoqfhxuzajaoqydnc

The package uses only the browser-safe Supabase publishable key. No service-role key is included.

## Portal workflow
- Admin: Supabase Auth -> active admin -> approvals, class/subject assignments, content and gallery management.
- Teacher: signup -> pending -> private verification files -> Admin approval -> class/subject assignment -> Teacher portal.
- Student: signup -> pending -> private verification files -> Admin matches admission number + DOB -> Student portal.

## Verification
ID proof, profile photo and camera capture are stored in private Supabase Storage buckets. Camera capture is a verification photo for manual review; this package does not claim biometric identity/liveness recognition.

## Deployment
Vercel: Framework = Other/Static, Build command blank, Output directory `.`.

## Final fixes in this build
- Homework schema/code mismatch fixed with `homework.title`.
- Teacher assignment UI filters subjects by selected class.
- Database trigger rejects invalid class/subject combinations.
- Student approval matches admission number + date of birth.
- Attendance duplicate prevention via existing unique constraint/index.
- Missing foreign-key indexes added for portal tables.
- RLS auth calls optimized in the affected teacher/homework policies.
- Approved profile photos are displayed through signed private Storage URLs.
- JS syntax checked for all inline scripts.

## Supabase dashboard hardening
Enable Authentication -> Password Security -> Leaked password protection. This is a hosted Auth setting and is not safely changed by the static frontend package.
