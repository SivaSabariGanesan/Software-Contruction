## Blog Management - Use Case Diagram (GitHub Compatible)

```mermaid
flowchart TD
  Admin((Admin))
  Author((Author))
  Reader((Reader))

  Users["Manage Users"]
  Blogs["Manage Blogs"]
  Reports["View Reports"]
  
  WritePost["Write Blog Post"]
  EditPost["Edit Blog Post"]
  DeletePost["Delete Blog Post"]
  ViewOwn["View Own Blogs"]
  ManageComments["Manage Comments"]

  ViewBlogs["View Blogs"]
  SearchBlogs["Search Blogs"]
  CommentBlog["Comment on Blog"]
  LikeShareBlog["Like/Share Blog"]

  Admin --> Users
  Admin --> Blogs
  Admin --> Reports

  Author --> WritePost
  Author --> EditPost
  Author --> DeletePost
  Author --> ViewOwn
  Author --> ManageComments

  Reader --> ViewBlogs
  Reader --> SearchBlogs
  Reader --> CommentBlog
  Reader --> LikeShareBlog
