## Blog Management - Activity Diagram

```mermaid
flowchart TD
  Start([Start])
  
  Start --> Login{Login Successful?}
  
  Login -- Yes --> Dashboard
  Login -- No --> Start
  
  Dashboard --> ChooseRole{Are you Admin, Author, or Reader?}
  
  ChooseRole -- Admin --> AdminActions
  ChooseRole -- Author --> AuthorActions
  ChooseRole -- Reader --> ReaderActions
  
  AdminActions[Manage Users / Manage Blogs / View Reports]
  AuthorActions[Write Blog / Edit Blog / Delete Blog / Manage Comments]
  ReaderActions[View Blogs / Search Blogs / Comment / Like or Share]
  
  AdminActions --> Logout
  AuthorActions --> Logout
  ReaderActions --> Logout
  
  Logout([Logout])
  Logout --> End([End])
