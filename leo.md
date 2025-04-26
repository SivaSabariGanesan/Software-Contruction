## Blog Management - Use Case Diagram (GitHub Compatible)

```mermaid
flowchart TD
  Admin((Admin))
  Author((Author))
  Reader((Reader))

  Admin -->|Manage| Users
  Admin -->|Manage| Blogs
  Admin -->|View| Reports

  Author -->|Write| "Write Blog Post"
  Author -->|Edit| "Edit Blog Post"
  Author -->|Delete| "Delete Blog Post"
  Author --> "View Own Blogs"
  Author --> "Manage Comments"

  Reader --> "View Blogs"
  Reader --> "Search Blogs"
  Reader --> "Comment on Blog"
  Reader --> "Like/Share Blog"
```
