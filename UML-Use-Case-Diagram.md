::: mermaid


flowchart LR
  %% Actors
  User([<<User>>]):::actor
  Trainer([<<Trainer>>]):::actor
  Admin([<<Admin>>]):::actor

  %% User Use Cases
  UC1((Register / Login)):::usecase
  UC2((View Dashboard)):::usecase
  UC3((Start Workout)):::usecase
  UC4((Log Exercise)):::usecase
  UC5((View Nutrition Plan)):::usecase
  UC6((Log Meal)):::usecase
  UC7((Track Progress)):::usecase
  UC8((Update Profile)):::usecase

  %% Trainer Use Cases
  UC9((Create Workout Plan)):::usecase
  UC10((Assign Workout)):::usecase
  UC11((View User Progress)):::usecase

  %% Admin Use Cases
  UC12((Manage Users)):::usecase
  UC13((Manage Workouts)):::usecase
  UC14((Manage Nutrition)):::usecase

  %% Layout padding for readability
  subgraph Users
    User
  end

  subgraph Trainers
    Trainer
  end

  subgraph Admins
    Admin
  end

  subgraph UseCases_User [User Use Cases]
    UC1
    UC2
    UC3
    UC4
    UC5
    UC6
    UC7
    UC8
  end

  subgraph UseCases_Trainer [Trainer Use Cases]
    UC9
    UC10
    UC11
  end

  subgraph UseCases_Admin [Admin Use Cases]
    UC12
    UC13
    UC14
  end

  %% Connections
  User --> UC1
  User --> UC2
  User --> UC3
  User --> UC4
  User --> UC5
  User --> UC6
  User --> UC7
  User --> UC8

  Trainer --> UC9
  Trainer --> UC10
  Trainer --> UC11

  Admin --> UC12
  Admin --> UC13
  Admin --> UC14

  %% Relationships
  UC2 --> UC3
  UC2 --> UC5
  UC2 --> UC7
  UC3 --> UC4
  UC5 --> UC6

  %% Styling
  classDef actor fill:#ffe0b3,stroke:#cc9900,stroke-width:2px;
  classDef usecase fill:#e0f7fa,stroke:#00838f,stroke-width:2px;

:::
