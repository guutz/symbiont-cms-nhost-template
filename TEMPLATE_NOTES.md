# Template Configuration Notes

## What's Pre-configured

This template includes:

1. **Database Schema** (`migrations/`)
   - Posts table with UUID, timestamps, Notion integration fields
   - Automatic updated_at trigger
   - Proper indexing on slug and publish_at

2. **GraphQL API** (`metadata/`)
   - Posts table exposed with full CRUD operations
   - Basic permissions for 'user' role
   - Ready for authentication integration

3. **Extensions**
   - pgcrypto for secure UUID generation
   - Row Level Security enabled

## For Template Users

After deploying this template:

1. **Authentication**: Add Nhost Auth to your frontend
2. **Permissions**: Customize in Hasura Console as needed
3. **Additional Tables**: Use migrations or Hasura Console
4. **Notion Integration**: Use the provided fields (notion_page_id, etc.)

## Development Workflow

- Use `nhost dev` for local development
- Hasura Console automatically available
- Changes to metadata can be exported and committed
- Migrations are version controlled