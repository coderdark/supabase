# Supabase
This are notes about supabase tools and apis

## Auth

## Database

## Storage
+ Docs: https://supabase.com/docs/guides/storage
+ Schema: https://supabase.com/docs/guides/storage/schema/design
+ Helper Functions: https://supabase.com/docs/guides/storage/schema/helper-functions
+ To test RLS in storage, go to the `SQL Editor` and run queries against `storage.object`. You can then use the `Roles` button to impersonate and test your RLS.
```
SELECT * FROM storage.objects
```
+ To fetch the `buckets` you can use the following query
```
SELECT * FROM storage.buckets
```
