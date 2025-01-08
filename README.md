# Supabase
This are notes about supabase tools and apis

## General Notes or URLs
+ https://supabase.com/docs/guides/database/postgres/column-level-security

## RLS (Row Level Security)
+ https://supabase.com/docs/guides/database/postgres/row-level-security
+ This security is done at the ROW level
```SQL
create policy "policy_name"
on "public"."table_name"
as PERMISSIVE -- RESTRICTIVE (Policies are combined using the AND boolean operator) for PERMISSIVE (Policies are combined using the OR boolean operator) 
for SELECT --Type of SQL queries: SELECT INSERT, UPDATE, DELETE
to public
using (
  (select auth.uid()) = user_id -- this expression returns a boolean, if the table row has a user_id field that is equal to the authenticated user (get user uid by running this function auth.uid()) then the row(s) is returned.
)
```

## RBAC (Role Base Access Control)
+ https://supabase.com/docs/guides/database/postgres/custom-claims-and-role-based-access-control-rbac

## Auth

## Database

## Storage
+ Docs: https://supabase.com/docs/guides/storage
+ Schema: https://supabase.com/docs/guides/storage/schema/design
+ Helper Functions: https://supabase.com/docs/guides/storage/schema/helper-functions
+ To test RLS in storage, go to the `SQL Editor` and run queries against `storage.object`. You can then use the `Roles` button to impersonate and test your RLS. NOTE: supabase does not allow you to access `storage.objects` or `storage.buckets` in your app.  They force you to use the storage API.
```
SELECT * FROM storage.objects
```
+ To fetch the `buckets` you can use the following query
```
SELECT * FROM storage.buckets
```
