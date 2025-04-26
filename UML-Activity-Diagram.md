## Blog Management - Full Activity Diagram

```mermaid
flowchart TD
  Start([Start])
  
  Start --> ChoiceLogin{Login or Register?}
  
  ChoiceLogin -- Login --> LoginPage[Login Page]
  ChoiceLogin -- Register --> RegisterPage[Register Page]

  LoginPage --> LoginSuccess{Login Successful?}
  RegisterPage --> RegisterSuccess{Register Successful?}

  LoginSuccess -- Yes --> Dashboard
  LoginSuccess -- No --> LoginPage

  RegisterSuccess -- Yes --> LoginPage
  RegisterSuccess -- No --> RegisterPage

  Dashboard --> RoleChoice{Select Role}

  RoleChoice -- Admin --> AdminDashboard
  RoleChoice -- Author --> AuthorDashboard
  RoleChoice -- Reader --> ReaderDashboard

  %% Admin Actions
  AdminDashboard --> ManageUsers["Manage Users: Add, Update, Delete"]
  AdminDashboard --> ManageBlogs["Manage Blogs: Approve, Edit, Delete"]
  AdminDashboard --> ViewReports["View Site Reports"]
  
  ManageUsers --> AdminDashboard
  ManageBlogs --> AdminDashboard
  ViewReports --> AdminDashboard
  
  %% Author Actions
  AuthorDashboard --> CreateBlog["Create New Blog"]
  AuthorDashboard --> EditBlog["Edit Existing Blog"]
  AuthorDashboard --> DeleteBlog["Delete Blog"]
  AuthorDashboard --> ManageOwnComments["Manage Comments on Own Blog"]

  CreateBlog --> SubmitBlog{Submit Blog for Approval?}
  SubmitBlog -- Yes --> WaitApproval["Waiting for Admin Approval"]
  SubmitBlog -- No --> AuthorDashboard

  WaitApproval --> ApprovalResult{Admin Approved?}
  ApprovalResult -- Yes --> Published["Blog Published"]
  ApprovalResult -- No --> Rejected["Blog Rejected: Edit and Resubmit"]

  Published --> AuthorDashboard
  Rejected --> AuthorDashboard

  EditBlog --> AuthorDashboard
  DeleteBlog --> AuthorDashboard
  ManageOwnComments --> AuthorDashboard

  %% Reader Actions
  ReaderDashboard --> BrowseBlogs["Browse Blogs"]
  BrowseBlogs --> ViewBlogDetail["View Blog Details"]
  
  ViewBlogDetail --> CommentBlog["Comment on Blog"]
  ViewBlogDetail --> LikeBlog["Like Blog"]
  ViewBlogDetail --> ShareBlog["Share Blog"]

  CommentBlog --> CommentSubmitted{Comment Submitted?}
  CommentSubmitted -- Yes --> ViewBlogDetail
  CommentSubmitted -- No --> CommentBlog

  LikeBlog --> ViewBlogDetail
  ShareBlog --> ViewBlogDetail
  
  %% Logout and End
  AdminDashboard --> Logout
  AuthorDashboard --> Logout
  ReaderDashboard --> Logout

  Logout([Logout]) --> End([End])
