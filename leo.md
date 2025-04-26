## Blog Management - Use Case Diagram

```mermaid
%% Mermaid Use Case Diagram
usecaseDiagram
  actor Admin
  actor Author
  actor Reader

  Admin --> (Manage Users)
  Admin --> (Manage Blogs)
  Admin --> (View Reports)

  Author --> (Write Blog Post)
  Author --> (Edit Blog Post)
  Author --> (Delete Blog Post)
  Author --> (View Own Blogs)
  Author --> (Manage Comments)

  Reader --> (View Blogs)
  Reader --> (Search Blogs)
  Reader --> (Comment on Blog)
  Reader --> (Like/Share Blog)
```
