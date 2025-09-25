# Symbiont CMS Nhost Template

A ready-to-deploy Nhost template for content management with Notion integration.

## Quick Start

1. **Deploy to Nhost:**
   ```bash
   # Fork this repository
   # Connect to Nhost and deploy
   ```

2. **What you get out of the box:**
   - `posts` table with GraphQL API
   - Basic CRUD permissions for authenticated users
   - Notion integration ready
   - Auto-updating timestamps

3. **GraphQL API Examples:**
   ```graphql
   # Create a post
   mutation {
     insert_posts_one(object: {
       title: "My First Post"
       slug: "my-first-post"
       content: "Hello world!"
     }) {
       id
       created_at
     }
   }

   # Get all posts
   query {
     posts {
       id
       title
       slug
       created_at
       publish_at
     }
   }
   ```

## Local Development

```bash
# Start local development environment
nhost dev

# Access Hasura Console at http://localhost:9695/console
```

## Customization

- **Add fields**: Modify `nhost/migrations/default/01_create_initial_schema.sql`
- **Change permissions**: Update `nhost/metadata/databases/tables/tables.yaml` or use Hasura Console
- **Add relationships**: Use Hasura Console to create foreign keys and relationships

## Template Structure

```
nhost/
├── migrations/default/
│   ├── 00_enable_extensions.sql  # Required extensions
│   └── 01_create_initial_schema.sql  # Posts table schema
└── metadata/  # Pre-configured GraphQL API metadata
```