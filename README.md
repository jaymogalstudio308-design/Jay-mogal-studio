# JAY MOGAL STUDIO
Premium static website and Supabase-backed admin area. Hosting target: GitHub Pages only; Vercel is not used.

## Deploy
Open repository Settings → Pages → Build and deployment → GitHub Actions. The included workflow publishes the repository root.

## First administrator
Create a user in Supabase Authentication → Users, copy its UUID, then run in SQL Editor:
```sql
insert into public.admin_profiles(user_id,display_name,is_active) values ('YOUR-AUTH-USER-UUID','Studio Admin',true);
```
Sign in at /admin/. Only active admin_profiles users have management access.

The database schema, RLS and public studio-media bucket have been configured in the linked project. config.js contains only a public publishable key. Never expose service-role keys.
